# QueriesSQL - Plataforma de Alquiler

## Objetivo del proyecto:

Crear una base de datos para una plataforma de alquiler de habitaciones, que permita gestionar información sobre las propiedades, usuarios y alquileres, con la finalidad de aprender y profundizar en la creación de bases de datos y en la realización de consultas SQL.


## 1. Creación de la base de datos:

```sql
 CREATE DATABASE "Queries SQL - plataforma de alquiler de habitaciones"
    WITH
    OWNER = postgres
    ENCODING = 'UTF8'
    LOCALE_PROVIDER = 'libc'
    CONNECTION LIMIT = -1
    IS_TEMPLATE = False;
```

## 2. Creación de las tablas de usuario:

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
