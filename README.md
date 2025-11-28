# 📘 Projeto de Banco de Dados — Sistema de Biblioteca

## 🎯 Objetivo
Este projeto tem como finalidade modelar e implementar um **sistema de gerenciamento de biblioteca**, permitindo o controle de usuários, livros, empréstimos, reservas e multas.  
O modelo foi desenvolvido em **MySQL** e pode ser visualizado em diagramas ER no MySQL Workbench.

---

## 🏛️ Entidades Principais

### Biblioteca
- **id_biblioteca** (PK)
- nome
- endereco
- telefone
- email

### Usuário
- **id_usuario** (PK)
- nome
- email
- cpf
- **id_biblioteca** (FK → biblioteca)

### Livro
- **id_livro** (PK)
- titulo
- autor
- genero
- ano_publicacao
- **id_biblioteca** (FK → biblioteca)

### Empréstimo
- **id_emprestimo** (PK)
- **id_usuario** (FK → usuario)
- **id_livro** (FK → livro)
- data_emprestimo
- data_devolucao

### Reserva
- **id_reserva** (PK)
- **id_usuario** (FK → usuario)
- **id_livro** (FK → livro)
- data_reserva

### Multa
- **id_multa** (PK)
- **id_usuario** (FK → usuario)
- valor
- motivo

---

## 🔗 Relacionamentos

- **Biblioteca 1:N Usuário** → cada biblioteca possui vários usuários.  
- **Biblioteca 1:N Livro** → cada biblioteca possui vários livros.  
- **Usuário 1:N Empréstimo** → um usuário pode realizar vários empréstimos.  
- **Usuário 1:N Reserva** → um usuário pode reservar vários livros.  
- **Usuário 1:N Multa** → um usuário pode ter várias multas.  
- **Livro 1:N Empréstimo** → um livro pode estar em vários empréstimos.  
- **Livro 1:N Reserva** → um livro pode ter várias reservas.  

---

## 🛠️ Tecnologias Utilizadas
- **MySQL** para criação das tabelas e definição das chaves primárias e estrangeiras.  
- **MySQL Workbench** para modelagem visual (diagrama ER).  
- **InnoDB** como mecanismo de armazenamento, garantindo suporte a chaves estrangeiras.  

---

## 📈 Benefícios do Projeto
- Organização clara das entidades da biblioteca.  
- Garantia de integridade referencial com uso de **FOREIGN KEYS**.  
- Facilidade para consultas complexas (ex.: listar empréstimos ativos, reservas pendentes, multas por usuário).  
- Escalabilidade: permite adicionar novas bibliotecas, usuários e livros sem comprometer o modelo.  

---

## 🚀 Próximos Passos
- Criar **procedures** para automatizar operações (ex.: registrar empréstimo, calcular multa).  
- Implementar **triggers** para atualizar status de livros automaticamente.  
- Desenvolver uma interface web ou desktop para interação com o banco.  
