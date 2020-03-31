## Fundamentos de Bases de Datos NoSQL

Las BBDD NoSQL son tecnologías de base de datos que pretenden abordar el problema de la escalabilidad en bases de datos relacionales, causada por las características de los datos masivos: **Volumen, Velocidad y Variedad**.

ACID vs BASE:

* Las Bases de Datos Relacionales son **ACID**:
    - Atomicidad: Indica que las transacciones de la base de datos o bien se ejecutan por completo, o bien no se ejecutan en absoluto. No es posible que una transacción se ejecute parcialmente.
    - Consistencia: Los datos almacenados no pueden violar las restricciones de integridad de la base de datos.
    - Aislamiento (Isolation): Múltiples transacciones ejecutándose concurrentemente no interfieren entre ellas.
    - Durabilidad: Las transacciones finalizadas persistirán incluso en el caso de fallos del sistema.

* Las Bases de Datos No Relacionales son **BASE**:
    - Basic Available: La base de datos está básicamente disponible la mayor parte del tiempo, es decir, aunque algunos nodos fallen en un momento determinado, la base de datos seguirá funcionando.
    - Soft-state: Significa que el estado del sistema no se puede garantizar, es decir, que el mismo dato puede tener múltiples valores en diferentes partes del sistema.
    - Eventual Consistency: Consistencia eventual implica que aunque la base de datos no esté en el mismo estado todo el tiempo, pasado el suficiente tiempo, llegará a un estado consistente.

### Teorema de CAP

Teorema de CAP: Un sistema distribuido debe idealmente proporcionar las siguientes características:

* Consistency (Consistencia): Datos Con Sentido
* Availability (Disponibilidad):
* Partition Tolerance (Tolerancia a Particiones): 
    - Cómo segmentas la información cuando hay información demasiado grandes.

> Es imposible tener las 3 al mismo tiempo


[CA]: Bases de Datos Relacionales
[CP]: Bases de Datos No Relacionales
[AP]: Bases de Datos No Relacionales

Ejemplo:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Yaq8AHlFA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Modelo de Datos

Tipos de Modelo de Datos NoSQL:

- Key-Value
    - Almacenamiento:
        - Almacenan datos en la forma de un par clave-valor, donde la clave es un identificador único y el valor contiene el dato que se desea almacenar.
    - Características:
        - Normalmente [AP]
        - El dato puede ser de una gran variedad de formatos, como por ejemplo, JSON, vídeo, audio
        - Consultas sencillas.
        - Modelado de datos flexible.
        - Altas prestaciones y alta disponibilidad.
        - Escalabilidad.
        - Portabilidad y bajos costes operacionales.
    - Adecuada:
        - Información de sesión en aplicaciones web.
        - Carritos de la compra.
    - No Adecuada:
        - Se necesitan búsquedas en los valores.
        - Los datos se encuentran interconectados.

- Column Stores:
    - Adecuadas para consultas de agregación.
    - Almacenamiento:
        - Almacenan datos de forma tabular, pero organizando los datos en forma de columnas.
        - Es altamente escalable y de muy altas prestaciones.
    - Características:
        - Consultas de agregación muy rápidas en comparación con bases de datos orientadas a filas.
        - Mejor compresión.
        - Si se necesitan múltiples columnas de cada fila, sus prestaciones caen.
        - Las escrituras requieren más tiempo ya que hay que escribir cada columna independientemente.

- Document Stores
    - Adecuadas para consultas basadas en valores.
    - Almacenamiento:
        - Almacenan datos semi-estructurados, como JSON, XML, BSON. Cada documento puede tener una estructura diferente al resto.
    - Características:
        - Modelado de datos flexible.
        - Escrituras rápidas.
        - Lecturas rápidas.
    - Adecuada:
        - Realizar búsquedas basadas en el valor.
        - CMS, blogs...
    - No Adecuada:
        - Aplicaciones que requieran consultas complejas.

- Graph Stores
    - Adecuadas para datos altamente relacionados.
    - Almacenamiento:
        - Proporcionan una representación eficiente de los datos donde los registros tienen relaciones entre ellos.
        - Aprovechan algoritmos optimizados para buscar en estructuras de datos basados en grafos.
        - Estas bases de datos pueden localizar información de forma diferente a otras propuestas NoSQL.
        - En estas estructuras, de datos la información y sus propiedades se representan como aristas y nodos.
    - Características:
        - Altas prestaciones.
        - Flexibilidad.
    - Adecuada:
        - Sistemas de recomendación.

### Modelo de Distribución

Cómo se gestionan los datos en el cluster:

* Replicación maestro-esclavo
    - Principalmente lecturas
    - Lecturas tolerantes a fallos
    - Problema: inconsitencia
* Sharding
    - Los datos se distribuyen entre los nodos del sistema.
    - Cada dato está en un nodo.
    - La asignación de datos a nodos puede ser manual o automática.
    - No mejora la tolerancia a fallos
* Replicación peer-to-peer:
    - Todos los nodos leen y escriben todos los datos.
    - Tolerancia fallos de cualquier nodo.
* Combinación de replicación y sharding

### Indexación

Los índices en una base de datos mejoran el acceso de lectura a los datos, a expensas de empeorar en las escrituras.
Las estructuras de datos que se utilizan en los índices en bases de datos NoSQL son similares a las utilizadas en bases de datos relacionales.
