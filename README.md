## Reto 2 - Modelado de un problema de la vida real a través de objetos y clases

El reto propuesto en clase fue el modelado de una situación de la vida real a través de relaciones entre objetos y clases, haciendo uso del conocimiento adquirido durante la sesión y diagramas tipo UML.
Como la situación a modelar era de libre elección opte por modelar a través de objetos y clases una tienda de televisores.

### Relación tienda de televisores - cliente
```mermaid
classDiagram
Cliente --> Tienda_de_televisores : Entrar (), Comprar () 

class Tienda_de_televisores {
    Dirección : str
    Inventario : str

    Abrir la tienda (Hora)
    Cerrar la tienda (Hora)
}

class Cliente {
    Nombre : string
    Edad : int
}
```

### Relación Tienda de televisores -  Televisor
``` mermaid
classDiagram

Televisor --* Tienda_de_televisores

class Tienda_de_televisores {
    Dirección : str
    Inventario : str

    Abrir la tienda (Hora)
    Cerrar la tienda (Hora)
}

class Televisor {
    Dimensiones : tuple
    Resolucion : tuple
    Marca : string
    Modelo : string
    Número de puertos USB : int
    Número de puertos HDMI : int
    Es smart : bool
    Precio : float
    
    Encendido ()
    Apagado ()
    Configuraciones ()
}
```

### Relación entre el personal de la tienda
```mermaid
classDiagram

Conserje --|> Personal
Empleado_de_pasillo --|> Personal
Gerente --|> Personal
Cajero --|> Personal
Especialista_en_almacen --|> Personal
Seguridad --|> Personal

class Personal {
    Horario laboral : string
    Cargo : string
    Uniforme : string
    Salario (cargo)
}

class Conserje {
    Equipo de herramientas : list
}

class Empleado_de_pasillo {
    Número de pasillo : int      
}

class Gerente {
    Organizar presupuestos ()
}

class Cajero {
    Número de ventas realizadas : int
}

class Especialista_en_almacen {
    Lista de pedidos de inventarios : dict
}

class Seguridad {
    Acceso total a las instalaciones: bool
}
```

### Relación tienda de televisores - personal
``` mermaid
classDiagram

Conserje --> Tienda_de_televisores : Limpiar (), Organizar ()
Empleado_de_pasillo --> Tienda_de_televisores : Informar clientes (), Guiar clientes ()
Gerente --> Tienda_de_televisores : Reponer_inventario ()
Cajero --> Tienda_de_televisores : Cobrar_cliente (precio)
Especialista_en_almacen --> Tienda_de_televisores : Revision de inventario (), Recibir productos para inventario ()
Seguridad --> Tienda_de_televisores : Supervizar (), Revisar ()

class Conserje {
    Equipo de herramientas : list
}

class Empleado_de_pasillo {
    Número de pasillo : int      
}

class Gerente {
    Organizar presupuestos ()
}

class Cajero {
    Número de ventas realizadas : int
}

class Especialista_en_almacen {
    Lista de pedidos de inventarios : dict
}

class Seguridad {
    Acceso total a las instalaciones: bool
}

class Tienda_de_televisores {
    Dirección : str
    Inventario : str

    Abrir la tienda (Hora)
    Cerrar la tienda (Hora)
}
```
