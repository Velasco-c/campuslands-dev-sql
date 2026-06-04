# Campuslands Dev SQL

Repositorio de ejercicios de SQL para practicar diseno, creacion, insercion y consulta de bases de datos relacionales.

Este repositorio esta preparado para crecer por modulos. Cada ejercicio vive en `ejercicios/` y las entregas o soluciones de trabajo viven en `resoluciones/`.

## Objetivo

Fortalecer las habilidades necesarias para:

- Analizar requerimientos de una base de datos.
- Identificar entidades, atributos, relaciones y restricciones.
- Crear modelos relacionales con llaves primarias y foraneas.
- Implementar estructuras con SQL.
- Insertar datos de prueba.
- Ejecutar consultas usando DQL.
- Documentar evidencias tecnicas de forma clara.

## Flujo de trabajo con Git

El repositorio tiene dos ramas principales protegidas:

- `main`: rama estable. No se trabaja directamente sobre esta rama.
- `dev`: rama base de desarrollo. Los ejercicios nuevos y las soluciones deben partir desde esta rama.

Regla de trabajo:

1. Cambiarse siempre a `dev` antes de modificar archivos.
2. Crear una rama por ejercicio, estudiante o ajuste.
3. Hacer commits pequenos y descriptivos.
4. Integrar los cambios hacia `dev`.
5. Promover a `main` solo cuando el instructor lo indique.

Ejemplo:

```bash
git switch dev
git switch -c ejercicio/01-apellido-nombre
```

El repositorio incluye un hook local en `.githooks/pre-commit` para bloquear commits directos en `main`, `master` o `dev`. Para activarlo despues de clonar:

```bash
git config core.hooksPath .githooks
```

## Estructura

```text
campuslands-dev-sql/
├── README.md
├── CONTRIBUTING.md
├── ejercicios/
│   ├── README.md
│   └── 01-cinemax-sqlite/
│       ├── README.md
│       └── plantilla/
│           ├── diagramas/
│           │   └── .gitkeep
│           ├── ddl/
│           │   └── schema.sql
│           ├── dml/
│           │   └── inserts.sql
│           └── dql/
│               └── consultas.sql
└── resoluciones/
    └── README.md
```

## Como trabajar un ejercicio

1. Cambiese a `dev`.
2. Cree una rama nueva desde `dev`.
3. Lea completamente el enunciado en `ejercicios/<numero>-<nombre>/README.md`.
4. Copie la carpeta `plantilla/` dentro de `resoluciones/` usando su nombre o grupo.
5. Complete los archivos solicitados.
6. Ejecute los scripts SQL en SQLite.
7. Documente capturas o evidencias cuando el ejercicio lo pida.

Ejemplo:

```bash
cp -R ejercicios/01-cinemax-sqlite/plantilla resoluciones/01-cinemax-sqlite-apellido-nombre
```

## Requisitos recomendados

- Git
- SQLite 3
- Extensiones opcionales para visualizar bases de datos SQLite
- Herramienta para diagramas E-R, por ejemplo Draw.io, Lucidchart, Mermaid o similar

## Convenciones

- Los nombres de carpetas deben ir en minuscula y con guiones.
- Los archivos SQL deben terminar en `.sql`.
- Las soluciones deben poder ejecutarse desde cero en una base de datos vacia.
- No se deben subir archivos generados innecesarios como bases de datos locales, caches o capturas temporales.
