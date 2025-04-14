```erDiagram
    CLIENTE ||--o{ AUTOMOVIL : adquiere
    CLIENTE {
        string DNI PK
        string nombre
        string direccion
        string ciudad
        string numero_telefono
        int codigo_interno
    }
    AUTOMOVIL {
        string matricula PK
        string marca
        string modelo
        string color
        float precio_venta
    }
    %% Cardinalities
    note right of CLIENTE: "1 Cliente can acquire 1 or more Automoviles (1:N)"
    note left of AUTOMOVIL: "1 Automovil is acquired by exactly 1 Cliente (1:1)"
```
