📚 Web Scraping de Books to Scrape

Este proyecto realiza web scraping sobre Books to Scrape
 para obtener información de libros (título, precio, rating y categoría).
Luego, con la Google Books API, se buscan los autores y se guardan todos los datos en una base de datos SQLite.

⚙️ Tecnologías

```- Python 3
- BeautifulSoup4
- Requests
- Pandas
- SQLite3
- Google Books API
```

🗂️ Estructura del proyecto
```
📁 proyecto_libros/
│
├── books_scraping.ipynb   # Notebook principal del proyecto
├── books.db                # Base de datos SQLite con los libros y autores
├── .env                    # Archivo con la API Key
└── README.md               # Este archivo
```

🔐 Variables de entorno
Crea un archivo .env con tu clave de Google Books API:
```
API_KEY=tu_clave_aqui
```

🧠 Flujo del proyecto
```
1. Se realiza scraping del sitio Books to Scrape para obtener todas las categorías y libros.
2. Se limpian y formatean los datos (precios, ratings, etc.).
3. Se buscan los autores mediante la Google Books API.
4. Se guardan los datos en una base de datos SQLite, con tres tablas:
  - Libros
  - Autores
  - Libros_Autores (tabla intermedia para relaciones muchos a muchos)
5. Se realizan consultas SQL y pruebas con índices para optimizar búsquedas.
```

🧾 Ejemplo de consulta SQL
```
SELECT L.titulo, A.nombre AS autor, L.precio
FROM Libros L
JOIN Libros_Autores LA ON L.id = LA.libro_id
JOIN Autores A ON A.id = LA.autor_id
WHERE L.precio < 25 AND L.rating >= 3
ORDER BY L.precio ASC;
```

🚀 Ejecución

- Abrí el archivo .ipynb en Jupyter Notebook o VS Code.
- Ejecutá las celdas en orden.
- Verificá los resultados en la base de datos o con las consultas SQL.
