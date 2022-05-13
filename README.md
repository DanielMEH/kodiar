# kodiar
aplicación para el manejo de inventarios en las tiendas de barrio en armenia

create database empresa;
use empresa;


create table empleado(
id_empleado bigint not null primary key,
nombre varchar(50),
apellidos varchar(50),
telefono bigint,
estadoCivil varchar(30)
);

create table kidPuesto(
    id_puesto bigint,
    descripcion_puesto varchar(30),
    sueldo text,
    constraint FK_puesto_empleado FOREIGN KEY(id_puesto) REFERENCES empleado(id_empleado)
);
create table kidDepartamento(
    id_departamento bigint PRIMARY key,
    descripcion_departamento text,
    num_departamento text unique,
    nombre_departamento varchar(50),
    telefono_departament varchar(50),
    constraint FK_departament_puesto FOREIGN key(id_departamento) REFERENCES kidPuesto(id_puesto)
);

create table fkidArea(
    id_area bigint,
    descripcion_area text,
    nombre_area text,
    estado_area int(),
    constraint FK_departament_area FOREIGN key(id_area) REFERENCES kidDepartamento(id_departamento)
)
