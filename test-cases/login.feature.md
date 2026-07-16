## Casos de Teste - Tela de Login

Este documento reúne os casos de teste elaborados utilizando a abordagem BDD (Behavior-Driven Development) para uma tela de login desenvolvida a partir de um protótipo já existente disponibilizado na comunidade do Figma. O objetivo deste projeto é demonstrar a análise dos requisitos visuais da interface e a construção de cenários de teste funcionais.

A tela de login utilizada possui os seguintes elementos:

* Username;
* Password;
* Botão de Login;
* Link **"Forgot Password"**.

O protótipo utilizado pode ser acessado no link abaixo:

https://www.figma.com/community/file/872144934711314532/login-page-design?q_id=acace580-7ff8-4fbd-8f57-52e276b43ed1

A seguir, encontram-se os casos de teste desenvolvidos para a funcionalidade de login.


## CT-01 - Login com usuário válido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

Given que o usuário está na tela de Login
And possui um username válido e um password válido
When informar as credenciais válidas e clicar no botão Login
Then o sistema deve autenticar o usuário e redirecioná-lo para a página inicial da aplicação



## CT-02 - Login com usuário inválido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

**Given** que o usuário está na tela de Login;
**And** possui um username ou um password inválidos;
**When** informar as credenciais inválidas e clicar no botão Login;
**Then** o sistema deve exibir uma mensagem informando que o e-mail ou a senha estão incorretos.


## CT-03 - : Login com campo username não preenchido pelo usuário.

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

Given que o usuário está na tela de Login;
And  preencheu apenas o campo password;
When clicar no botão Login;
Then o sistema deve exibir uma mensagem informando que o campo username é obrigatório.

## CT-04 - : Login com campo password não preenchido pelo usuário.

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

Given que o usuário está na tela de Login;
And  preencheu apenas o campo username;
When clicar no botão Login;
Then o sistema deve exibir uma mensagem informando que o campo password é obrigatório.


