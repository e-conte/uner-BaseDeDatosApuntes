```mermaid
erDiagram
    VEHICULO ||--o{ CLIENTE : compra
    VEHICULO {
        VARCHAR matricula PK
        VARCHAR marca
        VARCHAR modelo
        VARCHAR color
        DECIMAL precio_venta
    }
    CLIENTE {
        VARCHAR dni PK
        VARCHAR nombre
        VARCHAR direccion
        VARCHAR ciudad
        VARCHAR numero_telefono
        INT codigo_interno
    }
    REVISION ||--|{ VEHICULO : revisa
    REVISION {
        INT codigo_unico PK
        DATE fecha
        BOOLEAN cambio_filtro_aceite
    }
