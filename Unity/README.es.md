# Unity en español

* [Camara](#C%c3%a1mara)
* [UI](#UI)

## UI

### Canvas

El canvas tiene diversos componentes entre ellos:

* Canvas
* Canvas Scaler
* Canvas Group
* Canvas Renderer

### Canvas Scaler

Es utilizado para controlar la escala en general y densidad de pixeles de los elementos UI en el Canvas.

Si deseamos que nuestro juego tenga una resolución responsiva tenemos que usar los anclajes de RectTransform, tal como indica en los videos [Canvas Scaler](https://www.youtube.com/watch?v=XkfhxuNr9Es) y [Scale UI to the right size for every resolution](https://www.youtube.com/watch?v=svyDgYz5idg).

## Cámara

En unity existen dos tipos de cámara:

* [Perspectiva](#perspectiva)
* [Ortográfica](#ortogr%c3%a1fica)

### Perspectiva

La cámara perspectiva se usa en la mayoría de los juegos, generalmente para mostrar la vista del jugador donde muestra una perspectiva desde donde se coloca, ideal para juegos 3D.

### Ortográfica

La cámara ortográfica se usa para escenas de un juego que son estáticas, un tablero o algún juego con un sola sola pantalla sin movimiento, ideal para juegos 2D.

> Para más información sobre las cámaras da click [aquí](https://www.youtube.com/watch?v=xvyrzwwU1DE)

### Skybox

El skybox es el fondo que unity te da con la cámara por defecto para crear un horizonte de lo que visualiza la cámara.

En este [tutorial](https://www.youtube.com/watch?v=hZTa_kkuSTg) muestra cómo **crear un skybox propio**.

Este otro [tutorial](https://www.youtube.com/watch?v=QT-6u6NLaus&t=2s) te sirve para **crear un material** para el skybox propio.

## Otros datos

### Archivos considerados en el control de versiones

Cuando creamos un nuevo proyecto de Unity los únicos folders que deben ser considerados para el control de versiones son:

`/Assets`

`/ProjectSettings`

Cualquier otro archivo debe ser considerado en un `.gitignore`

Ver más información [aquí](https://unity3d.com/es/learn/tutorials/topics/production/mastering-unity-project-folder-structure-version-control-systems)

### Como abrir dos proyectos de Unity en Mac

En Mac cuando abres dos proyectos en unity generalmente se cierra el que tienes actualmente abierto por defecto, para evadir esta configuración abre un nuevo Unity desde terminal con el siguiente comando:

```open -na Unity```

Una vez abierto podrás seleccionar tu proyecto que deseas abrir y podrás tener dos ventanas de Unity abiertas.

---

Actualizado el 25 de septiembre de 2018.