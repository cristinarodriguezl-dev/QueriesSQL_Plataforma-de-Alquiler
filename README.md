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

## 5. Creación de la tabla COUNTRY:

```sql
CREATE TABLE "COUNTRY"
(
    id_contry serial NOT NULL,
    name_country character varying(100) NOT NULL,
    CONSTRAINT country_pkey PRIMARY KEY (id_contry)
);
```

## 6. Creación de la tabla PREFERENCE:

```sql
CREATE TABLE "PREFERENCE"
(
    id_user_pref integer NOT NULL,
    pet_owner_pref boolean,
    smoke_pref boolean,
    aircon_pref boolean,
    wifi_pref boolean,
    bath_pref boolean,
    closet_pref boolean,
    kitchen_pref boolean,
    balcony_pref boolean,
    visit_allow_pref boolean,
    utilities_incl_pref boolean,
    CONSTRAINT preference_pkey PRIMARY KEY (id_user_pref)
);
```

## 7. Creación de la tabla TOWN:

```sql
CREATE TABLE "TOWN"
(
    id_town serial NOT NULL,
    name_town character varying(100) NOT NULL,
    province_town character varying(100) NOT NULL,
    CONSTRAINT town_pkey PRIMARY KEY (id_town)
);
```

## 8. Creación de la tabla NEIGHBORHOOD:

```sql
CREATE TABLE "NEIRBORHOOD"
(
    id_neirbor serial NOT NULL,
    id_town_neibor integer NOT NULL,
    name_neibor character varying(100) NOT NULL,
    CONSTRAINT neirborhood_pkey PRIMARY KEY (id_neirbor)
);
```

## 9. Creación de la tabla EDU_CENTER:

```sql
CREATE TABLE "EDU_CENTER"
(
    id_edu serial NOT NULL,
    town_edu integer NOT NULL,
    name_edu character varying(150) NOT NULL,
    address_edu character varying(200) NOT NULL,
    type_edu character varying(50) NOT NULL,
    CONSTRAINT edu_center_pkey PRIMARY KEY (id_edu)
);
```

## 10. Creación de la tabla ENROLLMENT:

```sql
CREATE TABLE "ENROLLMENT"
(
    id_enroll serial NOT NULL,
    id_user_enroll integer NOT NULL,
    id_educenter_enroll integer NOT NULL,
    attach_enroll character varying(255),
    exp_date_enroll date,
    CONSTRAINT enrollment_pkey PRIMARY KEY (id_enroll)
);
```

## 11. Creación de la tabla ROOM:

```sql
CREATE TABLE "ROOM"
(
    id_room serial NOT NULL,
    id_owner_room integer NOT NULL,
    address_room character varying(200) NOT NULL,
    postal_room character varying(20) NOT NULL,
    floor_room character varying(10),
    town_room integer NOT NULL,
    neibor_room integer,
    size_room numeric(6,2),
    bed_qty_room integer,
    capacity_room integer,
    gender_allow_room character varying(20),
    closet_room boolean,
    bath_room boolean,
    balcony_room boolean,
    aircon_room boolean,
    wifi_room boolean,
    kitchen_allow_room boolean,
    visit_allow_room boolean,
    smoke_room boolean,
    pet_room boolean,
    utilities_incl_room boolean,
    status_room boolean NOT NULL,
    CONSTRAINT room_pkey PRIMARY KEY (id_room)
);
```
