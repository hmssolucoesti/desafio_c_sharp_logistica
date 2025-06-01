# 📦 Desafio Técnico – Desenvolvedor C# Sênior (Logística e Entregas)

## 📝 Descrição

Este projeto tem como objetivo avaliar habilidades de um desenvolvedor C# sênior na construção de uma aplicação RESTful robusta, com foco em **processamento assíncrono, filas, integração com banco de dados** e boas práticas de arquitetura.

Você deve implementar um sistema que simula o fluxo de **entregas de pedidos** no contexto de uma empresa de logística.

---

## 🎯 Objetivos

Desenvolver uma **REST API** em ASP.NET Core que permita:

- Cadastrar uma nova entrega
- Salvar os dados em um banco de dados
- Colocar a entrega em uma fila para processamento assíncrono
- Processar a entrega via um serviço em segundo plano
- Atualizar o status da entrega com base em regras de negócio
- Consultar o status atual de uma entrega

---

## 📦 Requisitos funcionais

### 📍 Cadastro de Entrega
- Endpoint: `POST /entregas`
- Payload:
```json
{
  "pedidoId": "ABC123",
  "destinatario": {
    "nome": "João da Silva",
    "endereco": "Rua das Flores, 1000",
    "cep": "01010-000"
  },
  "itens": [
    { "descricao": "Geladeira", "quantidade": 1 },
    { "descricao": "Fogão", "quantidade": 1 }
  ]
}
```

A entrega é salva no banco de dados com status inicial Pendente.

## 🛠️ Processamento em Fila
A entrega é enfileirada para ser processada por um serviço em segundo plano.

## O serviço:

Atualiza o status para Saiu para entrega

Aguarda 3 segundos (simulação)

Atualiza o status para:

Entregue com sucesso ou

Falha na entrega (regra aleatória usando Random)

## 🔍 Consulta de Entrega

Endpoint: GET /entregas/{id}

Deve retornar os dados e o status atual da entrega

## 🧠 Critérios de Avaliação

Organização do código / Camadas	25%

Clareza e lógica de processamento	20%

Modelagem de dados	15%

Uso de filas e serviços	15%

Boas práticas (REST, SOLID)	15%

Testes ou simulações adicionais	10%



## Swagger para documentação da API

Injeção de dependência e separação por camadas (Controller, Service, Repository, Domain, etc.)

## 📬 Entrega

Envie o link do repositório público (GitHub/GitLab)

O código deve conter instruções claras de execução

Adicione comentários explicando suas decisões de arquitetura, se necessário

