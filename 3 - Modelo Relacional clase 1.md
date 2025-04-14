# Material de Estudio: Normalización en Bases de Datos

## Clase 4 - Diseño Lógico y Formas Normales

### Introducción
En esta clase se abordó el proceso de normalización en bases de datos relacionales, enfocándose en las formas normales y su aplicación para eliminar redundancias y anomalías en los datos. A continuación, se presenta un resumen estructurado de los temas discutidos.

---

## 1. **Diseño Lógico y Normalización**
El diseño lógico es una etapa crucial en el desarrollo de bases de datos, donde se transforma el esquema conceptual (diagramas entidad-relación) en un esquema lógico basado en tablas. Este proceso es iterativo y busca optimizar la estructura de los datos para garantizar:
- **Eliminación de redundancias.**
- **Recuperación eficiente de información.**
- **Adaptabilidad a cambios futuros.**

### Proceso Iterativo
- **Refinamiento continuo:** El diseño conceptual y lógico puede depurarse y mejorarse en cualquier momento.
- **Normalización:** Técnica clave para lograr un esquema robusto y libre de inconsistencias.

---

## 2. **Formas Normales**
Las formas normales son reglas que definen cómo organizar los datos para minimizar problemas como redundancias y anomalías de actualización. A continuación, se detallan las principales formas normales:

### 2.1. **Primera Forma Normal (1FN)**
**Definición:**  
Una tabla está en 1FN si:
- Todos los atributos contienen valores atómicos (indivisibles).
- No hay grupos repetitivos.

**Ejemplo:**  
- **Tabla no normalizada:** `Producto(código, nombre, versión(numero, fecha, ventas))`.  
  - Problema: `versión` es un atributo compuesto.  
- **Solución:** Dividir en `Producto(código, nombre)` y `Versión(código_producto, numero, fecha, ventas)`.

---

### 2.2. **Segunda Forma Normal (2FN)**
**Definición:**  
Una tabla está en 2FN si:
- Está en 1FN.
- Todos los atributos no clave dependen completamente de la clave primaria.

**Ejemplo:**  
- **Tabla no normalizada:** `Inscripción(estudiante, actividad, precio)`.  
  - Problema: `precio` depende parcialmente de `actividad`, no de la clave completa.  
- **Solución:** Dividir en `Inscripción(estudiante, actividad)` y `Actividad(actividad, precio)`.

---

### 2.3. **Tercera Forma Normal (3FN)**
**Definición:**  
Una tabla está en 3FN si:
- Está en 2FN.
- No hay dependencias transitivas (atributos no clave que dependen de otros atributos no clave).

**Ejemplo:**  
- **Tabla no normalizada:** `Alquiler(inquilino, edificio, alquiler)`.  
  - Problema: `alquiler` depende de `edificio`, no directamente de la clave.  
- **Solución:** Dividir en `Alquiler(inquilino, edificio)` y `Edificio(edificio, alquiler)`.

---

### 2.4. **Forma Normal de Boyce-Codd (FNBC)**
**Definición:**  
Una tabla está en FNBC si:
- Todos los determinantes son claves candidatas.  
- Casos poco frecuentes en diseños tradicionales.

---

### 2.5. **Cuarta Forma Normal (4FN)**
**Definición:**  
Elimina dependencias multivaluadas no triviales.  
**Ejemplo:**  
- **Tabla no normalizada:** `Profesor(ID, especialidad, curso)`.  
  - Problema: Un profesor puede tener múltiples especialidades y cursos independientes.  
- **Solución:** Dividir en `Profesor_Especialidad(ID, especialidad)` y `Profesor_Curso(ID, curso)`.

---

### 2.6. **Quinta Forma Normal (5FN)**
**Definición:**  
Trata dependencias de reunión complejas, raramente aplicadas en la práctica.

---

## 3. **Ejercicio Práctico: Normalización**
**Enunciado:**  
Normalizar la tabla `Préstamo(num_socio, nombre_socio, fecha_préstamo, editorial, país, ISBN)`.

**Pasos:**  
1. **1FN:** Verificar atomicidad y eliminar grupos repetitivos.  
2. **2FN:** Separar `Socio(num_socio, nombre_socio)` y `Préstamo(num_socio, fecha_préstamo, ISBN)`.  
3. **3FN:** Crear `Libro(ISBN, editorial)` y `Editorial(editorial, país)` para eliminar dependencias transitivas.  

**Esquema final:**  
- `Socio(num_socio, nombre_socio)`  
- `Libro(ISBN, editorial)`  
- `Editorial(editorial, país)`  
- `Préstamo(num_socio, ISBN, fecha_préstamo)`  

---

## 4. **Consejos para Ejercicios Prácticos**
- **Ubicación de elementos:** En diagramas, asegurar que los círculos de atributos estén dentro de las entidades.  
- **Claves foráneas:** Identificarlas claramente al pasar de ER a tablas.  
- **Iterar:** Revisar dependencias funcionales en cada paso de normalización.  

---

## 5. **Próximos Temas**
- **Práctica:** Ejercicio en Draw.io para diseñar diagramas ER y pasaje a tablas.  
- **Parcial:** Revisar fechas en el campus virtual.  

**Material adicional:**  
- Presentación de normalización subida al campus.  
- Ejercicios resueltos para practicar.  

---

**Nota:** Para dudas, revisar las grabaciones o consultar en el foro del campus.  
