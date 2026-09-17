# Handoff · lotes, pesos y entregables

Para trabajar aparte el **reordenamiento de los lotes**: combinarlos con el producto que se vende y
linkearlos con los entregables.

Documento autocontenido — no hace falta conocer el resto del sistema para usarlo.
Corte: 16 de septiembre de 2026.

---

## 1. Qué es esto

**Ctrl.S Arquitectura** presta un servicio llamado **Documentación Quirúrgica**: toma un proyecto de
arquitectura ya diseñado y lo lleva a documentación de obra construible, coordinando todas las
ingenierías en BIM.

El trabajo está partido en **ocho lotes**, que son etapas con dependencia entre sí. Se miden con una
**matriz de modelado**: una grilla con una fila **General** —lo troncal del proyecto— y una fila por
**nivel** del edificio; las columnas son las disciplinas.

| | |
|---|---|
| Disciplinas | ARQ · EST · SAN (sanitaria) · AFC (agua fría y caliente) · CMA (termomecánica) · GAS · FPT (incendio) · ELE (eléctrica) · ILU (iluminación) · BTE (baja tensión) · Coordinación |
| Estados de cada celda | espera de draft · iniciar · en proceso · actualización · en validación · **listo** · desactualizado · **documentado** · no aplica |

Cada celda en cierto estado dispara el avance de un lote. **Cerrado** cuenta solo *listo* y
*documentado*; **avance del equipo** también suma lo empezado.

---

## 2. Los ocho lotes, con su peso

| Lote | | Peso | Alcance | Qué lo cierra |
|---|---|---|---|---|
| **L1** | Modelo base | **5** | General | ARQ y EST del General en Listo |
| **L2** | Detallado ARQ + parámetros | **5** | General (se reutiliza por nivel en L5) | ARQ de cada nivel en Listo (75%) + tildes de parámetros (25%) |
| **L3** | Ingenierías 2D | **10** | General, una celda por disciplina | que llegue el draft del asesor |
| **L4** | Ingenierías 3D | **10** | General (troncales) | los 8 sistemas MEP del General en Listo |
| **L5** | **Coordinación + completitud** | **40** | **Por nivel** | la columna Coordinación de cada nivel en Listo |
| **L6** | Documentación | **10** | Por nivel | las celdas del nivel en Documentado |
| **L7** | Locales | **10** | **Por tipología**, no por piso | 3 tildes: cocinas, baños, otros locales |
| **L8** | Detalles | **10** | General | 4 tildes de planillas |

**La coordinación se lleva 40 de los 100** porque es lo único que escala con la cantidad de niveles:
se repite entero en cada piso. Todo lo demás se hace una vez.

---

## 3. Qué hace cada lote y qué produce

Esta es la parte que importa para linkear con el producto: **qué sale de cada lote y si es algo que
el cliente recibe o algo que queda adentro del modelo.**

### L1 · Modelo base — 5 pts
**Objetivo:** poner el edificio en sistema y **verificar que lo recibido esté realmente resuelto**.
**15 tareas, 8 de ellas inputs de terceros** (anteproyecto, mensura final, niveles de cordón,
proyecto estructural municipal, modelo del asesor).
Las internas son ejes y grillas, plenos, niveles y alturas libres, espesores de contrapiso, rampas y
escaleras.
**Produce:** nada emitible. Es verificación y habilitación.

### L2 · Detallado ARQ + parámetros — 5 pts
**Objetivo:** llevar la arquitectura a LOD 300+ y cargar los parámetros.
14 tareas de modelado (muros con núcleo y revestimiento separados, cielorrasos por ambiente,
solados, zócalos, aberturas con medida real, cocinas, baños, mobiliario fijo, escaleras, rampas).
**Produce tres planillas que son input y output a la vez:**
- **Planilla de materialización** — define materiales; es **condición para documentar ARQ**
- **Planilla de locales** — insumo directo de L7
- **Planilla de artefactos**

Las tres alimentan las **cuantificaciones 5D**.

> **Criterio del protocolo, textual:** *"usa familias provistas, no las crea. No toma decisiones:
> modela según el CAD ARQ."* Es el límite del servicio: si el proyecto llega sin resolver, alguien
> tiene que decidir, y eso hoy no está en el alcance ni en el precio.

### L3 · Ingenierías 2D — 10 pts
**Objetivo:** cerrar con cada asesor las definiciones técnicas de su disciplina.
**45 definiciones**, repartidas: EST 7 · SAN 5 · AFC 7 · ELE 6 · FPT 5 · CMA 10 · GAS 5.
Van desde "salida pluvial de PB" hasta "¿sprinklers van o no?".
**Produce:** el draft de cada asesor. **No es un entregable nuestro: es un input que gestionamos.**

### L4 · Ingenierías 3D — 10 pts
**Objetivo:** modelar los troncales — montantes, bajadas, colectores, tableros, ventilaciones.
**31 tareas** repartidas en seis sistemas.
**Produce:** modelo, no plano. Es barato de cerrar y **desbloquea los 40 puntos de L5**.

### L5 · Coordinación + completitud — 40 pts
**Objetivo:** que las disciplinas no se pisen y completar el modelado de cada una, nivel por nivel.
**Se repite entero en cada nivel.** La secuencia:

> modelar troncales y estructura o vincular el IFC → **emitir el plano de interferencias** →
> corregir → **aprobar la coordinación** → completar el modelado de cada ingeniería → marcar los pases

**Produce:** el **plano de interferencias por nivel** — el único entregable del lote — más el modelo
completo de las 12 celdas del nivel.

### L6 · Documentación — 10 pts
**Objetivo:** emitir los planos. **No hay tareas nuevas: es sacar lo que ya se modeló en L5.**
**Produce, por nivel:**
- Plano de replanteo EST (encofrados + pases)
- Plantas Sanitarias · Agua · Termomecánicas · Gas · Incendio · Eléctricas · Corrientes débiles
- Planos ARQ de albañilería: replanteo, revestimientos, pisos y zócalos, cielorrasos

> **Regla que vale plata:** cuando todas las celdas de un nivel están documentadas, **el nivel se
> congela** y *"cambio posterior = extra-contractual"*.

### L7 · Locales — 10 pts
**Objetivo:** resolver cocinas y baños **por tipología**: tipificar los que se repiten, modular
muebles, definir artefactos, griferías, revestimientos, alturas.
15 tareas. Necesita como input el **checklist de detalles de locales**.
**Produce:** documentación de locales por tipología. **Realimenta L5**, porque la posición final de
los artefactos define la de algunos pases.

> El modelado de los locales vive dentro de la arquitectura (L2). L7 **documenta**, no modela.

### L8 · Detalles — 10 pts
**Objetivo:** emitir las planillas de carpinterías, que salen del modelo ya parametrizado.
**Produce:** planilla + plano de **ventanas**, **puertas**, **herrerías/barandas/divisores** y
**frentes de placard**.

> **Discrepancia pendiente:** la matriz usa *escaleras* como cuarto ítem en lugar de *frentes de
> placard*. Se cambió el 20/08/2026. Hay que unificar, o dejar los cinco.

---

## 4. El mapa entregable → lote

| Entregable | Sale de | Alcance |
|---|---|---|
| Planilla de materialización · de locales · de artefactos | **L2** | General |
| Plano de interferencias | **L5** | por nivel |
| Replanteo EST (encofrados + pases) | **L6** | por nivel |
| Plantas SAN · AFC · CMA · GAS · FPT · ELE · BTE | **L6** | por nivel |
| Planos ARQ de albañilería | **L6** | por nivel |
| Documentación de locales | **L7** | por tipología |
| Planillas de carpinterías y herrerías | **L8** | General |
| Cuantificaciones 5D | **L2** (vía las planillas) | General |

**De los ocho lotes, solo cuatro producen algo que el cliente recibe: L5, L6, L7 y L8.** Los cuatro
primeros producen estado del modelo — verificación, definiciones con asesores y troncales.

---

## 5. La tensión que hay que resolver

**El peso no sigue al entregable.**

- **L5 vale 40 puntos y emite un plano por nivel** — el de interferencias, que además es un
  documento de trabajo interno más que un producto.
- **L6 vale 10 puntos y emite todos los planos de obra** — los nueve juegos por nivel, que son lo
  que el cliente compró.

El peso está puesto sobre el **esfuerzo** —coordinar es donde se va el trabajo— y no sobre el
**valor entregado**. Para el trabajo de reordenar y linkear con el producto, esa es la decisión de
fondo: **si los lotes miden esfuerzo o miden producto.** Hoy miden esfuerzo.

Un dato que lo confirma: los contratos atan los **hitos de cobro a entregas de documentación**, o
sea a L6. Con la escala actual, un proyecto puede estar al 80% de avance y no haber emitido nada
cobrable.

---

## 6. Reglas de medición que hay que respetar si se reordena

**Emitir no cierra; validar cierra.** El plano de coordinación de un nivel emitido lo deja en
*Documentado*, que es la mitad del proceso. Lo cierra la aprobación del cliente o del asesor.
*(Confirmado el 07/09/2026, vale para todos los proyectos.)*

**La columna EST no pesa por sí sola en ningún lote.** Habilita: sin estructura no se coordina ni se
documenta, pero cerrarla no suma puntos directos.

**Una celda vacía cuenta como no hecha; "no aplica" sale del divisor.** No todas las disciplinas
tienen troncal —la eléctrica casi no ocupa espacio propio y la baja tensión no tiene—, así que esas
celdas van en *no aplica*.

**Una semana entera de trabajo puede dar cero.** Ya pasó tres veces: modelado de estructura por
nivel, y coordinación emitida sin validar. Es correcto según el criterio, pero hay que saberlo antes
de leer un ±0 como falta de avance.

**Terminar de modelar un nivel puede bajar el avance de equipo** — el "en modelado" de L5 cuenta los
estados en proceso pero no *Listo*. Es un defecto identificado y sin corregir.

---

## 7. Dónde está cada cosa

Repositorio `ctrls-tableros` (GitHub: `roozimmermann-arq/ctrls-tableros`):

| Archivo | Qué tiene |
|---|---|
| `LISTA-DE-TAREAS-POR-LOTE.md` | **La lista maestra completa**, tarea por tarea, con tipo, disciplina, alcance y qué estado dispara |
| `CRITERIO-DE-MEDICION.md` | Cómo se calcula el avance: pesos, qué fila mide cada lote, qué significa cada estado, trampas conocidas |
| `matriz-proyectos.html` | La matriz, con los ocho proyectos cargados |
| `flujo-lotes-y-estados.html` | Referencia visual de una página |
| `lista-tareas-original.html` | La fuente original de la lista |

---

## 8. Estado de la cartera, para contexto

Ocho proyectos. Al corte del 5/9, sobre la meta comprometida para el 30/9:

| Proyecto | Equipo | Cerrado |
|---|---|---|
| Moreno | 92% | 90% |
| Paroissien | 82% | 82% |
| Casa Sucre *(entregado, en soporte de obra)* | 58% | 42% |
| Ugarte | 52% | 29% |
| JPV | 32% | 15% |
| Cerri | 19% | 19% |
| Ciudad de la Paz | 18% | 12% |
| Manhattan | 11% | 6% |

**Ningún proyecto llegó a L7 ni L8** salvo Moreno, que tiene los locales cerrados, y Paroissien, que
acaba de tildar ventanas. **Los 20 puntos de locales y detalles están casi enteramente sin explorar
en la práctica** — dato relevante si se los va a reordenar o empaquetar como producto.

---

*Ctrl.S · handoff preparado el 16/09/2026 para trabajar el reordenamiento de lotes por producto*
