# **SYSTEMS BALANCE SHEET — *Pueblo Quimera***

**Versión:** 0.1  
 **Rol:** balance, tuning y simulación mental  
 **Formato recomendado:** doc \+ spreadsheet (Google Sheets / Excel)

---

## **1\. Filosofía de balance**

### **1.1 Objetivo del balance**

No buscamos:

* equilibrio perfecto

* estabilidad eterna

* crecimiento exponencial controlado

Buscamos:

* **oscilación**

* **picos de tensión**

* **recuperaciones parciales**

* decisiones que *se sienten* antes de entenderse

El sistema debe tender al **desequilibrio manejable**, no al colapso inmediato ni a la estabilidad infinita.

---

## **2\. Curva de dificultad global**

| Fase | Días | Sensación |
| ----- | ----- | ----- |
| Early | 1–10 | Descubrimiento, errores perdonables |
| Mid | 11–30 | Caos encadenado, trade-offs claros |
| Late | 31+ | Crisis sistémicas, decisiones duras |

### **Regla**

* Early: errores cuestan **dinero**

* Mid: errores cuestan **estabilidad**

* Late: errores cuestan **opciones**

---

## **3\. Variables globales — rangos y efectos**

### **3.1 Felicidad (`happiness`)**

| Rango | Estado | Efecto |
| ----- | ----- | ----- |
| 70–100 | Contentos | \+ingresos menores |
| 40–69 | Inquietos | normal |
| 20–39 | Molestos | \+eventos sociales |
| 0–19 | Enfadados | bloqueos \+ crisis |

**Cambio diario típico:** −2 a \+3  
 **Regla:** nunca sube rápido sin coste.

---

### **3.2 Riesgo ecológico (`risk_ecology`)**

| Rango | Estado | Efecto |
| ----- | ----- | ----- |
| 0–30 | Estable | nada especial |
| 31–60 | Tenso | side-effects más frecuentes |
| 61–80 | Crítico | eventos ecológicos |
| 81–100 | Volátil | mutaciones \+ crisis encadenadas |

**Regla clave:**  
 Baja lentamente, sube rápido.

---

### **3.3 Estabilidad (`stability`)**

| Rango | Rol |
| ----- | ----- |
| 0–30 | Nada amortigua |
| 31–70 | Reduce impactos |
| 71–100 | Sistema robusto |

**Función:**  
 Reduce efectos negativos **hasta un máximo**, nunca los elimina.

---

## **4\. Economía (dinero)**

### **4.1 Ingresos base**

`Ingreso base diario = 300`

### **4.2 Modificadores**

* Turismo: \+0 a \+500

* Crisis: −100 a −400

* Eventos virales: \+rep, no siempre dinero

**Regla:**  
 El dinero soluciona el presente, **no el futuro**.

---

## **5\. Criadero — valores base de especies**

### **5.1 Población inicial**

`Población inicial estándar = 10`

### **5.2 Umbrales**

| Umbral | Efecto |
| ----- | ----- |
| \>50 | Impacto visible |
| \>100 | Presión ecológica |
| \>200 | Plaga potencial |
| \>400 | Crisis mayor |

---

### **5.3 Tasa reproductiva (`repro_rate`)**

| Valor | Interpretación |
| ----- | ----- |
| 0.05 | Lenta |
| 0.15 | Media |
| 0.30 | Alta |
| 0.50+ | Explosiva |

**Fórmula simplificada**

`crecimiento = población × (repro_rate − control)`

---

## **6\. Control institucional**

### **6.1 Control base**

`control = 0.05`

### **6.2 Mejoras**

* Infraestructura: \+0.05 a \+0.15

* Decretos: temporales

* Crisis: reduce control

**Regla:**  
 Nunca llegar a `control ≥ repro_rate` para todas las especies.

---

## **7\. Ecosistema — fórmulas base**

### **7.1 Contaminación**

`pollution += waste_daily − digestor_effect`

Valores típicos:

* waste\_daily: 3–10

* digestor\_effect por especie: 1–5

---

### **7.2 Biodiversidad**

`biodiversity += variedad − invasión − contaminación`

* Variedad: nº de especies distintas

* Invasión: especies invasivas × movilidad

---

### **7.3 Depredadores**

`predators += atractivo − estabilidad/20`

---

### **7.4 Presión de invasión**

`invasion_pressure +=`  
  `(repro_rate × 60) +`  
  `(mobility × 40) −`  
  `estabilidad/30`

---

## **8\. Viralidad y reputación**

### **8.1 Viral score (por especie)**

| Fuente | Puntos |
| ----- | ----- |
| Cute | \+15 |
| Gross | \+15 |
| Illegal | \+10 |
| Side-effect grave | \+10 |
| Normal | −10 |

---

### **8.2 Reputación (`online_rep`)**

* Sube rápido

* Baja poco

* Genera presión mediática

**Regla:**  
 Más reputación \= más eventos, no más control.

---

## **9\. Eventos — severidad y frecuencia**

### **9.1 Frecuencia base**

* 1 evento diario garantizado

* \+1 si `risk_ecology > 50`

* \+1 si hay plaga activa

### **9.2 Severidad**

| Severidad | Efecto |
| ----- | ----- |
| 1–2 | Local |
| 3 | Sistémico |
| 4 | Crisis |
| 5 | Cadena |

---

## **10\. Recuperación (anti-frustración)**

### **10.1 Mecanismos suaves**

* Decretos de emergencia

* Sacrificios económicos

* Eliminación drástica de especies

* “Reset narrativo” (escándalo tapa otro)

### **10.2 Regla**

Siempre debe existir **una salida costosa**, nunca bloqueo total.

---

## **11\. Simulaciones de prueba (recomendado)**

En el spreadsheet:

* Simula 10 días sin decisiones

* Simula 10 días de malas decisiones

* Simula 10 días de “optimización”

El sistema debe:

* empeorar sin jugador

* resistir malas decisiones

* romperse si se optimiza demasiado

---

## **12\. Números prohibidos**

* Multiplicadores infinitos

* Bonos permanentes sin coste

* “Reduce a 0” absolutos

* RNG sin explicación

---

## **13\. Uso del documento**

Este documento:

* se ajusta constantemente

* es la base para QA

* evita parches impulsivos

**Si un número no está aquí, es sospechoso.**

