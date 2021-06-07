# MOEMVC

Disciplina de Engenharia de Software - UFG

Prof. Cássio Leonardo

Estudantes: Paulo Paz e Cinara Gomes

Instruções:

1 - instalar WAMP SERVER
    https://sourceforge.net/projects/wampserver/
    
2 - instalar codeigniter versão 4
    https://github.com/codeigniter4/framework/archive/v4.1.1.zip
    
3 - Pastas MVC devem ser copiadas para o respectivo local no "www" conforme manual de instalação do codeigniter versão 4

4 - Executar o seguinte script para criação do banco de dados

    CREATE DATABASE MOE;
    USE MOE;
    CREATE TABLE ESTAGIARIO
    (
      id_estagiario INT AUTO_INCREMENT,
      email VARCHAR(60),
        senha VARCHAR(32),
        nome_estagiario VARCHAR(60),
        curso_estagiario VARCHAR(60),
        ano_ingresso_estagiario DATE,
        minicurriculo_estagiario VARCHAR(220),
        status_esta varchar(1),
        CONSTRAINT ESTAGIARIO_PKEY PRIMARY KEY (id_estagiario)
    );

    CREATE TABLE EMPREGADOR
    (
      id_empregador INT AUTO_INCREMENT,
        email VARCHAR(60),
        senha VARCHAR(220),
        nome_empresa VARCHAR(60),
        endereco_empresa VARCHAR(60),
        pessoa_de_contato VARCHAR(60),
        descricao_empresa VARCHAR(220),
        produtos_empresa VARCHAR(220),
        status_emp varchar(1),
        CONSTRAINT EMPREGADOR PRIMARY KEY (ID_EMPREGADOR)
    );

    CREATE TABLE COORDENADOR
    (
      id_coordenador INT AUTO_INCREMENT,
        email varchar(60),
        senha varchar(60),
        nome_coordenador varchar(60),
        remuneracao decimal(10,2),
        CONSTRAINT coodernador_pkey PRIMARY KEY (id_coordenador)
    );
    INSERT INTO COORDENADOR (email,senha,nome_coordenador,remuneracao) VALUES ('coordernador.moe@gmail.com','V$1234567','Coordenador',1200);


    CREATE TABLE CADASTRO_INTERESSE
    (
      id_cadastro_interesse int auto_increment,
        id_estagio int,
        id_empresa int,
        constraint cadas_int_pkey primary key(id_cadastro_interesse),
        constraint cadas_esta_fkey foreign key (id_estagio) references ESTAGIARIO(id_estagiario),
        constraint cadas_emp_fkey foreign key (id_empresa) references EMPREGADOR(id_empregador)
    );

    CREATE TABLE vagas (
      id_vaga int auto_increment,
        id_empregador int,
      descricao varchar(255),
      lista_atividades varchar(255),
      semestre_requerido int,
      lista_habilidades varchar(255),
      quantidade_horas int,
      remuneracao float,
        constraint vaga_pkey primary key (id_vaga),
        constraint vaga_fkey foreign key (id_empregador) references empregador(id_empregador)
    );

5 - Iniciar o WampServer e acessar o navegador usando: http://localhost/projetomoe/public/
