# Recursos interactivos — Microeconomía Intermedia

Simuladores interactivos, en archivos HTML autocontenidos, para la enseñanza de Microeconomía Intermedia en cursos de grado avanzado. Cada recurso permite visualizar y manipular en tiempo real los elementos analíticos centrales del modelo correspondiente, mediante controles deslizantes que actualizan gráficos y valores numéricos sin necesidad de recarga.

---

## Elección óptima del consumidor — simulador interactivo

Simulador interactivo, en un único archivo HTML autocontenido, para la enseñanza de la teoría del consumidor en cursos de Microeconomía Intermedia. Permite visualizar el óptimo del consumidor bajo distintas funciones de utilidad y descomponer el efecto de una variación de precio en efecto sustitución y efecto ingreso, mediante los procedimientos de **Slutsky** y de **Hicks**.

[**Demo en vivo**](https://fcontiggiani.github.io/microeconomia-recursos/consumer_choice_standalone.html)

[![Captura del simulador](https://github.com/fcontiggiani/microeconomia-recursos/raw/main/captura.png)](/fcontiggiani/microeconomia-recursos/blob/main/captura.png)

### Descripción

La herramienta calcula, para cada combinación de precios, ingreso y parámetros de preferencias que el usuario define mediante controles deslizantes, la canasta óptima del consumidor y su descomposición ante una variación del precio del bien x. El cálculo se resuelve de forma enteramente numérica (búsqueda áurea unidimensional, tanto para el problema primal de maximización de utilidad como para el problema dual de minimización del gasto), por lo que el resultado es robusto ante soluciones de esquina y válido para cualquier combinación de parámetros admitida por cada caso.

### Casos contemplados

| Función de utilidad                                          | Caso ilustrado                      | Efecto sustitución                   | Efecto ingreso                       |
| ------------------------------------------------------------ | ------------------------------------ | ------------------------------------- | ------------------------------------- |
| Cobb–Douglas, U(x,y) = xᵅy¹⁻ᵅ                                | Bien normal (referencia homotética)  | Refuerza                              | Refuerza                              |
| Cuasi-lineal, U(x,y) = A·ln(x) + y                           | Bien neutro                          | Explica la totalidad de la respuesta  | Nulo                                  |
| No separable, U(x,y) = A·ln(x) + y·(1 − c·x)                 | Bien inferior                        | Domina (ley de demanda se preserva)   | Se opone                              |
| Complementarios perfectos (Leontief), U(x,y) = min(x/a, y/b) | Efecto sustitución nulo              | Nulo                                  | Explica la totalidad de la respuesta  |

Un panel de diagnóstico clasifica automáticamente el bien (normal, neutro, inferior o de Giffen) a partir de los signos calculados en cada actualización de los controles, lo que permite además que el estudiantado explore, mediante los parámetros del caso inferior, la dificultad inherente a la construcción de un bien de Giffen a partir de preferencias bien comportadas.

### Uso en el aula

1. Seleccionar la función de utilidad en el menú desplegable superior.
2. Ajustar precio inicial y final del bien x, precio del bien y e ingreso monetario mediante los controles deslizantes.
3. Alternar entre el método de descomposición de Slutsky y el de Hicks para contrastar ambas definiciones de compensación.
4. Consultar el panel lateral para los valores numéricos de las canastas óptimas (A, B y C) y la magnitud de cada efecto, y el panel de notas formales para la justificación analítica del caso seleccionado.

---

## Especialización bajo ventaja comparativa — modelo ricardiano

Simulador interactivo, en un único archivo HTML autocontenido, para la enseñanza del modelo ricardiano de comercio internacional con tecnologías lineales. Permite visualizar la frontera de posibilidades de producción (FPP) de dos países, la solución de esquina de especialización completa según el precio relativo internacional, y la construcción de la FPP conjunta (mundial) como envolvente de la asignación eficiente de un planificador central.

[**Demo en vivo**](https://fcontiggiani.github.io/microeconomia-recursos/especializacion_ricardiana.html)

### Descripción

La herramienta resuelve, para cada combinación de requerimientos unitarios de trabajo, dotaciones de factor y precio relativo internacional definidos mediante controles deslizantes, el programa de optimización lineal de cada país (solución de esquina) y del planificador central (envolvente cóncava por tramos). Los tres gráficos —FPP de cada país y FPP mundial— se actualizan en tiempo real, junto con un panel de veredicto que identifica el patrón de especialización predicho por el modelo y el rango de precios relativos compatible con comercio mutuamente beneficioso.

### Elementos contemplados

| Bloque analítico                          | Contenido                                                                                   |
| ------------------------------------------ | --------------------------------------------------------------------------------------------- |
| FPP nacional (países A y B)               | Segmento lineal determinado por $a_{1i}, a_{2i}, \bar L^i$; solución de esquina según $p^w$   |
| Costo de oportunidad doméstico             | $\theta_i = a_{1i}/a_{2i}$, calculado y comparado dinámicamente entre ambos países             |
| Rango de comercio mutuamente beneficioso   | Intervalo $[\theta_{\min}, \theta_{\max}]$ dentro del cual el precio internacional induce especialización completa en bienes distintos |
| FPP mundial (planificador central)         | Envolvente poligonal construida por ordenamiento de los tramos de trabajo según $\theta_i$ creciente; vértice y régimen de especialización mundial |

### Uso en el aula

1. Ajustar los requerimientos unitarios de trabajo ($a_{1i}$, $a_{2i}$) y la dotación de trabajo ($\bar L^i$) de cada país mediante los controles deslizantes del panel izquierdo.
2. Modificar el precio relativo internacional $p^w = p_1/p_2$ y observar el desplazamiento del punto óptimo entre los vértices de cada FPP nacional.
3. Contrastar el panel de veredicto para identificar si el precio vigente induce especialización completa (dentro del intervalo $[\theta_{\min}, \theta_{\max}]$) o convergencia de ambos países al mismo bien (fuera de dicho intervalo).
4. Consultar el gráfico de la FPP mundial para verificar que la asignación del planificador central reproduce la asignación descentralizada de mercado — ilustración aplicada del primer teorema del bienestar en un entorno de tecnología lineal.

---

## Estructura del repositorio

```
.
├── consumer_choice_standalone.html   # Elección óptima del consumidor y descomposición Slutsky/Hicks
├── especializacion_ricardiana.html   # Especialización ricardiana y FPP del planificador central
├── captura.png                       # Imagen de vista previa utilizada en este README
└── README.md
```

Ambos archivos son autocontenidos (HTML, CSS y JavaScript plano) y no requieren proceso de compilación ni instalación de paquetes. Las únicas dependencias externas son tipográficas (Google Fonts) y, en el caso del simulador de especialización ricardiana, la librería MathJax (servida desde cdnjs.cloudflare.com) para el renderizado de notación matemática.

## Requisitos técnicos

Cualquier navegador moderno con JavaScript habilitado (Chrome, Firefox, Edge, Safari). No se requiere conexión a internet salvo para la carga inicial de tipografías y, en el segundo simulador, de MathJax; el resto de cada aplicación se ejecuta íntegramente en el cliente, sin comunicación con servidor alguno.

## Autoría y uso

Material de apoyo docente desarrollado para la cátedra de Microeconomía Intermedia. Los valores numéricos son ilustrativos y se recalculan dinámicamente; no representan datos empíricos reales salvo indicación expresa. Se autoriza su reutilización y adaptación con fines educativos, citando la fuente.
