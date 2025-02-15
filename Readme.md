# API para los códigos postales de México
[![Code Climate](https://codeclimate.com/github/Munett/API-Codigos-Postales/badges/gpa.svg)](https://codeclimate.com/github/Munett/API-Codigos-Postales)

Dado un código postal, regresa un arreglo con las colonia, municipio y estado perteneciente al código postal.
Además se pueden realizar búsquedas de códigos postales usando los números iniciales.

### Ejemplos de uso

#### Liga a la API

[https://api-codigos-postales.herokuapp.com](https://api-codigos-postales.herokuapp.com)


**Consultar la información de un código postal**

```text
https://api-codigos-postales.herokuapp.com/v2/codigo_postal/66436
```

**Respuesta del servidor**
```json
{
  "codigo_postal": "66436",
  "municipio": "San Nicolás de los Garza",
  "estado": "Nuevo León",
  "colonias": [
    "Praderas de Santo Domingo",
    "Las Nuevas Puente"
  ]
}
```

---

**Buscar códigos postales**

```text
 https://api-codigos-postales.herokuapp.com/v2/buscar
```

_parametros necesarios_
```text
  codigo_postal=# codigo a buscar, parcial o total
```
_Ejemplo de busqueda para códigos que inicien con **66**, con **664** y con **6641**_
```json
https://api-codigos-postales.herokuapp.com/v2/buscar?codigo_postal=66
https://api-codigos-postales.herokuapp.com/v2/buscar?codigo_postal=664
https://api-codigos-postales.herokuapp.com/v2/buscar?codigo_postal=6641
```

** Para el codigo postal 6641 el servidor regresa **
```json
{
  "codigos_postales": [
    "66410",
    "66412",
    "66413",
    "66414",
    "66415",
    "66417",
    "66418"
  ]
}
```

___


### Instalación

Para instalar con Docker y Docker Compose:

```sh
$ docker-compose up
# Aplicación en: http://localhost:3000
```

### Rake task
Ejecuta el rake task `rake sepomex:update` para descargar todos los códigos postales de méxico y actualizar tu base de datos.

### Colabora
Errores y pull requests son bienvenidos en Github: https://github.com/Munett/API-Codigos-Postales.
Para bajar en tu BD todos los códigos postales corre el rake script `rake sepomex:update`.

Los datos se obtuvieron de http://www.correosdemexico.gob.mx/lservicios/servicios/CodigoPostal_Exportar.aspx

### TODO
- [ ] Pruebas automatizadas minitest

### Los datos se actualizan cada domingo.

### Licencia
MIT License
