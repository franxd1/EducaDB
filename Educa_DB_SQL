DROP DATABASE IF EXISTS EducaDB ;
CREATE DATABASE EducaDB;
USE EducaDB;


CREATE TABLE Alunos (
    Id_Alunos INT PRIMARY KEY NOT NULL,
    RA VARCHAR(20) NOT NULL,
    Nome VARCHAR(255) NOT NULL,
    Data_De_Nasc DATE NOT NULL,
    CPF INT NOT NULL,
    Endereco VARCHAR(255) NOT NULL,
    Telefone INT NOT NULL,
    Email VARCHAR(255) NOT NULL,
    Status VARCHAR(255) NOT NULL,
    fk_Curso_Id_Curso INT
);

CREATE TABLE Turmas (
    Id_Turma INT PRIMARY KEY NOT NULL,
    Ano INT NOT NULL,
    Semestre INT NOT NULL,
    fk_Disciplina_Id_Disciplina INT 
);

CREATE TABLE Disciplina (
    Id_Disciplina INT PRIMARY KEY NOT NULL,
    Carga_Horaria TIME NOT NULL,
    Tipo VARCHAR(255) NOT NULL,
    fk_Curso_Id_Curso INT 
);

CREATE TABLE Professores (
    Id_Professor INT PRIMARY KEY NOT NULL,
    Nome VARCHAR(255) NOT NULL,
    Data_de_Nasc DATE NOT NULL,
    CPF INT NOT NULL,
    Endereco VARCHAR(255) NOT NULL,
    Email VARCHAR(255) NOT NULL,
    Telefone INT NOT NULL,
    Qualificacao VARCHAR(255) NOT NULL,
    fk_Turmas_Id_Turma INT
);

CREATE TABLE Curso (
    Id_Curso INT PRIMARY KEY NOT NULL,
    Nome VARCHAR(255) NOT NULL,
    Descricao VARCHAR(255) NOT NULL,
    Carga_Horaria TIME NOT NULL
);

CREATE TABLE Historico_Escolar (
    Id_Historico_Esc INT PRIMARY KEY NOT NULL,
    Notas DOUBLE NOT NULL,
    Periodo INT NOT NULL,
    Frequencia INT NOT NULL,
    fk_Alunos_Id_Alunos INT 
);
CREATE TABLE Departamentos (
    IdDepartamento INT PRIMARY KEY NOT NULL,
    Nome VARCHAR(255) NOT NULL,
    fk_Professores_Id_Professor INT NOT NULL
);

CREATE TABLE Alunos_has_Turmas (
    fk_Turmas_Id_Turma INT ,
    fk_Alunos_Id_Alunos INT 
);

CREATE TABLE Disciplina_has_Professores (
    fk_Professores_Id_Professor INT ,
    fk_Disciplina_Id_Disciplina INT
);

CREATE TABLE Alunos_has_Disciplina (
    fk_Alunos_Id_Alunos INT,
    fk_Disciplina_Id_Disciplina INT
);

ALTER TABLE Departamentos ADD CONSTRAINT FK_Departamentos_2
    FOREIGN KEY (fk_Professores_Id_Professor)
    REFERENCES Professores (Id_Professor)
    ON DELETE RESTRICT;

ALTER TABLE Turmas ADD CONSTRAINT FK_Turmas_2
    FOREIGN KEY (fk_Disciplina_Id_Disciplina)
    REFERENCES Disciplina (Id_Disciplina)
    ON DELETE RESTRICT;

ALTER TABLE Disciplina ADD CONSTRAINT FK_Disciplina_2
    FOREIGN KEY (fk_Curso_Id_Curso)
    REFERENCES Curso (Id_Curso)
    ON DELETE RESTRICT;

ALTER TABLE Professores ADD CONSTRAINT FK_Professores_2
    FOREIGN KEY (fk_Turmas_Id_Turma)
    REFERENCES Turmas (Id_Turma)
    ON DELETE RESTRICT;

ALTER TABLE Alunos ADD CONSTRAINT FK_Alunos_2
    FOREIGN KEY (fk_Curso_Id_Curso)
    REFERENCES Curso (Id_Curso)
    ON DELETE RESTRICT;

ALTER TABLE Historico_Escolar ADD CONSTRAINT FK_Historico_Escolar_2
    FOREIGN KEY (fk_Alunos_Id_Alunos)
    REFERENCES Alunos (Id_Alunos)
    ON DELETE RESTRICT;

ALTER TABLE Alunos_has_Turmas ADD CONSTRAINT FK_Alunos_has_Turmas_1
    FOREIGN KEY (fk_Turmas_Id_Turma)
    REFERENCES Turmas (Id_Turma)
    ON DELETE RESTRICT;

ALTER TABLE Alunos_has_Turmas ADD CONSTRAINT FK_Alunos_has_Turmas_2
    FOREIGN KEY (fk_Alunos_Id_Alunos)
    REFERENCES Alunos (Id_Alunos)
    ON DELETE RESTRICT;

ALTER TABLE Disciplina_has_Professores ADD CONSTRAINT FK_Disciplina_has_Professores_1
    FOREIGN KEY (fk_Professores_Id_Professor)
    REFERENCES Professores (Id_Professor)
    ON DELETE RESTRICT;

ALTER TABLE Disciplina_has_Professores ADD CONSTRAINT FK_Disciplina_has_Professores_2
    FOREIGN KEY (fk_Disciplina_Id_Disciplina)
    REFERENCES Disciplina (Id_Disciplina)
    ON DELETE RESTRICT;

ALTER TABLE Alunos_has_Disciplina ADD CONSTRAINT FK_Alunos_has_Disciplina_1
    FOREIGN KEY (fk_Alunos_Id_Alunos)
    REFERENCES Alunos (Id_Alunos)
    ON DELETE RESTRICT;

ALTER TABLE Alunos_has_Disciplina ADD CONSTRAINT FK_Alunos_has_Disciplina_2
    FOREIGN KEY (fk_Disciplina_Id_Disciplina)
    REFERENCES Disciplina (Id_Disciplina)
    ON DELETE RESTRICT;

-- Inserir dados na tabela Curso
INSERT INTO Curso (Id_Curso, Nome, Descricao, Carga_Horaria) VALUES
(1, 'Engenharia de Software', 'Curso de Engenharia de Software', 3600),
(2, 'Ciência da Computação', 'Curso de Ciência da Computação', 4000),
(3, 'Engenharia Civil', 'Curso de Engenharia Civil', 4000),
(4, 'Medicina', 'Curso de Medicina', 7200),
(5, 'Direito', 'Curso de Direito', 4500),
(6, 'Administração', 'Curso de Administração', 3600),
(7, 'Arquitetura', 'Curso de Arquitetura', 4000),
(8, 'Biologia', 'Curso de Biologia', 3800),
(9, 'Química', 'Curso de Química', 3600),
(10, 'Física', 'Curso de Física', 3600),
(11, 'Matemática', 'Curso de Matemática', 3600),
(12, 'História', 'Curso de História', 3600),
(13, 'Geografia', 'Curso de Geografia', 3600),
(14, 'Filosofia', 'Curso de Filosofia', 3600),
(15, 'Sociologia', 'Curso de Sociologia', 3600),
(16, 'Educação Física', 'Curso de Educação Física', 3600),
(17, 'Pedagogia', 'Curso de Pedagogia', 3600),
(18, 'Psicologia', 'Curso de Psicologia', 4000),
(19, 'Enfermagem', 'Curso de Enfermagem', 4000),
(20, 'Nutrição', 'Curso de Nutrição', 3600);

-- Inserir dados na tabela Disciplina
INSERT INTO Disciplina (Id_Disciplina, Carga_Horaria, Tipo, fk_Curso_Id_Curso) VALUES
(1, 60, 'Teórica', 1),
(2, 80, 'Prática', 1),
(3, 40, 'Teórica', 2),
(4, 70, 'Teórica', 3),
(5, 50, 'Prática', 3),
(6, 100, 'Teórica', 4),
(7, 60, 'Prática', 4),
(8, 80, 'Teórica', 5),
(9, 70, 'Prática', 5),
(10, 60, 'Teórica', 6),
(11, 40, 'Prática', 6),
(12, 90, 'Teórica', 7),
(13, 60, 'Prática', 7),
(14, 70, 'Teórica', 8),
(15, 50, 'Prática', 8),
(16, 80, 'Teórica', 9),
(17, 60, 'Prática', 9),
(18, 70, 'Teórica', 10),
(19, 50, 'Prática', 10),
(20, 60, 'Teórica', 11);

-- Inserir dados na tabela Professores
INSERT INTO Professores (Id_Professor, Nome, Data_de_Nasc, CPF, Endereco, Email, Telefone, Qualificacao, fk_Turmas_Id_Turma) VALUES
(1, 'João Silva', '1970-05-12', 12345678901, 'Rua A, 123', 'joao.silva@example.com', 11987654321, 'Doutor', NULL),
(2, 'Maria Oliveira', '1980-03-22', 23456789012, 'Rua B, 456', 'maria.oliveira@example.com', 11987654322, 'Mestre', NULL),
(3, 'Carlos Sousa', '1975-07-14', 34567890123, 'Rua C, 789', 'carlos.sousa@example.com', 11987654323, 'Doutor', NULL),
(4, 'Ana Pereira', '1982-09-10', 45678901234, 'Rua D, 101', 'ana.pereira@example.com', 11987654324, 'Mestre', NULL),
(5, 'Pedro Santos', '1968-11-30', 56789012345, 'Rua E, 202', 'pedro.santos@example.com', 11987654325, 'Doutor', NULL);
