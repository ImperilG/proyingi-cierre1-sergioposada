# Investigación: ¿esto ya existe? ¿quién lo dice?

**Autor:** Sergio Eduardo Posada Montiel
**Fecha:** Domingo 20 de septiembre, 2026
**Ideas analizadas:** ver [ideas-proyecto](ideas-proyecto.md)

---

## Parte 1. Un ejemplo que ya existe, por cada idea

### Idea 1: Botes de basura inteligentes

- **Qué encontré:** Un tutorial de electrónica publicado en Circuit Digest, un sitio dedicado a proyectos con microcontroladores, llamado "IoT Based Smart Bin".
- **Enlace:** https://circuitdigest.com/microcontroller-projects/iot-based-smart-bin
- **Qué hace:** Usa un Arduino y dos sensores ultrasónicos: uno detecta cuando alguien acerca la mano y abre la tapa con un servomotor, y el otro mide qué tan lleno está el bote. Cuando el llenado llega a un porcentaje alto, el sistema manda un aviso a un tablero en línea (Firebase) para que alguien sepa que ya hay que vaciarlo.
- **Por qué no resuelve mi caso:** Está pensado para un solo bote doméstico conectado por WiFi a una cuenta personal, no para varios botes repartidos en la calle o en una escuela. Tampoco tiene ningún aviso sonoro, y depende de que alguien esté revisando la app; no sirve para que el personal de limpieza se entere sin tener acceso a ese sistema.

### Idea 2: Platos alimentadores

- **Qué encontré:** Una nota periodística de CGTN sobre una máquina que se instaló de verdad en una calle de Shanghái para alimentar gatos y perros callejeros.
- **Enlace:** https://news.cgtn.com/news/2020-10-14/Chinese-social-media-debates-first-auto-feeder-for-strays-UzMDd2QaC4/index.html
- **Qué hace:** La máquina suelta comida en un plato cuando alguien deposita una moneda o una botella de plástico usada, tiene paneles solares arriba y, atrás, un pequeño refugio donde puede recostarse un animal pequeño.
- **Por qué no resuelve mi caso:** No usa ningún sensor que detecte al animal —depende de que una persona ponga una moneda o botella—, y además causó quejas de vecinos por higiene y seguridad: la administración del lugar ordenó retirarla a los dos días. No se parece a lo que yo necesito para un fraccionamiento privado, donde el punto es que el plato se abra solo cuando el animal se acerca.

### Idea 3: Sin garrafones vacíos

- **Qué encontré:** Una tesis de licenciatura de la Facultad de Estudios Superiores Aragón de la UNAM sobre un sistema que monitorea y controla automáticamente el nivel de agua en los depósitos de una casa (cisterna y tinaco) usando IoT.
- **Enlace:** https://ru.dgb.unam.mx/bitstream/20.500.14330/TES01000846893/3/0846893.pdf
- **Qué hace:** Usa un microcontrolador ESP32 con un sensor ultrasónico y electrodos para medir el nivel de agua en la cisterna y el tinaco de una casa, enciende o apaga bombas automáticamente según ese nivel, y muestra el porcentaje de agua junto con avisos en una app (Blynk) para que el usuario sepa el estado del sistema desde su celular.
- **Por qué no resuelve mi caso:** Está pensado para el agua de la red pública que llena tinacos y cisternas en una casa, no para un garrafón individual en un edificio escolar, y la alerta llega a la app personal de un solo dueño de casa, no a un equipo de mantenimiento institucional. Tampoco incluye ningún diseño de base o mueble para esconder los componentes.

---

## Parte 2. Fuentes de la idea que elegí

### Fuente 1

| Campo | Contenido |
|---|---|
| Autor u organización | López Cruz Ángel Iván, dirigido por el Dr. Ismael Díaz Rangel — Universidad Nacional Autónoma de México (UNAM), Facultad de Estudios Superiores Aragón |
| Título | Sistema para automatizar la distribución de agua en los depósitos del hogar incorporando el paradigma de internet de las cosas |
| Año | 2023 |
| Enlace | https://ru.dgb.unam.mx/bitstream/20.500.14330/TES01000846893/3/0846893.pdf |
| Tipo | documentación técnica (tesis de licenciatura) |
| Por qué le creo | Es una tesis para obtener el título de Ingeniero Eléctrico Electrónico en la UNAM, con marco teórico, desarrollo experimental documentado paso a paso y pruebas reales de cada componente, no solo una opinión o un producto comercial. |
| Qué dato me dio | Documenta un problema real que tuvieron al medir con el sensor ultrasónico (lecturas erróneas cuando se toman muy seguido) y cómo lo resolvieron dejando un intervalo de varios segundos entre cada medición, un detalle práctico que me sirve directamente para programar mi propio sensor. |

### Fuente 2

| Campo | Contenido |
|---|---|
| Autor u organización | Angel L. Braña, Warren G. Panes, Metche A. Golez y Judy-An C. Albanes — Iloilo State University of Fisheries, Science and Technology, Filipinas |
| Título | AquaFy: Water Dispenser Monitoring System using IoT with SMS Notification |
| Año | 2025 |
| Enlace | https://lydwljxqxjucpixkyjzp.supabase.co/storage/v1/object/public/archive/papers/1772330436027-AquaFy_Water-Dispenser-Monitoring-System-using-IoT.pdf |
| Tipo | documentación técnica (artículo de revista académica) |
| Por qué le creo | Se publicó en una revista con ISSN (International Research Journal on Information and Communications Technology) y se probó con personal real y 306 estudiantes usando una metodología de evaluación de usabilidad (SUS), no es solo la palabra de los autores. |
| Qué dato me dio | Este estudio se hizo justo para instituciones (una universidad) y encontró que el monitoreo manual retrasa la reposición de agua; además probaron mandar alertas automáticas por SMS al personal encargado del mantenimiento, que es exactamente el problema que yo describo con quién repone los garrafones en la IBERO. |

### Fuente 3 (opcional)

| Campo | Contenido |
|---|---|
| Autor u organización | Yarana IoT Guru (Abhishek Maurya) |
| Título | IoT Based Smart Water Level Monitoring System using ESP32 |
| Año | 2025 |
| Enlace | https://www.hackster.io/yaranaiotguru/iot-based-smart-water-level-monitoring-system-using-esp32-de3de2 |
| Tipo | blog / tutorial técnico |
| Por qué le creo | No es un artículo académico, pero el autor comparte el código completo y funcional, además de fotos y los pasos de armado, en Hackster.io, una comunidad grande de proyectos de electrónica donde cualquiera puede revisar y comentar si el proyecto realmente funciona. |
| Qué dato me dio | El código completo para medir la distancia con un sensor ultrasónico HC-SR04 conectado a un ESP32 y mandar una alerta cuando el nivel baja de cierto umbral; me sirve como punto de partida ya que somos un equipo de principiantes. |

---

## Parte 3. Qué haría distinto

A diferencia de la tesis de la UNAM que encontré, que está pensada para el agua de la red pública que llena tinacos y cisternas de una sola casa y que además controla bombas, mi idea es más sencilla porque solo necesito medir cuánta agua queda en un garrafón, sin controlar ningún motor ni bomba, lo que la hace más fácil de construir en ocho sesiones siendo principiantes. También, en vez de mandar el nivel a una app como Blynk pensada para que la revise el dueño de una casa, la alerta necesita llegar a quien repone los garrafones en la IBERO, algo parecido a como lo hace el sistema de SMS del proyecto de Filipinas (AquaFy), pero usando el medio que ya use el personal de la universidad. Otra diferencia importante es que mi propuesta necesita adaptarse a varias estaciones de garrafones repartidas en distintos edificios de la IBERO, no a un solo depósito fijo como en los ejemplos que encontré, así que probablemente necesite un sensor independiente por estación. Por último, pienso esconder el sensor y la electrónica dentro de una base para el garrafón, algo que ninguno de los ejemplos que encontré propone, para protegerlos de derrames o golpes.

## Parte 4. Qué me falta averiguar

- [ ] Si existe un área o encargado específico en la IBERO responsable de reponer los garrafones, y cuál sería la mejor forma de avisarle (WhatsApp, correo, un tablero físico, etc.)
- [ ] Qué tan preciso sería medir el nivel de agua con un sensor ultrasónico a través de un garrafón opaco, o si conviene más un sensor de peso como pensé originalmente.
- [ ] Cuánto costarían los componentes (microcontrolador, sensor, batería o cable) conseguidos en México, y si alcanza el presupuesto típico de un equipo de principiantes.

---

## Declaración de uso de IA

- **Herramienta utilizada:** Claude (Anthropic), con la función de búsqueda web activada.
- **Qué le pedí:** A partir de mis tres ideas, le pedí que buscara un ejemplo real ya construido de cada una y que, para la idea que elegí, encontrara de dos a tres fuentes confiables sobre el tema.
- **Qué modifiqué o rechacé de su respuesta, y por qué:** Le pedí que cambiara la fuente de la Idea 3 porque, aunque el contenido estaba bien, venía en otro idioma y pues no me gustaba, así que le pedí que buscara fuentes en español o inglés. Después noté que el apartado de qué haría distinto seguía mencionando las fuentes del otro idioma así que le pedí que lo corrigiera para que tuviera coherencia con lo mencionado en las fuentes.
