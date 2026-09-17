# Lista de tareas maestra · L1–L8

Alimenta la matriz de modelado. Cada fila del full kit clasificada por **tipo**, **disciplina**
(→ columna de la matriz) y **alcance** (→ fila General o por nivel), con el estado que dispara.

> **Estado del documento:** lista completa, **a validar**. Faltan sumar los protocolos de modelado
> por disciplina. Las tareas de modelado de ARQ y EST siguen los protocolos de modelado
> (instructivo paso a paso).

**Tipos:** Input (de cliente o asesor) · Tarea interna · Definición / Verificación ·
Entregable (plano) · Input/Output (planilla que alimenta cuantificaciones).

*Transcrito de `procesos documentacion\lista-tareas.html` el 16/09/2026.*

---

## Tarea 0 · Habilitación de archivos Revit — arranque de cada lote

Antes de modelar o documentar hay que habilitar los archivos: **dónde se modela** = archivo por
nivel y sistema; **dónde se documenta** = master federado del sistema. Es el primer paso de cada
protocolo y se dispara al abrir el lote.

| Lote | Sistema | Archivo de modelo | Master / documentación |
|---|---|---|---|
| **L1** | ARQ | Habilitar modelo ARQ | Habilitar master ARQ |
| **L1** | EST | Habilitar modelo EST | Habilitar master EST |
| **L4** | SAN | Habilitar modelo SAN | Habilitar master SAN |
| **L4** | AFC | Habilitar modelo AFC | Habilitar master AFC |
| **L4** | CMA | Habilitar modelo CMA | Habilitar master CMA |
| **L4** | GAS | Habilitar modelo GAS | Habilitar master GAS |
| **L4** | FPT | Habilitar modelo FPT | Habilitar master FPT |
| **L4** | ELE / ILU / BTE | Habilitar modelo de los tres juntos | Habilitar master ELE/ILU/BTE |
| **L5** | Coord. | **Habilitar MASTER DE PISO** (federado por piso): reúne todos los modelos del piso; se coordina y se documenta ahí mismo | |

Cada "Habilitar…" es el paso inicial del protocolo de ese sistema — crear desde template, vincular,
setear vistas — y se marca como hecho antes de arrancar a modelar o documentar.

> A futuro **L1 se divide en ARQ base y EST base**.

---

## L1 · Modelo base

Del kit viejo "L1 Modelo Arq + Est". **Alcance: General del proyecto** → alimenta la fila General.
**15 tareas, de las cuales 8 son inputs de terceros.**

### ARQ · Inputs

| # | Tarea | Alimenta |
|---|---|---|
| 1 | Anteproyecto de arquitectura (CAD o Revit) | precondición ARQ gral |
| 2 | Mensura final | precondición |
| 3 | Niveles de cordón y vereda | precondición |
| 4 | Ubicación de cero de proyecto y NSL losa sobre 1 SS (PB) | precondición |
| 5 | Escaleras: huella y contrahuella máx | precondición |

### ARQ · Tareas internas (base)

| # | Tarea | Alimenta |
|---|---|---|
| 6 | Poner en sistema (draft + model) | ARQ gral → **En proceso** |
| 7 | Definir ejes y grillas | ARQ gral → En proceso |
| 8 | Estudiar plenos y asignarlos | ARQ gral |
| 9 | Revisar niveles de proyecto y alturas libres | ARQ gral |
| 10 | Revisar espesores de contrapiso (según sistemas y terminación) | ARQ gral |
| 11 | Verificar acceso, pendiente y ancho de rampa | ARQ gral |
| 12 | Verificar niveles de escaleras, huella y contrahuella máx | ARQ gral → **Listo** |

### EST · Inputs (estructura general)

| # | Tarea | Alimenta |
|---|---|---|
| 13 | Proyecto estructural municipal | precondición EST gral |
| 14 | Modelo estructural listo (asesor) | precondición EST gral |
| 15 | Master cuantificación EST | precondición · liga cuantificación EST |

---

## L2 · Detallado ARQ + parámetros

Kit viejo "L1" (detalle + planillas) + **Protocolo de modelado ARQ · LOD 300+**. Alcance: General.
Ya sin EST. **Este protocolo se reutiliza por nivel en el modelado detallado de L5.**

### L2.1 · ARQ detallada — qué modelar

| # | Tarea | Alimenta |
|---|---|---|
| 1 | Muros: núcleo + revestimientos **como capas separadas vinculadas con constraint ("candadito")**, en TODOS los muros; tipos y espesores diferenciados por nombre de tipo/layer | ARQ gral |
| 2 | Tabiques divisorios (no estructurales) | ARQ gral |
| 3 | Revestimientos de muros y pisos (cerámicos, porcelanatos), diferenciados | ARQ gral |
| 4 | Cielorrasos por ambiente: altura y local; tipo y materialidad | ARQ gral |
| 5 | Solados/pisos: tipos de suelo por ambiente, diferenciados | ARQ gral |
| 6 | Zócalos | ARQ gral |
| 7 | Ventanas y puertas: tipo correcto, medidas reales y sentido de apertura; antepechos y dinteles | ARQ gral · **insumo L8** |
| 8 | Cocinas: muebles bajo mesada, alacenas, mesada, bacha y artefactos (anafe, horno) según familia provista | ARQ gral · **insumo L7** |
| 9 | Baños: artefactos (inodoro, bidet, lavatorio, ducha/bañera), mueble bajo bacha, mesada y nichos | ARQ gral · **insumo L7** |
| 10 | Mobiliario fijo: placares, vestidores | ARQ gral |
| 11 | Escaleras: medidas reales (pedada/alzada), con barandas y pasamanos | ARQ gral |
| 12 | Rampas con pendientes; barandas, pasamanos, parapetos y antepechos; balcones | ARQ gral |
| 13 | Rejillas y aberturas de ventilación arquitectónicas | ARQ gral |
| 14 | Cotas de nivel por planta; nombres de habitaciones/locales | ARQ gral · **insumo L7** |

### L2.2 · Parámetros y planillas — cierra L2

| # | Tarea | Tipo | Alimenta |
|---|---|---|---|
| 15 | Cargar parámetros del modelo: tipo y espesor de muro, material de revestimiento, tipo de piso/solado, tipo y medida de abertura, nombre de local, cota de nivel | Tarea | Parám ARQ → **Listo** |
| 16 | **Planilla de materialización de proyecto** (define materiales y parámetros) | In/Out | input → alimenta cuantificaciones 5D → se emite como output · **condición para documentar ARQ** |
| 17 | Planilla de locales | In/Out | input → cuantificación 5D (cómputo SD) → output · **insumo L7** |
| 18 | Planilla de artefactos | In/Out | input → cuantificación 5D → output |

**Criterios del protocolo ARQ.** Muro núcleo + revestimiento con "candadito", no muro multicapa
único. **Usa familias provistas, no las crea. No toma decisiones: modela según el CAD ARQ.** Nivel
de detalle alto: nichos, zócalos, muebles de cocina y baño bien resueltos, aberturas con tipo y
medida correctos.

---

## L3 · Ingenierías 2D

Kit viejo "L2 MEP 2D / Draft" — **45 definiciones técnicas** cerradas con los asesores.
Tipo: Definición. Alcance: General. Cada grupo lleva su disciplina a Listo en 2D.

### Estructuras

| # | Definición / Verificación |
|---|---|
| 1 | Niveles superestructura *(→ EST 2D Listo)* |
| 2 | Niveles subsuelo |
| 3 | Continuidad estructural (desde N1) en PB y SS |
| 4 | Verificar apeos |
| 5 | Verificar bajorrecorrido y sobrerrecorrido |
| 6 | Altura libre en cocheras |
| 7 | Espacio libre de estacionamiento |

### Sanitarias

| # | Definición / Verificación |
|---|---|
| 8 | Continuidad de plenos y plenos disponibles *(→ SAN 2D Listo)* |
| 9 | Salida pluvial PB |
| 10 | Desagüe pluvial balcones |
| 11 | Interceptor de naftas |
| 12 | Ubicación de pozos de bombeo |

### Agua (AFC)

| # | Definición / Verificación |
|---|---|
| 13 | Sala de máquinas subsuelos *(→ AFC 2D Listo)* |
| 14 | Sala de máquinas azotea + presurización |
| 15 | Montantes |
| 16 | Sala de bombeo |
| 17 | Ubicación reserva de incendio · **liga FPT** |
| 18 | Tipo: agua central / individual / gas / eléctrico |
| 19 | Qué pisos se presurizan y cómo |

### Eléctricas

| # | Definición / Verificación |
|---|---|
| 20 | Plenos eléctricos *(→ ELE 2D Listo)* |
| 21 | Sala de medidores o nicho en vereda |
| 22 | Caja y buzón |
| 23 | Info para gestión de factibilidad |
| 24 | Cámara transformadora — ¿de quién es? |
| 25 | ¿Domótica? · **liga BTE** |

### Incendio (FPT)

| # | Definición / Verificación |
|---|---|
| 26 | Ubicación nicho hidrante y matafuego *(→ FPT 2D Listo)* |
| 27 | Reserva de incendio |
| 28 | Separado de medianera |
| 29 | Mismo nivel fondo tanque y bomba |
| 30 | Sprinklers — ¿van o no? |

### Termomecánicas (CMA)

| # | Definición / Verificación |
|---|---|
| 31 | Pleno cove ventilación palier *(→ CMA 2D Listo)* |
| 32 | Continuidad plenos cove ventilación baños |
| 33 | Diseño ventilaciones SS |
| 34 | Ubicación AA |
| 35 | Tipo de calefacción |
| 36 | Si van radiadores |
| 37 | ¿Purificador o extractor? |
| 38 | ¿Parrillas? |
| 39 | Presurización de escaleras · **liga FPT** |
| 40 | Claraboya escalera |

### Gas

| # | Definición / Verificación |
|---|---|
| 41 | Ubicación medidores gas *(→ GAS 2D Listo)* |
| 42 | Ubicación pleno de gas |
| 43 | Ventilaciones de artefactos con gas |
| 44 | Ubicación medidor y regulador sobre LO |
| 45 | ¿Cocinas a gas o anafes? · **liga ARQ cocinas** |

---

## L4 · Ingenierías 3D

Kit viejo "L3 MEP 3D / Modelo" — **modelado troncal por sistema**. Alcance: General (troncal).
Arranca con la Tarea 0: habilitar el archivo de modelo y el master de cada ingeniería.

### Sanitarias

| # | Tarea de modelado |
|---|---|
| 1 | Bajadas cloacales principales *(→ SAN troncal Listo)* |
| 2 | Ubicación de ramal 87°30' con ventilación |
| 3 | Codo con acometida horizontal para inodoro |
| 4 | Ubicación de PPA y conexión a descarga |
| 5 | Bajadas pluviales y conexión con embudos |
| 6 | Conexión cloacal a acometida DP |
| 7 | Conexión pluvial en vereda |

### Termomecánicas (CMA)

| # | Tarea de modelado |
|---|---|
| 8 | Termomecánicas SS *(→ CMA troncal Listo)* |
| 9 | Cove ventilación palier |
| 10 | Cove ventilación baños |
| 11 | AA — ubicación condensadoras |
| 12 | Cocinas con extracción |
| 13 | Si hay piso radiante |

### Incendio (FPT)

| # | Tarea de modelado |
|---|---|
| 14 | Conexión desde tanque de incendio *(→ FPT troncal Listo)* |
| 15 | Montante y ubicación de nichos |
| 16 | Sprinklers |

### Agua (AFC)

| # | Tarea de modelado |
|---|---|
| 17 | Tanques sala de máquinas *(→ AFC troncal Listo)* |
| 18 | Termotanques o calderas |
| 19 | Colectores |
| 20 | Montantes |
| 21 | Distribuciones hasta unidades |

### Eléctricas

| # | Tarea de modelado |
|---|---|
| 22 | Bocas de iluminación *(→ ELE troncal Listo)* |
| 23 | Tomas |
| 24 | Interruptores |
| 25 | Bocas de emergencia |
| 26 | Tableros |
| 27 | Medidores |

### Gas

| # | Tarea de modelado |
|---|---|
| 28 | Medidores *(→ GAS troncal Listo)* |
| 29 | Tendidos en áreas comunes |
| 30 | Montantes |
| 31 | Conexiones hasta artefactos |

---

## L5 · Coordinación + completitud — plantilla por nivel

Kit viejo "Coord. Inicial / Intermedio / Final". **Este bloque se repite en cada nivel** — Fund, SS,
PB, tipo, retiro, azotea. Una fila por celda de la matriz; el paso a paso operativo vive en los
protocolos de modelado. **Cada entregable dispara Documentado (L6).**

### Coordinación — la bisagra

| # | Tarea / Entregable | Alimenta |
|---|---|---|
| 1 | **Coordinación del nivel**: interferencias entre disciplinas y pases críticos resueltos | Coordinación nivel → **Listo** |
| 2 | **Plano de interferencias del nivel (BISAGRA)** | Coord → **Documentado** · habilita la completitud |

### Completitud — modelado detallado por celda

| # | Tarea | Alimenta |
|---|---|---|
| 3 | Modelado detallado ARQ + albañilería (muros, terminaciones, pisos, cielorrasos) | ARQ nivel → Listo · planos ARQ → Documentado |
| 4 | Carga de parámetros del nivel (desde planilla de materialización) | Parám nivel → Listo |
| 5 | Modelado detallado EST (encofrados, pases, marks) | EST nivel → Listo · replanteo EST → Documentado |
| 6 | Modelado detallado SAN | SAN nivel → Listo · Plantas Sanitarias → Documentado |
| 7 | Modelado detallado AFC | AFC nivel → Listo · Plantas Agua → Documentado |
| 8 | Modelado detallado CMA | CMA nivel → Listo · Plantas Termomecánicas → Documentado |
| 9 | Modelado detallado GAS | GAS nivel → Listo · Plantas Gas → Documentado |
| 10 | Modelado detallado FPT | FPT nivel → Listo · Plantas Incendio → Documentado |
| 11 | Modelado detallado ELE / ILU (incluye bocas en losa) | ELE nivel → Listo · Plantas Eléctricas → Documentado |
| 12 | Modelado detallado BTE | BTE nivel → Listo · Plantas Corrientes Débiles → Documentado |

---

## L6 · Documentación

**No son tareas nuevas:** es la emisión de los planos que en L5 figuran como entregable. Cada plano
emitido lleva su celda a Documentado. Alcance: por nivel.

| # | Plano emitido (por nivel) | Disc. | Alimenta |
|---|---|---|---|
| 1 | Plano de replanteo EST (encofrados + pases) | EST | EST → Documentado |
| 2 | Plantas Sanitarias · Agua · Termomecánicas · Gas · Incendio · Eléctricas · Corrientes débiles | MEP | cada sistema → Documentado |
| 3 | Planos ARQ de albañilería: replanteo, revestimientos, pisos y zócalos, cielorrasos | ARQ | ARQ → Documentado |
| — | **Nivel con TODAS las celdas documentadas → nivel cerrado (se congela)** | — | emergente · **cambio posterior = extra-contractual** |

---

## L7 · Locales — paralelo

Cuelga de la ARQ detallada (L2), corre en paralelo y **realimenta la completitud (L5)**.
**Alcance: por tipología de local**, no por piso.

### ARQ · Inputs

| # | Tarea |
|---|---|
| 1 | **Checklist detalles de locales** |
| 2 | Proyecto de arquitectura base modelado (CONT-RE / CONT-TE) |

### ARQ · Tareas internas

| # | Tarea | Liga |
|---|---|---|
| 3 | **Tipificar baños y cocinas que se repiten** | realimenta completitud L5 |
| 4 | [COCINAS] Modular muebles, espacio para heladera | → L5 |
| 5 | [COCINAS] Alturas de mesada, alzada, alacenas | → L5 |
| 6 | [COCINAS] Extractores, bachas, griferías, anafes/hornos | → L5 · liga CMA/SAN |
| 7 | [COCINAS] Mesadas, banquinas | → L5 |
| 8 | [COCINAS] ¿Zócalo en mesada? | → L5 |
| 9 | [COCINAS] Alineación SAN / AGUA / ELE | → L5 · coordina MEP |
| 10 | [BAÑOS] Tipo de artefacto, ubicación, separación inodoro-bidet | → L5 |
| 11 | [BAÑOS] Modelar ducha, verificar desagüe, griferías | → L5 · liga SAN |
| 12 | [BAÑOS] Mesada, bacha, grifería, mueble, espejo | → L5 |
| 13 | [BAÑOS] Revestimientos, altura | → L5 |
| 14 | [BAÑOS] Cielorrasos | → L5 |
| 15 | [BAÑOS] Tendido de agua, llaves, descargas, PPA, puntos eléctricos | → L5 · liga SAN/AFC/ELE |

---

## L8 · Detalles — paralelo

Carpinterías: **las planillas son entregables que salen del modelo con parámetros.** Paralelo,
cuelga de la ARQ detallada (L2). Alcance: General.

| # | Planilla / Entregable | Alimenta |
|---|---|---|
| 1 | Planilla de carpinterías — **Ventanas** | plano + planilla ventanas · liga cuantificación |
| 2 | Planilla de carpinterías — **Puertas** | plano + planilla puertas |
| 3 | Planilla de **Herrerías / Barandas / Divisores** | plano herrerías |
| 4 | Planilla de **Frentes de Placard** | plano placares |

> **Diferencia con la matriz.** La lista tiene *frentes de placard* como cuarto ítem; la matriz usa
> *escaleras*. El cambio se decidió el 20/08/2026 al armar los tildes de L7 y L8. **Falta
> actualizar esta lista** o confirmar que van los cinco.

---

*Ctrl.S · reforma de lotes + matriz de modelado · lista de tareas maestra L1–L8*
