# QueriesSQL - Plataforma de Alquiler

## Objetivo del proyecto:

Crear una base de datos para una plataforma de alquiler de habitaciones, que permita gestionar información sobre las propiedades, usuarios y alquileres, con la finalidad de aprender y profundizar en la creación de bases de datos y en la realización de consultas SQL.


## 1. Creación de la base de datos:

```sql
 CREATE DATABASE "QueriesSQL-plataforma-de-alquiler-de-habitaciones"
    WITH
    OWNER = postgres
    ENCODING = 'UTF8'
    LOCALE_PROVIDER = 'libc'
    CONNECTION LIMIT = -1
    IS_TEMPLATE = False;
```

## 2. Creación de la tabla USER:

```sql
CREATE TABLE "USER"
(
    id_user serial NOT NULL,
    num_docu_user character varying(30) NOT NULL,
    type_docu_user character varying(20) NOT NULL,
    name_user character varying(100) NOT NULL,
    lastname_user character varying(100) NOT NULL,
    birthyear_user integer NOT NULL,
    gender_user character varying(20) NOT NULL,
    mail_user character varying(150) NOT NULL,
    phone_user character varying(20),
    country_resi_user integer,
    status_user boolean NOT NULL,
    CONSTRAINT user_pkey PRIMARY KEY (id_user),
    CONSTRAINT user_mail_user_key UNIQUE (mail_user)
);

```
## 3. Creación de la tabla de ROLE_USER:

```sql
CREATE TABLE "ROLE_USER"
(
    id_user_roleuser integer NOT NULL,
    id_role_roleuser integer NOT NULL,
    CONSTRAINT role_user_pkey PRIMARY KEY (id_user_roleuser,id_role_roleuser)
);
```

## 4. Creación de la tabla ROLE:

```sql
CREATE TABLE "ROLE"
(
    id_role serial NOT NULL,
    name_role character varying(20) NOT NULL,
    CONSTRAINT role_pkey PRIMARY KEY (id_role)
);
```

## 5.