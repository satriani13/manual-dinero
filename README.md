# El Manual del Dinero

Guía didáctica e interactiva para explicar **finanzas personales desde cero**. Incluye dos experiencias:

- **El Manual del Dinero** (`index.html`) — curso para **adolescentes y adultos** (desde ~15 años).
- **La Aventura del Dinero** (`ninos.html`) — versión para **niños de 9–11 años**, con historias interactivas y animaciones.

🔗 **Demo:** https://jpchost.ddns.net/proyectos/manual-dinero/ · Versión niños: `…/manual-dinero/ninos.html`

Web estática pura (HTML/CSS/JS, sin dependencias ni build). Cada página se sirve sola; se enlazan entre sí.

## El Manual del Dinero (`index.html`)

Curso paso a paso organizado en **3 pestañas**, cada una con su propio índice, subtítulo y contador de progreso:

1. **Módulos A·B·C — Curso base** (11 capítulos): qué es el dinero y por qué existe, ingresos vs gastos, inflación · el banco y la deuda (débito/crédito), presupuesto 50/30/20 y fondo de emergencia, impuestos (bruto/neto, IVA, IRPF) · interés simple vs compuesto, qué es invertir, activa vs pasiva y fondos indexados, el menú de activos (bolsa, inmobiliario, cripto) y la psicología del inversor. Incluye reglas de oro y examen de repaso.
2. **Módulo Inversiones** (caps. 12–20): profundización en cada producto —fondos indexados y activos, ETFs, ETCs, crowdlending, crowdfunding inmobiliario, inmobiliario directo, private equity y cripto— con ejemplos numéricos, libros recomendados y una tabla comparativa ("El mapa de las inversiones").
3. **Módulo fiscal** (caps. 21–26): la fiscalidad en España de cada activo del módulo anterior (las dos bases del IRPF, tramos del ahorro, traspaso de fondos, permuta de cripto, alquiler en base general…), con ejemplos y la tabla "Fiscalidad de un vistazo".

### Interactivo
- 🧮 Calculadora de **interés compuesto** con gráfico en vivo (lo que aportas tú vs lo que genera el interés).
- 📉 Simulador de **inflación** y 💰 repartidor de **presupuesto 50/30/20**.
- ✅ **Pruebas de comprensión** al final de cada capítulo + examen de repaso.
- 📊 **Progreso de las preguntas por módulo**, guardado **por usuario del portal**: la cookie de sesión es `httpOnly`, así que la página identifica al usuario vía `fetch('/auth/verify')` (cabecera `X-User`) y guarda el progreso en `localStorage` con ese nombre; fuera del portal usa un perfil local.
- 🌗 Modo claro/oscuro y diseño responsive.

## La Aventura del Dinero (`ninos.html`)

Versión para **niños (9–11 años)**, pensada como un cuento interactivo guiado por **Monedita** (una moneda con brazos y piernas que saluda). Personajes ilustrados en SVG con vida propia (parpadean, respiran, saludan, la coleta se balancea, el zapatero martillea, el abuelo habla) y escenarios animados (mercado, cuarto, calle con carrito de helados, jardín y dormitorio de noche, con nubes, pájaros, mariposas, flores y sol en movimiento). Los mini-juegos usan animaciones reales: objetos que vuelan en arco (Web Animations API), la hucha que se zarandea y engorda, la regadera que se inclina y el árbol que crece con rebote, y un efecto sepia de "foto antigua" en la máquina del tiempo. Cuatro historias:

1. **¿Qué es el dinero?** — el trueque (Nina quiere zapatos, el zapatero quiere pescado) y la invención de la moneda.
2. **Ganar, gastar y guardar** — reparte 5 monedas entre "gastar" y "guardar" (la hucha).
3. **¿Por qué suben los precios?** — una máquina del tiempo (slider) muestra la inflación.
4. **El dinero que crece** — planta y riega una moneda; el árbol crece y las monedas se duplican (interés compuesto).

Incluye **estrellas de progreso** (robustas: copia en memoria + `localStorage` cuando está disponible), trofeo final, modo día/noche, sonido on/off (WebAudio, solo en interacción) y respeto a `prefers-reduced-motion`. Interacciones por toque (funcionan en táctil y ratón). Desde la portada se enlaza al manual para mayores, y el manual enlaza a esta versión.

## Despliegue

Estático servido por nginx en el VPS (patrón pelusa/escata), registrado en el portal de demos (type `web`). Actualizar: editar en local → `git push` → en el VPS `cd /var/www/proyectos-src/manual-dinero && git pull` (nginx sirve al instante, sin reload).

## Changelog

- **Versión para niños, ilustraciones nuevas:** personajes y escenarios rediseñados con animaciones continuas y mini-juegos con movimiento (vuelos en arco, hucha que engorda, árbol que crece, sepia en la máquina del tiempo).
- **Versión para niños** (`ninos.html`): "La Aventura del Dinero", 4 historias interactivas (9–11 años), enlazada desde el manual.
- Subtítulo del hero adaptado a cada módulo; índice y contador de progreso filtrados por pestaña; 2ª pestaña renombrada a "Módulo Inversiones".
- Reorganización en 3 pestañas (Módulos A·B·C / Inversiones / Fiscal).
- Módulo fiscal (fiscalidad de cada activo en España).
- Fase 2: profundización en productos de inversión + progreso de preguntas por usuario.
- Versión inicial: curso base desde cero con calculadoras y quizzes.

## Aviso

Material **educativo**, no asesoramiento financiero ni fiscal personalizado. Las rentabilidades pasadas no garantizan las futuras y toda inversión puede perder valor. Los porcentajes de impuestos y los ejemplos son orientativos y pueden cambiar según el año y la comunidad autónoma.
