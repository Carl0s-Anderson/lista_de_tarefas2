# 📝 App Lista de Tarefas - Arquitetura Segura

Um aplicativo web dinâmico para gerenciamento de tarefas do dia a dia. Este projeto vai além de um simples CRUD, implementando uma **arquitetura de diretórios separada (Público/Privado)** para garantir a segurança dos dados e da lógica de negócios da aplicação.

## ✨ Funcionalidades

* **Adicionar Tarefas:** Criação rápida de novas tarefas.
* **Listagem Dinâmica:** Visualização separada para tarefas "Pendentes" e "Todas as Tarefas".
* **Edição In-line:** Atualização da descrição da tarefa diretamente na lista.
* **Exclusão:** Remoção de tarefas indesejadas.
* **Conclusão via Ajax:** Marque tarefas como realizadas sem recarregar a página! A interface é atualizada instantaneamente usando a API `Fetch` do JavaScript.

## 🚀 Tecnologias Utilizadas

* **Front-end:** HTML5, CSS3, JavaScript (Vanilla & Fetch API), Bootstrap 4, FontAwesome.
* **Back-end:** PHP (Orientado a Objetos).
* **Banco de Dados:** MySQL (via PDO).

---

## 🔒 O Segredo por Trás dos Panos: Arquitetura de Segurança

Se você explorar o código fonte deste repositório, notará que o arquivo `tarefa_controller.php` faz uma requisição curiosa:

```php
require_once '../../lista_tarefas_segurança/tararefa_controller.php';
Por que isso acontece?
Este repositório contém apenas os arquivos públicos da aplicação (Views, CSS, JS, e imagens) — ou seja, os arquivos que ficam expostos no diretório raiz do servidor web (como o htdocs ou www).

Para garantir a máxima segurança, toda a inteligência e os dados sensíveis da aplicação ficam em um diretório privado, localizado fora da pasta pública do servidor.

O diretório privado (não exposto neste repositório) contém:

Conexão com o Banco de Dados: Credenciais de acesso protegidas contra invasões e leituras diretas via URL.

Modelos (Models): Classes que representam a estrutura dos dados.

Serviços (Services): Toda a lógica de CRUD (Create, Read, Update, Delete) utilizando PDO para prevenir SQL Injection.

Controlador Real: O motor que processa as requisições e gerencia o fluxo de dados.

Essa separação de responsabilidades (Frontend exposto vs. Backend protegido) é uma prática avançada de segurança que impede o acesso direto aos arquivos do núcleo do sistema.

🛠️ Como rodar o projeto localmente
Para que o projeto funcione na sua máquina, você precisará recriar essa estrutura segura:

Crie o banco de dados: Execute o script presente no arquivo banco_de_dados.sql no seu SGBD (ex: MySQL via phpMyAdmin).

Estrutura de Pastas:

No seu servidor local (ex: XAMPP), vá até a pasta anterior ao htdocs.

Crie uma pasta chamada lista_tarefas_segurança.

Dentro dela, você precisará implementar os arquivos de back-end (conexao.php, tarefa.model.php, tarefa.service.php e tararefa_controller.php).

Pasta Pública: Acesse no navegador: http://github.com/Carl0s-Anderson/lista_de_tarefas2

👨‍💻 Autor
Carlos Anderson

GitHub: @Carl0s-Anderson