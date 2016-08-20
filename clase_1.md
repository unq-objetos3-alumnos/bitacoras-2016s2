# 19 / 08 / 2016

## Introducción a la materia

### Link Útiles

 - Sitio de la materia: https://sites.google.com/site/programacionhm/unq
 - Github con ejemplos de la materia https://github.com/orgs/uqbar-paco (tip: filren por "obj3")
 - Canal de youtube: https://www.youtube.com/channel/UC20rhT1zAZyVRZuRqukk74Q/videos

### Forma de evaluación

 - 4 trabajos prácticos y dos días de recuperatorios.
 

### Qué vimos

 - Se repasaron brevemente conceptos vistos en materias anteriores (clases, interfaces, prototipos, polimorfismo)
 - Se comentó que la materia se enfoca principalmente en tres temas: Mixins/Traits, Metaprogramación y DSLs. 
 - Dimos una introducción al lenguaje Scala
 - Presentamos el ejercicio "Age of Empires" y planteamos soluciones basadas en herencia simple y herencia múltiple 
 - Se presentó el concepto de Mixins como una alternativa para la resolución del ejercicio anterior (de manera acelerada porque quedaba poco tiempo de clase, la siguiente clase vamos a volver sobre esto).

 
## Para la clase siguiente

 - Completar el formulario de grupos para TPs
 - Leer el paper de [Mixins](https://d8a0dde1-a-62cb3a1a-s-sites.googlegroups.com/site/programacionhm/conceptos/mixins/Paper%20-%20Bracha%2C%20Cook%20-%20Mixin-Based%20Inheritance.pdf?attachauth=ANoY7cqbcrZ3pmTTzR7PWq9dJQqoJERPbWgsN1HOkIl5vHo7Z8YFAS2khfzq3v-M8rHTsGGl9NT4LW87Z6evHTc_1g7oCfGw0SQG_VyjVZtyIC5utmPvI-c10Y_l2tTCfNxxkckw9OGDFJt9nARVAhUTfHSp9RulcrVxCfAncjES63FC6XTzuVtUp-DQXtKJac-fzFcpxaFApQmwFkGI2gAXF9JdZpSie6ov4LlGtDjEGcP-nkNzeHvAGo45sMNnJxncfTUK9ndQDLiSXIeWjlq-7FKr5sYK8mpfYlUKNQBI7oatfpkUHHA%3D&attredirects=0)
 - Opcional: los ejercicios que aparecen a continuación

### Algunos ejercicios para repasar uso de colecciones:

En [el sitio de la materia](https://sites.google.com/site/programacionhm/te/scala/introduccin-a-scala) van a encontrar los métodos vistos en clase.

Dadas las clases:

```scala
class Casa(val direccion:String, val ambientes:Int) {
    override def toString = s"\n  ${this.getClass().getSimpleName}(direccion=$direccion, ambientes=$ambientes)"
}

class Departamento(dir:String, val piso:Int, val numero:Int, cantidadAmbientes:Int) 
extends Casa(s"$dir, piso $piso, departamento $numero", cantidadAmbientes) 

class Edificio(val departamentos:Seq[Departamento]) {
    override def toString = s"\n  Edificio( departamentos=$departamentos )"
}

``` 

Donde la cantidad de pisos de un edificio está dada por mayor número de piso entre sus departamentos.

Y dadas las colecciones

```scala
val casas = List(
    new Casa("Calle falsa 1234", 5),
    new Casa("Lalala 23", 2),
    new Casa("Chiquita 44", 1),
    new Casa("Mediana 98", 3)
)

val edificios = List( 
    new Edificio(List( new Departamento(dir="Calle falsa 1111", piso=1, numero=1, cantidadAmbientes=3)))
) // Completar con casos representativos 

```

Obtener:

 - La cantidad de casas con más de 2 ambientes
 - Las casas con un ambiente
 - La cantidad de edificios con más de 10 departamentos
 - Todos los departamentos
 - Las direcciones de todos los departamentos de un edificio
 - El edificio con el departamento con más ambientes (si hay varios con la misma cantidad basta con obtener uno de ellos)
 - Los edificios con más de 3 pisos
 - Todos los departamentos que son monoambientes.
 - La cantidad total de departamentos
 - Las direcciones de los departamentos de más de un ambiente que se encuentran en edificios de menos de 3 pisos
 - Los edificios con departamentos que tengan cantidad de ambientes par, ordenados de mayor a menor según cantidad de pisos.

