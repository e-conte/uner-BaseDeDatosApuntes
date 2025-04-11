# Clase de Base de Datos: Modelo Entidad-Relación

## Introducción al Diseño de Bases de Datos
- El diseño de bases de datos sigue una metodología, similar al desarrollo de software.
- Inicialmente, el desarrollo se hacía por prueba y error, pero hoy es imprescindible seguir metodologías estructuradas.
- **Objetivo**: Garantizar que se consideren todos los requerimientos funcionales y de información.

---

## Ciclo de Vida del Diseño de Bases de Datos
1. **Diseño Conceptual**:
   - Esquema inicial independiente del motor de base de datos.
   - Captura la realidad sin considerar aspectos físicos.
2. **Diseño Lógico**:
   - Transforma el modelo conceptual en un esquema lógico.
   - Elimina construcciones no representables en el modelo elegido (relacional, orientado a objetos, etc.).
3. **Diseño Físico**:
   - Elección del sistema de gestión de bases de datos (SQL Server, Oracle, etc.).
   - Implementación del esquema físico.

---

## Importancia del Modelado
- Un modelo de datos es una representación simplificada de un sistema real.
- Debe capturar tanto características estáticas (estructura) como dinámicas (operaciones).
- **Componentes de un modelo de datos**:
  - Objetos y sus relaciones.
  - Operaciones o lenguajes para representar dinámicas.
  - Restricciones sobre objetos, relaciones y operaciones.

---

## Modelo Entidad-Relación (ER)
- **Propósito**: Diseño conceptual de bases de datos relacionales.
- **Elementos principales**:
  - **Entidades**: Objetos reales o abstractos (ej: cliente, cuenta bancaria).
  - **Relaciones**: Asociaciones entre entidades (ej: "trabaja para").
  - **Atributos**: Propiedades de entidades o relaciones (ej: DNI, nombre).

### Representación Gráfica (Diagrama ER)
- **Entidades**: Rectángulos.
- **Relaciones**: Líneas con verbos (ej: "trabaja en").
- **Atributos**: Elipses.
  - **Atributo identificador**: Subrayado (ej: DNI para "cliente").
 
# Ejemplo de Diagrama Entidad-Relación (ER)

## Estructura básica
erDiagram
    CLIENTE ||--o{ PEDIDO : "realiza"
    CLIENTE {
        string DNI PK
        string nombre
        string teléfono
    }
    
    PEDIDO ||--|{ PRODUCTO : "contiene"
    PEDIDO {
        int id_Pedido PK
        date fecha
    }

    PRODUCTO {
        int codigo PK
        string nombre
        float precio
    }

---

## Pasos para el Diseño Conceptual
1. Identificar entidades a partir de requerimientos.
2. Identificar relaciones entre entidades.
3. Asociar atributos a entidades o relaciones.
4. Definir dominios de atributos (ej: numérico, texto).
5. Determinar identificadores (claves primarias).
6. Dibujar el diagrama ER y validarlo con el usuario.

---

## Cardinalidad y Opcionalidad
- **Cardinalidad**: Indica cuántas instancias de una entidad se relacionan con otra.
  - Tipos: 1:1, 1:N, N:1, N:M.
- **Opcionalidad**: Indica si la participación es obligatoria (1) u opcional (0).
- **Ejemplo**:
  - "Un empleado trabaja en un departamento" → Cardinalidad 1:N (un empleado en un departamento, un departamento con muchos empleados).

---

## Ejemplo Práctico: Diagrama ER
**Enunciado**: Diseñar una base de datos para empleados, departamentos y proyectos.
- **Entidades**:
  - Empleado (DNI, nombre, dirección).
  - Departamento (número, nombre, ubicación).
  - Proyecto (número, nombre, ubicación).
- **Relaciones**:
  - Empleado **trabaja para** Departamento (1:N).
  - Empleado **trabaja en** Proyecto (N:M).
  - Empleado **administra** Departamento (1:1).

**Herramienta**: [draw.io](https://draw.io) para crear diagramas ER.

---

## Consideraciones Finales
- Un buen diseño evita redundancia, mejora el desempeño y garantiza integridad.
- Errores en el modelo conceptual afectan la calidad del software.
- **Práctica recomendada**: Usar nombres significativos para entidades, relaciones y atributos.

---

### Tarea Práctica
- Realizar un diagrama ER basado en un enunciado.
- Responder preguntas teóricas sobre el modelo ER.
- **Fecha de entrega**: Viernes a las 23:59.

---

**Recursos**:
- Libros: "Derrames" (Capítulos 3 y 4), "Silverchat" (Capítulo 6).
- Herramientas: draw.io para diagramas.
- Grabación de la clase disponible en Drive (en 1-2 días).
