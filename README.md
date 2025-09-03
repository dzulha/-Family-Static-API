# Family API con Flask

Este proyecto es una API RESTful simple desarrollada en Python utilizando el micro-framework Flask. Permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) para gestionar los miembros de una familia ficticia. La API no utiliza una base de datos persistente; en su lugar, gestiona los datos en memoria durante el tiempo de ejecución del programa.

Este proyecto fue desarrollado como parte de mi bootcamp de desarrollo Full-Stack para demostrar mis habilidades en la creación de APIs, manejo de rutas, y lógica de backend en Python.

---

## ✨ Características Principales

* **Obtener todos los miembros**: Endpoint para recuperar la lista completa de miembros de la familia.
* **Obtener un miembro**: Endpoint para recuperar un miembro específico utilizando su `ID`.
* **Añadir un miembro**: Endpoint para agregar un nuevo miembro a la familia.
* **Eliminar un miembro**: Endpoint para borrar un miembro existente a través de su `ID`.

---

## 🛠️ Tecnologías Utilizadas

* **Backend**: Python, Flask
* **Gestor de Paquetes y Entorno**: Pipenv
* **Testing**: Pytest

-

## 📖 Uso de la API (Endpoints)

A continuación se detallan los endpoints disponibles y cómo interactuar con ellos.

### 1. Obtener todos los miembros
Recupera una lista de todos los miembros de la familia.

* **Método:** `GET`
* **URL:** `/members`
* **Respuesta Exitosa (Código `200`):**
    ```json
    [
        {
            "id": 1,
            "first_name": "John",
            "last_name": "Jackson",
            "age": 33,
            "lucky_numbers": [7, 13, 22]
        },
        {
            "id": 2,
            "first_name": "Jane",
            "last_name": "Jackson",
            "age": 35,
            "lucky_numbers": [10, 14, 3]
        }
    ]
    ```

### 2. Obtener un miembro por ID
Recupera la información de un solo miembro de la familia.

* **Método:** `GET`
* **URL:** `/members/<int:member_id>`
* **Respuesta Exitosa (Código `200`):**
    ```json
    {
        "id": 1,
        "first_name": "John",
        "last_name": "Jackson",
        "age": 33,
        "lucky_numbers": [7, 13, 22]
    }
    ```

### 3. Agregar un nuevo miembro
Crea y añade un nuevo miembro a la familia.

* **Método:** `POST`
* **URL:** `/members`
* **Cuerpo de la Petición (Body):**
    ```json
    {
        "first_name": "Tommy",
        "age": 23,
        "lucky_numbers": [1, 2, 3]
    }
    ```
* **Respuesta Exitosa (Código `200`):**
    ```json
    {
        "id": 4,
        "first_name": "Tommy",
        "last_name": "Jackson",
        "age": 23,
        "lucky_numbers": [1, 2, 3]
    }
    ```

### 4. Eliminar un miembro
Elimina un miembro de la familia utilizando su ID.

* **Método:** `DELETE`
* **URL:** `/members/<int:member_id>`
* **Respuesta Exitosa (Código `200`):**
    ```json
    {
        "done": true
    }
    ```

---

## ✅ Pruebas (Testing)

El proyecto incluye un conjunto de pruebas automatizadas para asegurar el correcto funcionamiento de cada endpoint. Para ejecutarlas, utiliza el siguiente comando:

```bash
pipenv run test
