# ECOVOLT · Prototipo digital

Prototipo de aplicación (una sola página, sin dependencias) para el proyecto **ECOVOLT**: sistema de enfriamiento residencial con energía solar y tubos subterráneos. Florencia, Caquetá, Colombia.

## Cómo abrirlo

- **En computador:** abre `index.html` con doble clic (Chrome, Edge o Firefox).
- **En celular (Android):** envía el archivo como **documento**, descárgalo y ábrelo con **Chrome**. No lo abras desde la vista previa de WhatsApp, Drive o Telegram: esas vistas no ejecutan JavaScript y el prototipo se ve vacío o roto.
- **Desde la red local:** si sirves esta carpeta en tu Wi-Fi (por ejemplo `http://192.168.1.11:8080/index.html`), ábrela desde Chrome en el celular. Si no carga, Windows está bloqueando el puerto en el firewall.
- No necesita instalación. Solo la tipografía se descarga de Google Fonts (si no hay internet se usa la fuente del sistema).

Si algo falla, la página muestra un aviso rojo con el detalle en lugar de quedarse en blanco.

## Acceso

| Opción | Datos |
|---|---|
| Cuenta demo | botón **Usar cuenta demo** (Camila Restrepo) |
| Crear cuenta | pestaña **Crear cuenta** (nombre + correo + contraseña de 4+ caracteres) |
| Invitado | enlace **Entrar como invitado** |
| Ingresar | cualquier correo válido + contraseña de 4+ caracteres |

La sesión se guarda en `localStorage`. Si el navegador bloquea el almacenamiento, el login sigue funcionando en memoria.

## Pantallas (10)

1. **Inicio** — qué hace el producto, diagrama del sistema, accesos rápidos.
2. **Simulador** — calcula temperatura de salida, efectividad, consumo y ahorro.
3. **Problema** — calor, humedad, costo del aire acondicionado y comparativo.
4. **Solución** — paneles, ventilador y tubos; conexión con el problema.
5. **Cómo funciona** — 4 pasos interactivos (seleccionables).
6. **Beneficios** — ahorro, comodidad, ambiente y adaptación.
7. **Materiales y pruebas** — insumos, protocolo, precauciones y requisitos.
8. **Modelo de negocio** — producto, clientes, costos e ingresos.
9. **Identidad** — logo, paleta, tono y eslogan.
10. **Contacto** — formulario validado, perfil de la sesión y confirmación.

## Interacciones que funcionan

- Login / registro / invitado / cerrar sesión.
- Navegación por menú lateral, barra móvil y botón atrás del navegador (rutas `#/pantalla`).
- Simulador con 4 controles: recalcula temperatura, consumo y ahorro; avisa riesgos por humedad o tubo corto.
- **Guardar en mi solicitud**: pasa los datos de la simulación al formulario de contacto.
- Pasos 1–4 de «Cómo funciona» con contenido dinámico.
- Formulario de contacto con validación y confirmación (envío **simulado**, sin backend).
- Guía del prototipo (botón del encabezado) con el mapa de la rúbrica.
- Animaciones del diagrama (sol, ventilador, flujo de aire) e interruptor **Animaciones** en el encabezado; la preferencia se guarda y no depende de la configuración de Windows.

## Relación con la actividad

| Requisito | Dónde se cumple |
|---|---|
| Se entiende el propósito | Inicio + eslogan + descripción del sistema |
| Usuario identificado | Login con nombre/correo reutilizado en contacto |
| La solución responde al problema | Problema → Solución → Cómo funciona |
| Mínimo 4 botones con función | Navegación, login, simulador, guardar, enviar, pasos |
| Login y pantallas de login | Ingresar, crear cuenta, demo, invitado, recuperación |
| Cada elemento tiene una función | Controles que calculan, pasos que cambian, formularios que validan |
| Pantallas ordenadas | 10 pantallas agrupadas en 4 bloques del menú |
| Textos legibles / imágenes pertinentes | Tipografía amplia, diagrama SVG del sistema, iconografía propia |
| Navegación completa | Menú, barra móvil, historial, botones de avance |
| Precauciones y requisitos | «¿Qué pasa cuando…?» + requisitos del usuario |

## Límites (importante)

- Los cálculos son **estimaciones educativas** (suelo a 24 °C, tarifa de $750/kWh); no son mediciones.
- El rendimiento real **no está comprobado**: no garantiza el frío de un aire acondicionado.
- El envío del formulario **no sale del navegador**: es una simulación del prototipo.

## Dónde editar

- Colores y medidas: variables CSS en `:root`.
- Pasos del sistema: arreglo `STEPS` en el `<script>`.
- Modelo del simulador: función `updateSim()`.
- Textos: directamente en cada `<section class="screen">`.

## Material del informe

La carpeta `informe/` es material aparte y **no** forma parte de la aplicación:

- `Equipo_Ecovolt_Gráficos_Semana4.xlsx`: **entrega de la actividad de Excel**. Hoja «Costos» con la tabla (fórmulas de kWh y costo) y el gráfico con título; hoja «Análisis» con las cinco preguntas respondidas.
- `grafico-costos.svg` / `grafico-costos.png`: gráfico de costos mensuales de energía (aire acondicionado, ventilador y ECOVOLT solar).
- `datos-costos.csv`: tabla de datos para Excel o Google Sheets.
- `datos-costos.md`: cifras, fórmulas, supuestos y cita sugerida.

Los datos salen del mismo escenario del simulador (45 W, 1.100 W, 8 h/día, 30 días, $750/kWh).

### Sobre el archivo de Excel

- En la hoja «Costos» se puede cambiar la tarifa en la celda `B9` y el consumo y los costos se recalculan solos.
- Las etiquetas del gráfico (`$198.000`, `$8.100`, `$0`) son texto fijo: si se cambian los datos, hay que ajustarlas a mano.
- El libro está listo para imprimir en una página por hoja (horizontal, ajustado al ancho).

### Para la presentación

- **Dos diapositivas listas:** `presentacion/Equipo_Ecovolt_Presentacion_Semana4.pptx` (editable en PowerPoint). Trae la vista previa en `presentacion/vista-previa-diapositivas.png`.
- **Gráfico suelto:** `presentacion/grafico-para-diapositiva.png`, para insertarlo en cualquier plantilla ocupando todo el ancho.
- **Si lo copias desde Excel:** en PowerPoint usa **Pegar especial → Metarchivo mejorado (EMF)** para que no se pixele.
- **Tabla:** selecciona `A4:F7` en Excel y pégala como imagen o como tabla.
- **Canva:** sube los PNG de la carpeta `presentacion/`; también puedes recrear el gráfico con su herramienta de gráficos.
- **Ojo:** si pegas el gráfico muy pequeño, el texto interno se ve diminuto. Déjalo ocupar casi todo el ancho.


