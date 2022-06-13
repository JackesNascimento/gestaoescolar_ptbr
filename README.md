<h1 align="center"><img src="public/appname.svg" width="500"></h1>

## A versão 2.X está aqui!!
Para a Versão 1.X, veja as [releases](https://github.com/changeweb/Unifiedtransform/releases). Continuation of Version 1.X support in **[v1-x-branch](https://github.com/changeweb/Unifiedtransform/tree/v1-x-branch)**.

<p align="center">
Software de gestão e contabilidade escolar
</p>

[![Build Status](https://travis-ci.org/changeweb/Unifiedtransform.svg?branch=master)](https://travis-ci.org/changeweb/Unifiedtransform)
[![Linux](https://img.shields.io/travis/changeweb/Unifiedtransform/master.svg?label=linux)](https://travis-ci.org/changeweb/Unifiedtransform)
[![Code Climate](https://codeclimate.com/github/changeweb/Unifiedtransform/badges/gpa.svg)](https://codeclimate.com/github/changeweb/Unifiedtransform)
[![Latest release](https://img.shields.io/github/release/changeweb/Unifiedtransform/all.svg)](https://github.com/changeweb/Unifiedtransform/releases)
[![MadeWithLaravel.com shield](https://madewithlaravel.com/storage/repo-shields/1362-shield.svg)](https://madewithlaravel.com/p/unifiedtransform/shield-link)
[![Discord](https://img.shields.io/discord/917848091107946556)](https://discord.gg/8sz6kpup99)

Gostamos de desafiar a qualidade do que construímos para torná-lo melhor. Para isso, tentamos tornar o produto intuitivo, bonito e fácil de usar. A inovação e o trabalho árduo ajudam a cumprir estes requisitos. Acredito que para inovar precisamos pensar diferente. Alguns meses atrás, descobri que não havia software de gerenciamento escolar gratuito de código aberto que atendesse aos meus padrões de qualidade. Acontece que eu sei um pouco de programação, então decidi fazer um. Também acredito que trabalhar com mais pessoas pode elevar o padrão mais alto do que trabalhar sozinho. Então decidi torná-lo de código aberto e gratuito.

## Destaque no Laravel News !!
![Screenshot_2019-04-07 Laravel News](https://user-images.githubusercontent.com/9896315/55683832-1b3c8c80-5966-11e9-8dfb-ab30a79a98ed.png)
Veja as novidades [aqui](https://laravel-news.com/unified-transform-open-source-school-management-platform)

## Framework usado

- Laravel 8.X
- Bootstrap 5.X

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-39-17 Unifiedtransform.png"></h1>

## Requisitos do servidor

- PHP >= 7.4
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension

## Teste

- Queremos softwares testáveis. A maioria das partes do software na versão anterior 1.x foram cobertas por testes. Vamos cobrir a versão 2.x também. Você também pode contribuir escrevendo casos de teste!
- Para executar Testes de Recurso e Unidade, execute os seguintes comandos:

    ```sh
    $ docker exec -it app sh
    // Inside container shell
    :/# php artisan test
    ```

## Licença

GNU General Public License v3.0

## Contribuir

Unifiedtransform é 100% de código aberto e gratuito para sempre!!

A contribuição da comunidade pode melhorar este produto!!

Ao contribuir para um projeto do Github, você concorda com estes termos dos [Termos de Serviço do Github(Contributions Under Repository License)](https://help.github.com/en/articles/github-terms-of-service#6-contributions-under-repository-license).

Como este projeto está sob a **GNU General Public License v3.0**, de acordo com os Termos de Serviço do Github, todas as suas contribuições também estão sob os mesmos termos de licença.
Assim, você permite que o usuário deste software use sua contribuição sob os termos da **GNU General Public License v3.0**.

## O que há de novo
v2.X é construído a partir do zero. Tanto a interface do usuário quanto o fluxo de trabalho interno do aplicativo foram alterados para um design melhor.

## Recursos ainda a serem migrados de v1.X para v2.X
Os seguintes recursos que existem na v1.X serão adicionados na v2.X também no futuro.

- Pagamento por faixa
- Mensagens
- Gerenciamento de biblioteca
- Gestão de receitas e despesas
- Exportação e importação de estudantes e professores em massa.
- Impressão de relatórios
- Gerenciamento de certificados.
- Outros idiomas suportados (espanhol, ...).

## Como começar
### Usando o Docker Container:

**[Docker](https://www.docker.com/)** agora é suportado e melhorado.

[Como configurar Laravel, Nginx e MySQL com o Docker Compose no Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose-on-ubuntu-20-04)

Com a configuração aprimorada do Docker, você obterá:
- Nginx
- PHP 7.4
- MySQL 5.7

### Passos para instalar:
1. Clone ou baixe o repositório.
2. Crie a pasta **purify** no diretório `storage/app/`.
3. Execute `cp .env.example .env`.
4. Execute `docker-compose up -d`.
5. Execute `docker exec -it db sh`. Dentro do shell, execute:

    ```sh
    :/# mysql -u root -p
    ```

    Mysql **Root password**: `your_mysql_root_password` no arquivo `docker-compose.yml`. Em seguida, execute os seguintes comandos:

    ```sql
    mysql> SHOW DATABASES;
    mysql> GRANT ALL ON unifiedtransform.* TO 'unifiedtransform'@'%' IDENTIFIED BY 'secret';
    mysql> FLUSH PRIVILEGES;
    mysql> EXIT;
    ```
6. Por fim, saia do contêiner executando `exit` no shell do contêiner.
7. Execute `docker exec -it app sh`. Dentro do shell, execute os seguintes comandos:

    ```sh
    :/# composer install
    :/# php artisan key:generate
    :/# php artisan config:cache
    :/# php artisan migrate:fresh --seed
    ```

    Em seguida, saia do container.
8. Visite **http://localhost:8080**. Credenciais de login do administrador:

    - Email: admin@ut.com
    - Password: password

## Passos a seguir:
Por favor, siga cuidadosamente os passos para configurar a escola.

**Função: Admin**

**Painel Escolar**
<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-27-05 Unifiedtransform.png"></h1>

### 1. Crie uma Sessão Escolar:
Depois de fazer login pela primeira vez, você verá a seguinte mensagem na barra de navegação superior.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-31-38 Unifiedtransform.png"></h1>

Para criar uma nova sessão, acesse a página **Configurações acadêmicas**.

#### Página de configurações acadêmicas:
<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-32-44 Unifiedtransform.png"></h1>

A criação bem-sucedida da sessão usando o seguinte formulário exibirá a mensagem de sucesso:

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-33-45 Unifiedtransform.png"></h1>

### 2. Crie um semestre
Agora crie um semestre. A duração do semestre geralmente é de 3 a 6 meses.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-34-45 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-36-39 Unifiedtransform.png"></h1>

### 3. Crie turmas
Agora crie classes. Dê nomes comuns como: **Classe 1** ou **Classe 11 (Ciências)**.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-35-16 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-37-26 Unifiedtransform.png"></h1>

### 4. Crie seções
Agora crie seções para cada classe. Dê o nome da seção (por exemplo: Seção A, Seção B), número da sala e atribua-os à respectiva classe.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-36-27 Unifiedtransform.png"></h1>

### 5. Crie cursos
Agora crie cursos e atribua-os ao respectivo semestre e turma.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-38-13 Unifiedtransform.png"></h1>

### 6. Defina o tipo de presença
A frequência pode ser mantida de duas maneiras: 1. Por seção, 2. Por curso. Atenha-se a um tipo por um semestre. Padrão: **Por seção**.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-37-09 Unifiedtransform.png"></h1>

### 7. Adicionar professores
Agora adicione professores.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-11-34 Unifiedtransform.png"></h1>

### 8. Atribuir professor
Agora atribua professores a semestre, turma, seção e curso.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-12-05 Unifiedtransform.png"></h1>

### 9. Adicionar alunos
Agora adicione alunos e atribua-os à classe e à seção.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-43-37 Unifiedtransform.png"></h1>

### 10. Ver professores e alunos adicionados
Agora navegue até as páginas **Ver professores** e **Ver alunos**.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-55-18 Unifiedtransform.png"></h1>

### 11. Veja o perfil do aluno e do professor
Agora navegue até **Perfil** na lista de alunos e professores.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 18-29-30 Unifiedtransform.png"></h1>

### 12. Visualize e edite classes e seções
Agora vá para **Aulas**. Aqui você pode ver todas as aulas e suas respectivas seções, programas e cursos. Aulas, seções e cursos podem ser editados a partir daqui.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-30-30 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-30-55 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-31-14 Unifiedtransform.png"></h1>

### 13. Crie sistemas de classificação
Agora crie um sistema de notas para cada turma e um semestre.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-32-31 Unifiedtransform.png"></h1>

### 14. Visualizar sistemas de classificação
Agora navegue até os sistemas de classificação criados.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-33-23 Unifiedtransform.png"></h1>

### 15. Adicione e visualize as regras do sistema de classificação
Agora adicione regras ao sistema de classificação e navegue por elas.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-33-36 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 12-16-04 Unifiedtransform.png"></h1>

### 16. Adicionar avisos
O administrador pode adicionar um aviso. No momento, os avisos podem ser escritos usando um editor de rich text.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-03-55 Unifiedtransform.png"></h1>

### 17. Crie eventos
Os eventos podem ser criados dentro de um calendário. Clique e arraste em uma data ou período de tempo para exibir a caixa de entrada. Um evento já criado pode ser **excluído** clicando no evento.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot from 2021-12-07 01-24-28.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-26-18 Unifiedtransform.png"></h1>

### 18. Crie e visualize rotinas
As rotinas podem ser criadas para cada classe e seção.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-27-54 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 02-26-21 Unifiedtransform.png"></h1>

### 19. Adicionar programa de estudos
Programa de estudos para cada classe e curso pode ser adicionado. O administrador pode visualizá-los na página **Classes**. O programa pode ser baixado.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 18-14-31 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-55-50 Unifiedtransform.png"></h1>

### 20. Navegue por sessões
Você pode navegar pelas sessões anteriores como um instantâneo. Este modo é **Somente leitura**. Ninguém deve poder alterar os dados das sessões anteriores.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 02-28-23 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-37-02 Unifiedtransform.png"></h1>

### 21. Allow Teachers to submit Final Marks
Submitting final marks of a semester should be controlled. By enabling this feature, it is possible to open a Mark Submission Window for a short time period. **Default: Disallowed**.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 00-38-37 Unifiedtransform.png"></h1>

### 22. Promote students
Students can only be promoted to a new class and section when a new Session along with its classes and sections are created.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 02-27-32 Unifiedtransform.png"></h1>
<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 02-28-00 Unifiedtransform.png"></h1>

**Role: Teacher**

**Teacher's dashboard**

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-41-04 Unifiedtransform.png"></h1>

### 1. View assigned courses
Teachers can manage their assigned courses from this page. From this page, teacher can do following:

- Take and view attendance
- View Syllabus
- Create and view Assignment
- Give Marks
- Message Students (Available in v1.X. Will be added in v2.X as well).

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-41-34 Unifiedtransform.png"></h1>

### 2. Take attendance
Teacher can take attendance for a section or a course (attendance type set by Admin).

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-51-20 Unifiedtransform.png"></h1>

### 3. View attendance
Teacher can view attendance.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-52-00 Unifiedtransform.png"></h1>

### 4. View syllabus
Teacher can view and download syllabus.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-56-20 Unifiedtransform.png"></h1>

### 5. Create assignment
Teacher can create assignment for an assigned course by uploading files.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-52-27 Unifiedtransform.png"></h1>

### 6. View assignments
Teacher can view and download created assignments.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-54-12 Unifiedtransform.png"></h1>

### 7. Create Exams
Before giving marks, teacher needs to create exams and set their rules. Don't have to create all the exams at a time. (Admin can also create exams on behalf of teachers).

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 20-10-30 Unifiedtransform.png"></h1>

### 8. View created exams
Teacher can view their created exams.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-43-58 Unifiedtransform.png"></h1>

### 9. Add, edit and view exam rules
Teacher can add, edit, and view exam rules.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-44-24 Unifiedtransform.png"></h1>

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-45-21 Unifiedtransform.png"></h1>

### 10. Give marks
Teacher can give marks after creating exams. Clicking on the exam names will lead to associated exam rules.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 11-47-50 Unifiedtransform.png"></h1>

### 11. Submit Final Marks
When the Grade submission window is open, teacher can submit final marks. Calculated marks will be generated based on all exams' marks. Final marks should be in **between** the marks set in the grade rules.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 11-48-01 Unifiedtransform.png"></h1>

If final marks is submitted, a message will be shown in place of submit button in **Give Marks** page.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 11-59-51 Unifiedtransform.png"></h1>

### 12. View Final Results
Teachers can view final results and calculated grades for a semester, class, section, and course based on their created grade rules.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 13-23-22 Unifiedtransform.png"></h1>

**Role: Student**

**Student dashboard**

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-57-15 Unifiedtransform.png"></h1>

### 1. View attendance
A student can view his/her attendance.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 11-39-45 Unifiedtransform.png"></h1>

### 2. View courses
A student can view his/her courses that are assigned in his/her class. From here, a student can do following:

- View Marks
- View Syllabus
- View Assignments

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 01-57-57 Unifiedtransform.png"></h1>

### 3. View Marks
A student can view marks, final results and grade for a course.

<h1 align="center"><img src="public/docs/imgs/ut/Screenshot 2021-12-07 at 13-41-38 Unifiedtransform.png"></h1>

### 4. View and download Syllabus
Students can view and download syllabi of their courses just like their teachers.

### 5. View and download assignments
Students can view and download assignments of their courses just like their teachers.

### 6. View routine
Students can view their class and section routine just like their admin/teachers.


