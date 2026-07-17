# Casos de Teste - Tela de Login

Este documento reúne os casos de teste elaborados utilizando a abordagem BDD (Behavior-Driven Development) para uma tela de login desenvolvida a partir de um protótipo já existente disponibilizado na comunidade do Figma. O objetivo deste projeto é demonstrar a análise dos requisitos visuais da interface e a construção de cenários de teste funcionais.

A tela de login utilizada possui os seguintes elementos:

- Username;
- Password;
- Botão de Login;
- Link **"Forgot Password"**.


## Protótipo da Tela de Login

A tela de login utilizada como referência para a elaboração dos casos de teste foi criada no Figma e disponibilizada na comunidade da plataforma.

![Protótipo da Tela de Login](https://github.com/user-attachments/assets/225c1fe9-4076-4578-9fd3-60f7aef7df1f)

O protótipo utilizado pode ser acessado no link abaixo:

https://www.figma.com/community/file/872144934711314532/login-page-design?q_id=acace580-7ff8-4fbd-8f57-52e276b43ed1

A seguir, encontram-se os casos de teste desenvolvidos para a funcionalidade de login.


## CT-01 - Login com usuário válido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Login com usuário válido

Given que o usuário está na tela de Login
And possui um username válido e um password válido
When informar as credenciais válidas e clicar no botão Login
Then o sistema deve autenticar o usuário e redirecioná-lo para a página inicial da aplicação
```

---

## CT-02 - Login com usuário inválido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Login com usuário inválido

Given que o usuário está na tela de Login
And possui um username ou password inválidos
When informar as credenciais inválidas e clicar no botão Login
Then o sistema deve exibir uma mensagem informando que o username ou password estão incorretos
```

---

## CT-03 - Login com campo username não preenchido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Login sem preencher o campo username

Given que o usuário está na tela de Login
And preencheu apenas o campo password
When clicar no botão Login
Then o sistema deve exibir uma mensagem informando que o campo username é obrigatório
```

---

## CT-04 - Login com campo password não preenchido

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Login sem preencher o campo password

Given que o usuário está na tela de Login
And preencheu apenas o campo username
When clicar no botão Login
Then o sistema deve exibir uma mensagem informando que o campo password é obrigatório
```

---

## CT-05 - Login com campos username e password não preenchidos

- **Tipo de Teste:** Funcional
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Login sem preencher username e password

Given que o usuário está na tela de Login
And não preencheu os campos username e password
When clicar no botão Login
Then o sistema deve exibir uma mensagem informando que os campos username e password são obrigatórios
```

---

## CT-06 - Login utilizando a tecla Enter

- **Tipo de Teste:** Usabilidade/Acessibilidade
- **Prioridade:** Média

### Cenário BDD

```gherkin
Scenario: Login utilizando a tecla Enter

Given que o usuário está na tela de Login
And possui um username válido e um password válido
When pressionar a tecla Enter
Then o sistema deve autenticar o usuário e redirecioná-lo para a página inicial da aplicação
```

---

## CT-07 - Recuperação de senha

- **Tipo de Teste:** Funcional
- **Prioridade:** Média

### Cenário BDD

```gherkin
Scenario: Acessar recuperação de senha

Given que o usuário está na tela de Login
When clicar no link "Forgot Password"
Then o sistema deve redirecionar o usuário para a página de recuperação de senha
```

---

## CT-08 - Bloquear tentativa de login utilizando SQL Injection no campo username

- **Tipo de Teste:** Segurança
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Bloquear tentativa de SQL Injection

Given que o usuário está na tela de Login
And informa um payload de SQL Injection no campo username
And informa qualquer password no campo password
When clicar no botão Login
Then o sistema deve rejeitar a tentativa de login
```

---

## CT-09 - Impedir múltiplos envios ao clicar várias vezes no botão Login

- **Tipo de Teste:** Usabilidade
- **Prioridade:** Alta

### Cenário BDD

```gherkin
Scenario: Impedir múltiplos envios de login

Given que o usuário está na tela de Login
And possui um username válido e um password válido
When clicar várias vezes rapidamente no botão Login
Then o sistema deve processar apenas uma tentativa de login
```

---

## CT-10 - Realizar login utilizando navegação via teclado

- **Tipo de Teste:** Acessibilidade
- **Prioridade:** Média

### Cenário BDD

```gherkin
Scenario: Realizar login utilizando teclado

Given que o usuário está na tela de Login
When pressionar a tecla Tab para navegar entre os campos
Then o foco deve seguir a ordem correta dos elementos
And o usuário deve conseguir acessar os campos username, password e botão Login
And ao pressionar Enter no botão Login o sistema deve realizar a autenticação
```

---

## CT-11 - Tentar realizar login sem conexão com a internet

- **Tipo de Teste:** Funcional
- **Prioridade:** Média

### Cenário BDD

```gherkin
Scenario: Login sem conexão com a internet

Given que o usuário está na tela de Login
And possui um username válido e um password válido
And o dispositivo está sem conexão com a internet
When clicar no botão Login
Then o sistema não deve realizar o login
And deve informar ao usuário que não foi possível conectar ao servidor
```

---

## CT-12 - Validar elementos da tela de Login

- **Tipo de Teste:** Interface
- **Prioridade:** Baixa

### Cenário BDD

```gherkin
Scenario: Validar elementos presentes na tela de Login

Given que o usuário está na tela de Login
When a página de Login for carregada
Then o campo Username deve estar visível
And o campo Password deve estar visível
And o botão Login deve estar visível
And o link "Forgot Password" deve estar visível
```

---

> **Observação:** Os cenários foram elaborados considerando o comportamento esperado de uma aplicação real, visto que o protótipo utilizado é estático.
