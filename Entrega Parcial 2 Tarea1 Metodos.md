# Class:  Unidad
-Atributos: HP, HP max, ATK, DEF, EVA
- `var HP max: Int`
- `var HP current: Int`
- `var ATK: Int`
- `var DEF: Int`
- `var EVA: Int`


# Trait:  Personaje		(Personaje extends Unidad)  2.0
-Atributos: Estrellas, contadorv, KO(bool)
- `var HP max: Int`
- `var HP current: Int`
- `var ATK: Int`
- `var DEF: Int`
- `var EVA: Int` //heredado de unidad?
- `var KO: Boolean`
- `var Estrellas: Int`
- `var Contadorv: Int`
- // `var Norma: Int`
- // `var ObjectiveChosen: str`
-Metodos:
- `recuperarPuntoVida()`
- `ganarEstrellas(cantidad: int)`
- `perder estrellas(cantidad: Int)`
- 
-Comentarios:gana [chapters/5]+1 estrellas por turno
puntos de victoria ganados dependiendo de rival 
(relacion personaje-wild unit, personaje-personaje por batalla)
En cada turno se revisa si ko=1, necesitando un 6-n*chapters del dado para => ko=0

# trait:  Wild Unit    (Wild Unit extends Unidad)
-Atributos:estrellas
- `var HP max: Int`
- `var HP current: Int`
- `var ATK: Int`
- `var DEF: Int`
- `var EVA: Int` //heredado de unidad
- `var Estrellas: int` // como estrellas se repite bien podria ser atributo de unidad

- 
-Comment: generan de manera aleatoria en encounter panel
quitan o dan estrellas segun resultado de batalla
tipo(chicken, robo ball,seagull determinan stats:HP,ATK,...,etc, idea de subclases con atributos val definidos?)

# Class: Norma
-Atributos: tabla con norma, estrellas, victorias. (no varian)
- `val Norma: list`   //idea de diccionario con norma de llave y dos condiciones? relacion pregunta una u otra segun eleccion
- `val ObjEstrellas: list`
- `val ObjVictorias: list`

-Compara con stats de personaje para subida de nivel y fin de juego. 
da a elegir objetivo (cual columna compara)
Comment: objetivo del juego, llegar a norma 6
norma check (en home panel) para subir de nivel y elegir un objetivo
hint de que personaje tiene que recordar "nivel de norma" y "objetivo de norma check"?

# Class: Tablero 2.0 
-Atributos: 
- `val Nombre: string`
- `val tipo: string`
- `val panelSiguiente: List[Tablero]= list() `
- 
-Metodos:
-`moverJugador(jugador: Jugador, resultadoDado:Int)`
-`efectoDelPanel(jugador:Jugador)`
-`realizarNormaCheck()`

Comments: (relacion personaje, tablero con movimiento, idea de puntero)
se puede modelar un mapa como punteros y diversos strings por bifurcacion 
Ej: Elegir string principal, strings secundarios en cada bifurcacion. entonces como los movimintos son 1 en 1,
permite elegir cual puntero principal que se mueve y determina donde esta. 
Home panel, bonus panel, drop panel, encounter panel, neutral panel. 
