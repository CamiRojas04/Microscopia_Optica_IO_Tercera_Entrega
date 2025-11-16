# Simulación de Microscopio 4f (Entrega 03 - Instrumentos Ópticos)
Este repositorio contiene los scripts en Python desarrollados para la Entrega 03 de la asignatura "Instrumentos Ópticos". El objetivo es simular la formación de imágenes en un microscopio infinito-corregido (sistema 4f) utilizando los principios de la Óptica de Fourier.Las simulaciones se realizan en el dominio de Fourier, implementando la Teoría de Abbe de formación de imágenes mediante la Transformada Rápida de Fourier (FFT) y el manejo correcto de las frecuencias espaciales (fftshift).
# Contenido del Repositorio
El proyecto se divide en dos simulaciones principales:
# 1. Simulación de Campo Claro (Bright-Field)
El script Campo_claro.ipynb simula un microscopio 4f estándar.
Carga de Objetos: Capaz de importar y procesar archivos de imagen (.png, .svg) como objetos de amplitud (p.ej., una mira USAF-1951).
Pupila (CTF): Define la Función de Transferencia Coherente (CTF) como una apertura circular simple, determinada por la Apertura Numérica (NA) del objetivo.
Formación de Imagen: Calcula la imagen final en el plano del sensor, demostrando la inversión de imagen (rotación de 180°) característica de los sistemas 4f.

# 2. Simulación de Contraste de Fase (Phase-Contrast)
El script Campo_oscuro.ipynb modifica el sistema anterior para simular un microscopio de contraste de fase tipo Zernike, diseñado para visualizar objetos de fase puros.
Objetos de Fase: Convierte la imagen de entrada en un objeto que solo modula la fase de la luz.
Pupila de Contraste de Fase: Implementa una función de pupila modificada que incluye:Una apertura estándar (limitada por el NA).Un "anillo de fase" central que atenúa ($\approx 50\%$) y desfasa ($\pi/2$ rad) la luz no difractada (componente DC) que pasa por el centro.
Resultado: Transforma las variaciones de fase del objeto (invisibles en campo claro) en variaciones de intensidad visibles en la imagen final.

# Tecnologías Utilizadas
Python 3NumPy: Para todos los cálculos numéricos y manejo de arreglos.
Matplotlib: Para la visualización de los resultados (objetos, pupilas e imágenes).
Pillow (PIL): Para la carga y redimensión de imágenes.
CairosSVG: (Opcional) Para la rasterización de archivos SVG.
