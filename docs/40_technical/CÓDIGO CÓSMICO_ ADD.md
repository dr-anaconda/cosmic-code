# ADD — Architecture Design Document

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
- `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`
- `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md`

---

## 1. Propósito

Este documento define la **arquitectura técnica** del juego: stack, capas, componentes y flujos de datos. Es la referencia para decisiones de implementación.

**Principios:**
1. Escalable: crecer sin refactor masivo
2. Maintainable: código organizado y testeable
3. Performante: optimización para móvil y web
4. Secure: datos de usuario protegidos

---

## 2. Stack Tecnológico

### 2.1 Stack Propuesto

| Capa | Tecnología | Justificación |
|------|------------|---------------|
| **Frontend Web** | Next.js 14 (App Router) | SSR/SSG, SEO, performance |
| **Frontend Móvil** | React Native | Código compartido |
| **Backend** | Node.js + Express | JSON native, async |
| **Database** | PostgreSQL | Relacional, robusto |
| **Cache** | Redis | Sesiones, real-time |
| **Realtime** | Socket.io | Actualizaciones live |
| **Queue** | Bull + Redis | Jobs async |
| **Storage** | S3/CloudFlare R2 | Assets, saves |
| **Hosting** | Vercel + Railway | DX + scalable |

### 2.2 Alternativas Consideradas

| Opción | Pros | Contras |
|--------|------|----------|
| PHP + MySQL | Legacy, known | DX poorer |
| Unity | Mobile native | Code share harder |
| Python/FastAPI | ML potential | Overhead |

---

## 3. Arquitectura de Capas

```
┌────────────────────────────────────────────────────────────┐
│                    CLIENTE                                 │
│  ┌──────────────────────────────────────────────────────┐ │
│  │              UI Layer (React/React Native)           │ │
│  │    Components │ Hooks │ State (Zustand/Context)      │ │
│  └──────────────────────────────────────────────────────┘ │
│                           │                               │
│  ┌──────────────────────────────────────────────────────┐ │
│  │            API Client (TanStack Query + Axios)       │ │
│  └──────────────────────────────────────────────────────┘ │
└───────────────────────────┬──────────────────────────────┘
                            │ HTTPS/WSS
┌───────────────────────────▼──────────────────────────────┐
│                      SERVIDOR                             │
│  ┌──────────────────────────────────────────────────────┐ │
│  │              API Layer (Next.js API Routes)         │ │
│  │         Controllers │ Middleware │ Validation       │ │
│  └──────────────────────────────────────────────────────┘ │
│                           │                               │
│  ┌──────────────────────────────────────────────────────┐ │
│  │            Application Layer (Services)              │ │
│  │    GameService │ UserService │ TournamentService    │ │
│  └──────────────────────────────────────────────────────┘ │
│                           │                               │
│  ┌──────────────────────────────────────────────────────┐ │
│  │              Domain Layer (Entities/Logic)           │ │
│  │      Universe │ Planet │ Species │ Evolution        │ │
│  └──────────────────────────────────────────────────────┘ │
│                           │                               │
│  ┌──────────────────────────────────────────────────────┐ │
│  │           Infrastructure Layer                        │ │
│  │     PostgreSQL │ Redis │ S3 │ External APIs         │ │
│  └──────────────────────────────────────────────────────┘ │
└───────────────────────────────────────────────────────────┘
```

---

## 4. Módulos Principales

### 4.1 GameModule

Gestión del núcleo del juego.

**Responsabilidades:**
- Universos y planetas
- Evolución y mutaciones
- Simulación de ecosistemas
- Tick engine
- Eventos y milestones

**Servicios:**
```
GameService
├── createUniverse(userId)
├── getUniverse(id)
├── createPlanet(universeId, params)
├── runTick(planetId)
├── processEvolution(planetId)
├── triggerMutation(speciesId)
├── applyTerraform(planetId, changes)
└── triggerMilestone(planetId, type)
```

### 4.2 GeneticsModule

Sistema de creación de especies.

**Responsabilidades:**
- Editor genético
- Genomas y neural networks
- Mutaciones
- Banco genético

**Servicios:**
```
GeneticsService
├── createSpecies(planetId, genome)
├── editGenome(speciesId, changes)
├── mutateSpecies(speciesId)
├── calculateStats(genome)
├── exportToBank(speciesId, userId)
├── importFromBank(bankId)
└── mergeGenomes(speciesA, speciesB)
```

### 4.3 TournamentModule

Sistema de torneos.

**Responsabilidades:**
- Inscripciones
- Simulación de batallas
- Rankings
- Recompensas

**Servicios:**
```
TournamentService
├── createTournament(config)
├── register(tournamentId, ecosystem)
├── runSimulation(tournamentId)
├── calculateRankings(tournamentId)
├── distributeRewards(tournamentId)
└── getLeaderboard(tournamentId)
```

### 4.4 UserModule

Gestión de usuarios.

**Responsabilidades:**
- Auth y sesiones
- Perfiles
- Settings
- Progresión global

**Servicios:**
```
UserService
├── register(data)
├── login(credentials)
├── getProfile(userId)
├── updateSettings(userId, settings)
├── getGlobalProgress(userId)
├── purchaseItem(userId, item)
└── updateAchievements(userId, achievement)
```

---

## 5. Base de Datos

### 5.1 Schema Principal

**users**
```sql
CREATE TABLE users (
  id UUID PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  username VARCHAR(50) UNIQUE NOT NULL,
  password_hash VARCHAR(255),
  created_at TIMESTAMP DEFAULT NOW(),
  settings JSONB DEFAULT '{}'
);
```

**universes**
```sql
CREATE TABLE universes (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  name VARCHAR(30),
  day INTEGER DEFAULT 1,
  implosion_level INTEGER DEFAULT 0,
  speed_bonus FLOAT DEFAULT 0,
  knowledge_points INTEGER DEFAULT 0,
  is_active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT NOW()
);
```

**planets**
```sql
CREATE TABLE planets (
  id UUID PRIMARY KEY,
  universe_id UUID REFERENCES universes(id),
  name VARCHAR(25),
  position_x FLOAT,
  position_y FLOAT,
  star_type CHAR(1),
  temperature INTEGER,
  atmosphere JSONB,
  life_level INTEGER DEFAULT 0,
  ecosystem JSONB,
  created_at TIMESTAMP DEFAULT NOW()
);
```

**species**
```sql
CREATE TABLE species (
  id UUID PRIMARY KEY,
  planet_id UUID REFERENCES planets(id),
  name VARCHAR(30),
  genome JSONB,
  population INTEGER DEFAULT 10,
  generation INTEGER DEFAULT 1,
  created_at TIMESTAMP DEFAULT NOW()
);
```

### 5.2 Índices

```sql
CREATE INDEX idx_universes_user ON universes(user_id);
CREATE INDEX idx_planets_universe ON planets(universe_id);
CREATE INDEX idx_species_planet ON species(planet_id);
CREATE INDEX idx_events_day ON events(universe_id, day);
```

---

## 6. APIs

### 6.1 REST Endpoints

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST | /api/universes | Crear universo |
| GET | /api/universes/:id | Obtener universo |
| POST | /api/planets | Crear planeta |
| POST | /api/tick | Ejecutar tick |
| POST | /api/species | Crear especie |
| PUT | /api/species/:id | Editar especie |
| POST | /api/tournaments | Crear torneo |
| POST | /api/tournaments/:id/register | Inscribir |

### 6.2 WebSocket Events

| Evento | Dirección | Descripción |
|--------|-----------|-------------|
| tick_complete | Server→Client | Tick ejecutado |
| milestone_reached | Server→Client | Hito alcanzado |
| tournament_update | Server→Client | Cambio en torneo |
| notification | Server→Client | Notificación |

---

## 7. Sistemas Especiales

### 7.1 Tick Engine

El tick es el corazón del juego. Debe ser:

- **Determinista:** Mismo input = mismo output
- **Eficiente:** Procesar miles de planetas
- **Escalable:** Paralelizable

**Arquitectura:**
```
Tick Request
    │
    ▼
Queue (Bull)
    │
    ▼
Worker Pool (N workers)
    │
    ▼
Process Universe
    │
    ├── Process Planets (parallel)
    │     │
    │     ├── Run Species AI
    │     ├── Apply Mutations
    │     ├── Update Ecosystem
    │     └── Check Milestones
    │
    ├── Save State
    │
    └── Emit Events
    │
    ▼
WebSocket → Clients
```

### 7.2 Simulación de Batallas

Las guerras de ecosistemas se simulan en servidor:

1. Cliente envía ecosistema (species + stats)
2. Servidor ejecuta simulación (100+ iteraciones)
3. Se determinan ganadores
4. Se distribuyen rewards

**Tiempo:** 1-5 minutos por simulación (en cola)

### 7.3 Sistema de Eventos

Eventos se generan en tick:

```
Tick → Check Conditions → Generate Events → Queue Effects → Apply
```

**Tipos:**
- milestone (hitos de evolución)
- mutation (mutaciones)
- disaster (desastres)
- player_action (acciones del jugador)
- system (sistema)

---

## 8. Caching y Optimización

### 8.1 Estrategias

| Recurso | Estrategia |
|---------|------------|
| Universe state | Redis (hot), PostgreSQL (cold) |
| User sessions | Redis |
| Tournament cache | Redis (TTL: 1h) |
| Static assets | CDN (CloudFlare) |
| API responses | Next.js ISR/SSG |

### 8.2 Optimización Móvil

- Code splitting por ruta
- Lazy loading de imágenes
- Virtualización de listas
- Payload compression
- Prefetching de datos

---

## 9. Seguridad

### 9.1 Autenticación

- JWT con refresh tokens
- HTTP-only cookies
- Rate limiting
- CSRF protection

### 9.2 Validación

- Zod para schemas
- Sanitización de inputs
- SQL injection prevention (Prisma/ORM)

### 9.3 Anti-Cheat

- Validación server-side de acciones
- Observación de patrones anómalos
- Rate limits por usuario

---

## 10. CI/CD

### 10.1 Pipeline

```
Commit → Lint → Test → Build → Deploy Preview
                      │
                      ▼
                Staging (auto)
                      │
                      ▼
                Production (manual)
```

### 10.2 Entornos

| Entorno | URL | Propósito |
|---------|-----|-----------|
| Development | local | Desarrollo |
| Preview | preview.app | PR previews |
| Staging | staging.app | Testing |
| Production | app.com | Usuarios |

---

## 11. Escalabilidad

### 11.1 Horizontals

- Load balancer (Vercel)
- Auto-scaling workers (Railway)
- Database read replicas (PostgreSQL)

### 11.2 Verticals

- Redis cluster
- Larger instances para workers

---

## 12. Monitoreo

### 12.1 Métricas

- Error tracking: Sentry
- Performance: Vercel Analytics
- Uptime: UptimeRobot
- Logs: Pino + Logtail

### 12.2 Alertas

- Errors > 0.1% → Slack
- Latency p99 > 2s → Slack
- CPU > 80% → PagerDuty

---

## 13. Testing

### 13.1 Estrategia

| Tipo | Cobertura target | Herramienta |
|------|-----------------|-------------|
| Unit | 80% | Jest |
| Integration | 60% | Jest + Supertest |
| E2E | Core flows | Playwright |
| Load | - | k6 |

### 13.2 Cobertura

- Lógica de tick
- Cálculos de evolución
- APIs críticas

---

## 14. Checklist de Validación

- [ ] Stack definido
- [ ] Arquitectura de capas clara
- [ ] Módulos identificados
- [ ] Esquema de base de datos definido
- [ ] APIs documentadas
- [ ] Tick engine diseñado
- [ ] Caching strategy
- [ ] Seguridad cubierta
- [ ] Pipeline de CI/CD definido
- [ ] Monitoreo considerado

---

## 15. Declaración Final

**Esta arquitectura es un punto de partida. Evolucionará con el desarrollo según las necesidades reales del proyecto.**

---

**Documento creado bajo sistema CANON**  
**Fin de tanda inicial de documentos**
