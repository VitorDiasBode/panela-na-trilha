# 🍲 Panela na Trilha

Aplicação web para escoteiros planejarem refeições de acampamento de forma prática e colaborativa. Permite registrar os dias de acampamento, organizar os pratos por refeição, listar ingredientes e gerar automaticamente uma lista de compras com base no número de participantes.

---

## 📌 Funcionalidades

- ✅ Cadastro de acampamentos com número de dias e participantes
- ✅ Planejamento de refeições (café, almoço, jantar, etc.)
- ✅ Associação de pratos e ingredientes
- ✅ Cálculo automático da lista de compras
- ✅ Interface amigável para escoteiros e chefes
- ✅ Compartilhamento e visualização online

---

## 🚀 Tecnologias

- **Frontend:** HTML5, CSS, JavaScript
- **Backend:** Node.js
- **Banco de dados:** PostgreSQL

---

## 🧱 Estrutura de Dados
```json
Camp
{
  "id": "uuid",
  "name": "Acampamento de Verão",
  "startDate": "2025-07-01",
  "endDate": "2025-07-03",
  "participants": 20,
  "meals": [ ... ]
}
```

```json
Meal
{
  "id": "uuid",
  "date": "2025-07-01",
  "type": "Almoço",
  "campId": "camp-001",
  "dishes": [
    { "dishId": "dish-001", "servings": 1 },
    { "dishId": "dish-002", "servings": 1 }
  ]
}
```

```json
Dish

{
  "id": "uuid",
  "name": "Macarronada",
  "ingredients": [
    {
      "ingredientId": "uuid",
      "amountPerPerson": 100,
      "unit": "g"
    }
  ]
}
```

```json
Ingredient

{
  "id": "uuid",
  "name": "Macarrão",
  "unit": "g"
}
```

---

🧮 Exemplo de Cálculo

**Macarrão (100g por pessoa) para 20 pessoas -> 2kg**
Todos os ingredientes de todos os pratos planejados para o período serão multiplicados pela quantidade de pessoas e agregados na lista de compras.

---

## 📘Histórias de Usuário

> As funcionalidades do sistema são descritas a partir da perspectiva de diferentes perfis de usuário, usando a estrutura:  
> **Como [personagem], quero [ação] para [benefício].**

- **Escoteiro Jovem**: quer acompanhar as refeições, entender o que será servido e colaborar no planejamento.
  
- **Chefe Escoteiro**: organiza o acampamento, planeja o cardápio e supervisiona a lista de compras.
  
- **Equipe de Cozinha**: precisa saber o que cozinhar e quais ingredientes estão disponíveis.
  
- **Administrador da Ferramenta**: cuida da manutenção e gerenciamento geral da plataforma.

---

### 🏕️ PROPRIEDADE DE ACAMPAMENTOS

- **Como usuário autenticado**, quero criar um novo acampamento e ser automaticamente o chefe responsável.
  
- **Como usuário autenticado**, quero ver a lista de acampamentos dos quais participo.
  
- **Como criador do acampamento**, quero poder editar ou excluir o acampamento que criei.

---

### 🔐 AUTENTICAÇÃO E PERFIL

- **Como usuário**, quero criar uma conta com email e senha para ter acesso seguro ao sistema.

- **Como usuário**, quero fazer login com minha conta para acessar meus acampamentos.
  
- **Como usuário**, quero editar meu nome e imagem de perfil para personalizar minha conta.
  
- **Como usuário**, quero redefinir minha senha caso eu esqueça.

---

### 💌 CONVITE DE PARTICIPANTES

- **Como chefe do acampamento**, quero definir um link para cada tipo de participante do acampamento (chefe ou equipe de cozinha).
  
- **Como chefe do acampamento**, quero convidar outros usuários para participar do meu acampamento usando um link.
  
- **Como convidado**, quero aceitar o convite e ser adicionado automaticamente ao acampamento com meu papel definido.
  
- **Como chefe do acampamento**, quero remover participantes do acampamento se necessário.

---

### 🔒 PERMISSÕES POR TIPO DE USUÁRIO

- **Como chefe**, quero poder editar todas as informações do acampamento (dias, refeições, pratos, ingredientes).
  
- **Como equipe de cozinha**, quero visualizar as refeições e a lista de compras, mas não editar os dados do acampamento.
  
- **Como chefe**, quero alterar o papel de um participante se necessário.
  
- **Como participante**, quero ver claramente quais ações posso ou não fazer com base no meu tipo.

---
### 🍽️ PLANEJAMENTO DE REFEIÇÕES

- **Como chefe escoteiro**, quero cadastrar um acampamento com número de dias e participantes para iniciar o planejamento.

- **Como chefe escoteiro**, quero definir as refeições de cada dia (café, almoço, jantar) para estruturar o cardápio.

- **Como escoteiro jovem**, quero visualizar as refeições planejadas para saber o que será servido.

- **Como chefe escoteiro**, quero adicionar pratos em cada refeição para montar o menu completo.

---

### 🥘 CADASTRO DE PRATOS E INGREDIENTES

- **Como chefe escoteiro**, quero cadastrar pratos com nome, descrição e ingredientes para reutilizá-los em outros acampamentos.
    
- **Como chefe escoteiro**, quero associar quantidades de ingredientes aos pratos para calcular a compra exata.
    
- **Como escoteiro jovem**, quero sugerir pratos para o acampamento como forma de participação.
    

---

### 🛒 LISTA DE COMPRAS

- **Como chefe escoteiro**, quero gerar uma lista de compras baseada nos pratos e no número de participantes para facilitar a preparação.
    
- **Como equipe de cozinha**, quero visualizar a lista de ingredientes agrupados por tipo para facilitar a compra.
    
- **Como chefe escoteiro**, quero exportar a lista de compras em PDF ou planilha para levar comigo.
    

---

### 📱 USABILIDADE E ACESSO

- **Como escoteiro jovem**, quero acessar a aplicação do celular para acompanhar as refeições com facilidade.
    
- **Como chefe escoteiro**, quero salvar e compartilhar o link do acampamento com a tropa.
    
- **Como administrador**, quero gerenciar os acessos para que apenas pessoas autorizadas editem o planejamento.
    

---

### 🛠️ AJUDA E INTERATIVIDADE

- **Como usuário**, quero receber dicas da mascote _Lua_ durante o uso para entender melhor como usar a ferramenta.
    
- **Como chefe escoteiro**, quero ver alertas se estiver faltando alguma refeição ou ingrediente.
    

---

### 💬 FEEDBACK E MELHORIAS

- **Como escoteiro jovem**, quero deixar comentários ou sugestões nos pratos para melhorar os próximos acampamentos.
    
- **Como chefe escoteiro**, quero revisar o histórico de acampamentos anteriores para usar como referência.

---

### 📜 REGISTRO E TRANSPARÊNCIA

- **Como participante**, quero ver quem são os outros membros do acampamento e seus papéis.

- **Como chefe**, quero registrar o histórico de convites enviados e aceitos.
  
- **Como chefe**, quero ser notificado se alguém aceitar ou recusar um convite.

---

### 📝 HISTÓRIAS FUTURAS (SUGESTÕES)

- **Como usuário**, quero autenticar com minha conta Google  para acessar meus acampamentos pessoais.
    
- **Como chefe escoteiro**, quero importar pratos ou acampamentos de outros grupos.
    

---
