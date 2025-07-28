# Apuntes SQL

SQL (Structured Query Language) es el lenguaje estándar para interactuar con bases de datos relacionales, y sus funciones básicas giran en torno a cuatro acciones principales. Aquí te las explico de forma clara y estructurada:

---

### 🧩 Funciones Básicas de SQL

#### 1. **SELECT** – Consultar datos
- Recupera información específica de una o más tablas.
- Ejemplo:  
  ```sql
  SELECT nombre, edad FROM usuarios WHERE edad > 18;
  ```

#### 2. **INSERT** – Agregar datos
- Añade nuevas filas (registros) a una tabla.
- Ejemplo:  
  ```sql
  INSERT INTO usuarios (nombre, edad) VALUES ('Juan', 25);
  ```

#### 3. **UPDATE** – Modificar datos
- Cambia valores existentes en una tabla.
- Ejemplo:  
  ```sql
  UPDATE usuarios SET edad = 26 WHERE nombre = 'Juan';
  ```

#### 4. **DELETE** – Eliminar datos
- Borra filas según una condición.
- Ejemplo:  
  ```sql
  DELETE FROM usuarios WHERE edad < 18;
  ```

#### 5. **CREATE** – Crear tablas o bases de datos
- Define estructuras nuevas para almacenar datos.
- Ejemplo:  
  ```sql
  CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    nombre VARCHAR(50),
    edad INT
  );
  ```

---

# 3 funciones adicionales para nivel intermedio

Estos tres comandos llevan tus consultas SQL a otro nivel. Aquí te dejo una guía clara con ejemplos:



### 🔗 `JOIN` — Combinar tablas

Sirve para conectar datos entre dos o más tablas relacionadas por una columna en común.

**Ejemplo**: Supón que tienes dos tablas: `usuarios` y `compras`.

```sql
SELECT usuarios.nombre, compras.producto
FROM usuarios
JOIN compras ON usuarios.id = compras.usuario_id;
```

📌 Esto te muestra el nombre del usuario y el producto que compró, combinando ambas tablas por el `id` del usuario.

---

### 📊 `GROUP BY` — Agrupar datos

Permite agrupar filas que tienen valores comunes en columnas específicas, especialmente útil con funciones como `COUNT`, `SUM`, `AVG`.

**Ejemplo**: contar cuántos productos compró cada usuario.

```sql
SELECT usuario_id, COUNT(*) AS total_compras
FROM compras
GROUP BY usuario_id;
```

📌 Así sabes cuántas compras hizo cada usuario.

---

### 🔠 `ORDER BY` — Ordenar resultados

Organiza los resultados de tu consulta según una o varias columnas.

**Ejemplo**: ordenar usuarios por edad.

```sql
SELECT nombre, edad
FROM usuarios
ORDER BY edad DESC;
```

📌 El `DESC` ordena en forma descendente; si usas `ASC`, será ascendente.

---



