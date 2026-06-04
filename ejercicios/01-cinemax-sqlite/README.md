# Ejercicio 01: Diseno e Implementacion de una Base de Datos para CineMax con SQLite

## Objetivo

Disenar, modelar e implementar una base de datos relacional utilizando SQLite para gestionar informacion basica de un cine.

Al finalizar, el estudiante debe demostrar que puede:

- Analizar un contexto de negocio.
- Identificar entidades, atributos y relaciones.
- Definir llaves primarias y foraneas.
- Aplicar restricciones de integridad.
- Crear tablas con DDL.
- Insertar datos con DML.
- Consultar informacion con DQL.
- Documentar evidencias tecnicas.

## Contexto

La empresa **CineMax** desea desarrollar un sistema sencillo para administrar la informacion relacionada con sus peliculas, salas de proyeccion, funciones y boletos vendidos.

Actualmente la informacion se registra manualmente, lo que dificulta:

- Consultar cuantas funciones existen.
- Saber que peliculas se proyectan.
- Conocer cuantos boletos se han vendido.
- Identificar cuales son las salas mas utilizadas.

La empresa requiere una base de datos que permita almacenar esta informacion de forma organizada, consistente y consultable.

Como analista de bases de datos, debe disenar el modelo de datos adecuado para resolver esta necesidad.

## Requerimientos

A partir del contexto anterior, identifique:

- Entidades necesarias.
- Atributos de cada entidad.
- Relaciones entre entidades.
- Llaves primarias.
- Llaves foraneas.
- Restricciones de integridad apropiadas.

La solucion debe contener **maximo 4 tablas**.

## Estructura de trabajo

Use la plantilla incluida en este ejercicio:

```text
plantilla/
├── diagramas/
│   └── .gitkeep
├── ddl/
│   └── schema.sql
├── dml/
│   └── inserts.sql
└── dql/
    └── consultas.sql
```

Para empezar su solucion:

```bash
cp -R ejercicios/01-cinemax-sqlite/plantilla resoluciones/01-cinemax-sqlite-apellido-nombre
```

Reemplace `apellido-nombre` por sus datos.

## Parte 1: Diseno del Modelo de Datos

Construya un diagrama UML E-R que represente la solucion propuesta.

El diagrama debe incluir:

- Entidades.
- Atributos.
- Llaves primarias.
- Llaves foraneas.
- Relaciones.
- Cardinalidades.

### Entregable

```text
diagramas/
└── diagrama-er.png
```

Tambien puede incluir un archivo fuente del diagrama si la herramienta lo genera, por ejemplo `diagrama-er.drawio`.

## Parte 2: Implementacion en SQLite con DDL

Implemente el modelo disenado utilizando SQLite.

Las tablas deben incluir obligatoriamente:

| Restriccion | Descripcion |
|-------------|-------------|
| `PRIMARY KEY` | Identificador unico de cada registro |
| `FOREIGN KEY` | Referencia a otra tabla |
| `NOT NULL` | El campo no puede estar vacio |
| `UNIQUE` | El valor no puede repetirse |
| `CHECK` | Validacion de valores permitidos |

Active las llaves foraneas cuando ejecute sus scripts:

```sql
PRAGMA foreign_keys = ON;
```

### Entregable

```text
ddl/
└── schema.sql
```

## Parte 3: Insercion de Datos con DML

Registre informacion de prueba para validar el funcionamiento de la base de datos.

### Requisitos de insercion

Inserte al menos:

- 5 peliculas.
- 5 salas.
- 8 funciones.
- 10 boletos.

### Casos de prueba

Incluya al menos:

- 2 inserciones validas.
- 2 inserciones que generen error por restricciones, por ejemplo:
  - Violacion de `UNIQUE`.
  - Violacion de `CHECK`.
  - Violacion de `FOREIGN KEY`.

Las inserciones que generan error deben estar comentadas o separadas en una seccion identificada para que el docente pueda probarlas manualmente sin romper la ejecucion principal.

### Entregable

```text
dml/
└── inserts.sql
```

## Parte 4: Consultas con DQL

Realice las siguientes consultas utilizando unicamente las tablas de su base de datos.

| # | Consulta |
|---|----------|
| 1 | Mostrar todas las peliculas registradas con todos sus atributos. |
| 2 | Mostrar unicamente el nombre y la duracion de todas las peliculas. |
| 3 | Mostrar las peliculas cuya duracion sea superior a 120 minutos. |
| 4 | Mostrar las peliculas ordenadas alfabeticamente por nombre. |
| 5 | Mostrar las tres peliculas con mayor duracion. |
| 6 | Contar cuantas peliculas existen registradas. |
| 7 | Mostrar la duracion promedio de las peliculas. |
| 8 | Mostrar la pelicula con la mayor duracion. |
| 9 | Mostrar todas las funciones programadas despues de una fecha especifica definida por usted. |
| 10 | Contar cuantas funciones existen para cada sala utilizando `GROUP BY`. |

### Entregable

```text
dql/
└── consultas.sql
```

## README de la resolucion

Dentro de su carpeta de resolucion agregue un `README.md` con estas secciones:

### 1. Informacion General

- Nombre del proyecto.
- Nombre del camper.
- Grupo o ruta.
- Fecha de entrega.

### 2. Descripcion del Problema

- Que necesidad tiene la empresa CineMax.
- Como la base de datos propuesta ayuda a resolverla.

### 3. Modelo de Datos

- Imagen del diagrama UML E-R.
- Descripcion de las entidades identificadas.
- Explicacion de las relaciones.

### 4. Restricciones Implementadas

- Llaves primarias.
- Llaves foraneas.
- Restricciones `NOT NULL`.
- Restricciones `UNIQUE`.
- Restricciones `CHECK`.

### 5. Evidencias

Agregue capturas o salidas donde se evidencie:

- Creacion de las tablas.
- Insercion de registros.
- Ejecucion de las consultas solicitadas.
- Ejemplos de errores producidos por restricciones.

## Como ejecutar

Desde la carpeta de su resolucion:

```bash
sqlite3 cinemax.db < ddl/schema.sql
sqlite3 cinemax.db < dml/inserts.sql
sqlite3 cinemax.db < dql/consultas.sql
```

Si necesita entrar a la consola interactiva:

```bash
sqlite3 cinemax.db
```

Comandos utiles dentro de SQLite:

```sql
.tables
.schema
.headers on
.mode column
```

## Criterios de evaluacion

| Criterio | Peso sugerido |
|----------|---------------|
| Modelo E-R coherente | 25% |
| DDL con restricciones correctas | 25% |
| Datos de prueba suficientes | 20% |
| Consultas correctas | 20% |
| Documentacion y evidencias | 10% |

## Consideraciones

- El modelo debe ser disenado por usted a partir del enunciado.
- No copie un modelo existente de internet.
- Se evaluara la coherencia del diseno realizado.
- No es obligatorio utilizar `JOIN` en las consultas, aunque puede hacerlo si lo considera necesario.
- Todas las consultas deben ejecutarse correctamente sobre los datos registrados.
- La solucion principal no debe depender de datos cargados manualmente desde la consola.

