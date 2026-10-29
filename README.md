# 📡 Nexlink Telecomunicaciones — Portafolio Interactivo
> **Práctica Calificada N° 3 (PC3)**  
> **Curso:** Hojas de Estilo en Cascada Avanzado  
> **Docente:** Mg. Ing. CIP Hernán Francisco Peña Carne 
> **Alumno:** Keviin Smith Cusi Espinoza

Este proyecto es una landing page corporativa responsiva desarrollada con **Bootstrap 5**, **Transformaciones CSS (2D y 3D)** y **Animaciones CSS (@keyframes)** para una empresa especializada en servicios de telecomunicaciones, tendido de fibra óptica y radioenlaces.

---

## 🚀 Transformaciones y Animaciones Aplicadas

### 1. Transformaciones 2D y Transiciones (CSS Puro)
Ubicadas en la sección de **Servicios Especializados** ([`#servicios`](index.html#servicios)). Se aplican tres efectos geométricos bidimensionales al interactuar con el cursor (`:hover`), suavizados mediante `transition: transform 0.3s ease, border-color 0.3s ease;`:

* **Caja 1 — Tendido de Fibra Óptica (`.caja-rotate`):**
  * **Efecto:** Aplica una rotación leve en sentido horario.
  * **Código CSS:**
    ```css
    .caja-rotate:hover {
      transform: rotate(3deg);
      border-color: var(--green);
    }
    ```

* **Caja 2 — Radioenlaces Microondas (`.caja-scale`):**
  * **Efecto:** Aplica un escalado proporcional que expande la tarjeta un 6%.
  * **Código CSS:**
    ```css
    .caja-scale:hover {
      transform: scale(1.06);
      border-color: var(--amber);
    }
    ```

* **Caja 3 — Certificación OTDR (`.caja-skew`):**
  * **Efecto:** Combina una traslación hacia arriba en el eje Y con un sesgado angular.
  * **Código CSS:**
    ```css
    .caja-skew:hover {
      transform: translateY(-8px) skew(-2deg);
      border-color: #38bdf8;
    }
    ```

---

### 2. Transformaciones 3D (CSS Puro)
Ubicadas en la sección de **Infraestructura** ([`#infraestructura`](index.html#infraestructura)). Se implementa una tarjeta interactiva tridimensional que gira 180° sobre su eje vertical al hacer `:hover`:

* **Perspectiva:** El contenedor padre (`.contenedor-3d`) define la profundidad de campo:
  ```css
  .contenedor-3d {
    perspective: 1000px;
    height: 320px;
  }
  ```
* **Preservación 3D:** El elemento hijo (`.tarjeta-3d`) mantiene el contexto tridimensional para ambas caras con una transición fluida:
  ```css
  .tarjeta-3d {
    transform-style: preserve-3d;
    transition: transform 0.75s ease;
  }
  .contenedor-3d:hover .tarjeta-3d {
    transform: rotateY(180deg);
  }
  ```
* **Caras Anverso y Reverso:** Ambas caras utilizan `backface-visibility: hidden;`. La cara frontal muestra el nodo troncal activo y la cara posterior (`.cara-back` con `transform: rotateY(180deg);`) revela los parámetros de SLA corporativo.

---

### 3. Animaciones Avanzadas (@keyframes)
Se crearon dos animaciones CSS personalizadas con control de duración, repetición y función de tiempo:

* **Animación de Carga / Loader (`.loader-spinner`):**
  * **Función:** Spinner giratorio con borde bicolor (ámbar y verde) mostrado al inicio de la página.
  * **Control:** `animation: spin 1s infinite linear;`
  * **Keyframes:**
    ```css
    @keyframes spin {
      to { transform: rotate(360deg); }
    }
    ```

* **Animación de Flujo de Datos (`.stream-bar`):**
  * **Función:** Barra horizontal luminosa en el Hero que simula el tráfico continuo de datos en la troncal óptica mediante desplazamiento de degradado.
  * **Control:** `animation: streamPulse 2.5s infinite ease-in-out;`
  * **Keyframes:**
    ```css
    @keyframes streamPulse {
      0% { background-position: 100% 0; }
      100% { background-position: -100% 0; }
    }
    ```

---

## 🛠️ Estructura del Framework Bootstrap 5
1. **Navbar Responsivo:** Barra superior con colapso tipo hamburguesa (`navbar-toggler`) para móviles.
2. **Sistema de Grid:** Distribución adaptable con `container`, `row` y columnas (`col-md-4`, `col-lg-6`, `col-lg-7`).
3. **Formulario y Botones:** Inputs con `form-control`, `form-label`, `mb-3` y botones organizados con `d-grid gap-2 d-md-flex`.

---

## 📂 Archivos del Proyecto
* [`index.html`](index.html): Estructura semántica HTML5 y maquetación Bootstrap 5.
* [`css/styles.css`](css/styles.css): Hoja de estilos con variables, transformaciones 2D/3D y animaciones CSS.
* [`assets/`](assets/): Recursos multimedia (fotografía realista de instalación de antena).
