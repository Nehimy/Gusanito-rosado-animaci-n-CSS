# <span style="color:#6A5ACD"> Pink worm - animación CSS </span>

## Introducción:

En este ejemplo crearemos un gusanito rosado (litle pink worm) y lo animaremos con CSS también pondremos una imagen svg que sera el título  y finalmente pondremos audio.

![Pink worm - animación CSS](https://i.imgur.com/6LZIFVn.png)

### Creando un gusanito con CSS

Bien, lo primero que tenemos que hacer es crear una etiqueta div en HTML, ponerle tamaño y color para luego darle forma con la propiedad border.

Código HTML

`<div class="worm">`

Código CSS
```
.worm{
    background: #f08eae;
    border: 4px solid #d5389f;
    width: 50px;
    height: 50px;
    position: relative;
    left: 0px;
    border-top-left-radius: 25px;
    border-top-right-radius: 25px;
    border-bottom-left-radius: 25px;
    border-bottom-right-radius: 25px;
}
```

Como ya tenemos la forma del cuerpo del gusanito toca ponerle ojo, boquita y rubor para que nuestro gusanito (worm) se vea kawaii, para ello crearemos nuevos div y luego los posicionamos y le damos una forma ovalada.


Código HTML

```
<div class="worm">
    <div class="eye">
        <div class="iris">
            <div class="pupil"></div>
            <div class="mouth"></div>
            <div class="blush"></div>
        </div>
    </div>
</div>
```

Nota: aquí cometí un error ya que pupil e iris deberían llamarse solo pupil pero como me da flojeracambiar el HTML y CSS no hice la modificación. Además el orden no es el adecuado.
        
Código CSS

```
.eye{
    width: 12px;
    height: 14px;
    position: relative;
    background: #000;
    top: 8px;
    left: 4px;
    border-radius: 25px;
}

.iris{
    width: 6px;
    height: 6px;
    position: relative;
    background: #fff;
	top: 2px;
	left: 6px;
    border-radius: 25px;
}

.pupil{
    width: 6px;
    height: 6px;
    position: relative;
    background: #fff;
    top: 4px;
    left: -6px;
    border-radius: 25px;
}

.mouth{
  
  width: 4.5px;
  height: 2.5px;
  background: #000;
  position: absolute;
  border-radius: 9px;
  margin-top: 8px;
  right: 9px;
}

.blush{
  width: 10px;
  height: 8px;
  background:#e6008c;
  position: absolute;
  border-radius: 9px;
  margin-top: 8px;
  left: 2px;
}

```

### Creando la animación del movimiento en CSS

En este punto el gusanito rosa (litle pink worm) va a moverse en horizontal de derecha a izquierda en un determinado tiempo.

Y para que pueda verse más natural, mientras avanza irá encogiéndose y estirándose.


Código CSS

Añadimos la animación de nombre MoveOn  la clase .worm y creamos la animación.

`
.worm{
   animation: MoveOn 50s infinite, Worm 2s infinite;
}
`

```
@keyframes MoveOn{
  0%{
    margin-left: 100%;
  }
  48% {
  	transform: rotateY(0deg);
  }
  50% {
  	transform: rotateY(180deg);
  	margin-left: 0%;
  }
  
  98% {
  	transform: rotateY(180deg);
  }
  100%{
    margin-left: 100%;
    transform: rotateY(0deg);
  }
}
```

Un detalle extra, mientras el gusanito va siguiendo el recorrido que le dimos, vamos hacer que vaya cambiando un poco de color.

En las siguientes lineas de código en CSS veremos como va cambiando de color el cuerpo y rubor del gusanito.
 
 
 Código CSS
 
 Añadiremos las siguientes animaciones a la clase .worm y .blush.
 
 ```
 .worm{animation: MoveOn 50s infinite, Worm 2s infinite;
 }
 
 .blush{
    animation: TwoBlushes 2s infinite;
 }
 ```
 Aquí creamos las animaciones de:
 + cambio de color del cuerpo del gusanito.
 + cambio de color del rubor del gusanito.
 
 ```
 @keyframes Worm{
  0%{
  	/*background: #ff73a1;*/
    background: #fca2bf;
    width: 40px;
  }
  
  50%{
    /*background: #ff4dd2;*/
    border-top-right-radius: 50px;
    border-bottom-left-radius: 25px;
    border-bottom-right-radius: 5px;
   /* border-top: 7px solid black;*/
    background: #ff88af;
    width: 70px;
  }
  
  100% {
    background: #fca2bf;
  	width: 40px;
  }
}

@keyframes TwoBlushes{
  0%{
    background:#e6008c;
  }
  50%{
    background: #b75454;
  }
  100%{
    background:#e6008c;
  }
  
}
```
