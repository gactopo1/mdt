# Modelo Digital del Terreno (MDT) Online

Herramienta web interactiva para el procesamiento de nubes de puntos, generación de mallas, curvas de nivel y cálculo de volúmenes directamente desde el navegador.

🔗 **[Ver Demo Online](https://gactopo1.github.io/mdt/)**

## 📋 Descripción

Esta aplicación permite transformar nubes de puntos en Modelos Digitales del Terreno (MDT) precisos sin necesidad de instalar software de escritorio. Utiliza algoritmos matemáticos avanzados para la interpolación de datos y librerías gráficas para la visualización en 2D y 3D.

## ✨ Características Principales

### 1. Importación de Datos
Soporta múltiples formatos de entrada para nubes de puntos:
*   **Excel:** `.xls`, `.xlsx`, `.xlsm`
*   **Texto:** `.csv`
*   **CAD:** `.dxf`

### 2. Métodos de Interpolación (Generación de Grilla)
Genera mallas regulares utilizando una amplia variedad de algoritmos:
*   **Básicos:** Vecino más cercano, Bilineal, Bicúbica.
*   **Geoestadísticos:** Kriging (Modelos Exponencial, Gaussiano, Esférico).
*   **Matemáticos:**
    *   Splines (Bicúbico, Bicuadrático).
    *   Mínimos Cuadrados Ajustados (Grado 1 y 2).
    *   Inversa de la Distancia (IDW) y Simple.
    *   Polígonos de Thiessen (Voronoi).
*   **Funciones de Base Radial (RBF):**
    *   Bessel, Neumann, Gaussiana, Lineal, Exponencial.
    *   Cúbica, Cuadrática.
    *   Multicuadrática e Inversa.
    *   Thin Plate Spline (TPS).

### 3. Curvas de Nivel
Generación y exportación de isolíneas:
*   Algoritmos: Marching Squares, Interpolación de Contornos, Triangulación de Delaunay.
*   **Exportación:** Descarga directa en formato **.DXF** con capas por niveles.

### 4. Cálculo de Volúmenes
*   Cubicación precisa de desmonte y terraplén.
*   Definición de plano de referencia (Cota Z).
*   Cálculo basado en prismas/tetraedros sobre la malla generada.

### 5. Visualización 3D
*   Visor interactivo basado en **Three.js**.
*   Soporte para WebGL 1 y WebGL 2.
*   Visualización de malla de alambre, superficie sólida, iluminación ambiental y direccional.
*   Plano de referencia visual.

## 🛠️ Tecnologías Utilizadas

*   **Core:** HTML5, CSS3, JavaScript (ES6+).
*   **Visualización 3D:** Three.js.
*   **Matemáticas y Geometría:**
    *   D3-Delaunay (Triangulación y Voronoi).
    *   Math.js (Cálculo matricial para Kriging/RBF).
*   **Manejo de Archivos:**
    *   SheetJS (xlsx) para archivos Excel.
    *   dxf-parser para archivos DXF.

## 🚀 Instalación y Uso Local

Al ser una aplicación estática (Client-side), no requiere un backend complejo.

1.  **Clonar el repositorio:**
    ```bash
    git clone https://github.com/gactopo1/mdt.git
    ```

2.  **Ejecutar:**
    Debido a las políticas de CORS de los navegadores (especialmente para cargar módulos ES6 y texturas), se recomienda usar un servidor local simple.

    *   Con Python 3:
        ```bash
        cd mdt
        python -m http.server 8000
        ```
    *   Con Node.js (http-server):
        ```bash
        npx http-server .
        ```

3.  Abrir el navegador en `http://localhost:8000`.

## 📖 Guía de Uso Rápida

1.  **Cargar Archivo:** Selecciona tu archivo de puntos (CSV, Excel o DXF).
2.  **Configurar Límites:** La app detecta automáticamente los extremos (X, Y, Z), pero puedes ajustar el paso de la malla y los niveles.
3.  **Generar Grilla:** Selecciona el botón "Grilla", elige el método de interpolación y ajusta los parámetros (ej. vecinos, nugget, rango).
4.  **Curvas de Nivel:** Ve a la sección de curvas, elige el método y visualízalas. Puedes exportarlas a DXF.
5.  **Vista 3D y Volumen:** Haz clic en "Volumen" para ver el modelo en 3D y calcular los movimientos de tierra respecto a una cota de referencia.

## ✒️ Autor

*   **GacTopo** - *Desarrollo Inicial*

---
*Este proyecto es una herramienta de uso libre para fines educativos y profesionales.*
