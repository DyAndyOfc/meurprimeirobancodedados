# meurprimeirobancodedados
Projeto de banco de dados relacional com tabelas para cadastro de pessoas, empregos e escolas. Inclui criação, alteração, inserção, atualização e exclusão de dados com comandos SQL. Ideal para treinar operações CRUD e modelagem básica de dados.


create table MinhasInfomacoes(
cpf varchar(15),
nome varchar(30) not null,
sexo enum('M','F'),
nacimento date,
peso decimal (5, 2),
altura decimal(3, 2),
nacionalidade varchar(20)
);

alter table minhasinfomacoes
change column nacimento nascimento date;

desc minhasinfomacoes;

select * from minhasinfomacoes;

insert into minhasinfomacoes (cpf, nome, sexo, nascimento,peso, altura, nacionalidade)
value
('147-258-369-58', 'Alexandre', 'M', '1993-03-16', 82.30, 1.82, 'Brasil'),
('111-222-333-444-55', 'Ester', 'F', '1998-02-10', 100.8, 1.60, 'Brasil'),
(default, 'Emanuelle', 'F', '2020-05-17', 17.5, 1.10, 'Brasil');

delete from minhasinfomacoes
where nome = 'Alexandre'
limit 2;

update minhasinfomacoes
set cpf = '147-258-369-58',
    peso= 80.3,
    altura = 1.68
where cpf = '111-111-111-11'
limit 1;  

create table empregos(
id int auto_increment primary key,
nome varchar(100),
email varchar(100)
);

insert into empregos (id, nome, email)
value
('1', 'Amigao supermecado', 'amigaosueper2gmail.com'),
('2', 'tintasportugues', 'tintaportuga@gmail.com');

select * from empregos;

create table escola(
matricula int auto_increment primary key,
nome varchar(100),
email varchar(100)
);

insert into escola(matricula, nome, email)
value
('12548', 'cemi emilio pacheco', 'emiliopacheco@gmail.com');

select * from escola;
