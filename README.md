create database paradas;
use paradas;

create table main(
  cd int primary key not null,
  nm varchar (110),
  nm_bairro varchar (110),
  ic_sexo char,
  dt_nasc date
);

insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (248554, 'GULIVER PERSIKE XAZAN', 'Centro', 'M','2019-06-12');
insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (156615, 'ANA BALAN VOADRH', 'Guarau', 'F', '2004-02-12');
insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (153315, 'ANA CAROLINA DOS ANJOS MENCHON', 'Capão Redondo', 'M', '2008-07-07');
insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (111122, 'VITOR ALEXANDRE NUNES', 'Veneza', 'M', '2011-11-11');
insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (111123, 'VITORIA ALEXANDRE NUNES', 'Veneza', 'F', '1982-02-02');

insert into main (cd, nm, nm_bairro, ic_sexo, dt_nasc) values (111124, 'VITORIA NUNES MUCKZ', 'Veneza', 'F', '2001-02-01');


create view vMeninas as
select nm from main where ic_sexo = 'F';

create view vMeninos as
select nm from main where ic_sexo = 'M';

alter view vMeninas as
select nm as nomeDaPessoa, dt_nasc as partoDeCria from main where ic_sexo = 'F';

alter view vMeninos as
select nm, nm_bairro from main where ic_sexo = 'M';

create view vMaiores as
select nm, ic_sexo from main where year (dt_nasc) <= 2004;

alter view vMaiores as
select nm, ic_sexo from main where year (dt_nasc) <= year (now());

select * from vMeninos;
select * from vMeninas;
select * from vMaiores; 

select year(now());
