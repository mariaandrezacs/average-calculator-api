# Average Calculator API

API Flask para calcular a média de uma lista de números. Este projeto foi desenvolvido como parte do **Desafio 04** do curso da Rocketseat sobre **Introdução ao Design de Código**.

## 📋 Descrição

Esta API expõe um endpoint POST que recebe uma lista de números e retorna a média aritmética desses valores. O projeto implementa boas práticas de design de código, incluindo:

- Separação de responsabilidades
- Testes unitários
- Tratamento de erros HTTP
- Padrão Factory
- Interfaces para handlers externos
- Injeção de dependências

## 🚀 Como Executar

### Pré-requisitos

- Python 3.12
- pip (gerenciador de pacotes Python)

### Instalação

1. Clone o repositório:
```bash
git clone <url-do-repositorio>
cd average-calculator-api
```

2. Instale as dependências:
```bash
pip install flask numpy
```

### Executar o servidor

```bash
python run.py
```

O servidor estará disponível em `http://localhost:3000`

## 📁 Estrutura do Projeto

```
average-calculator-api/
├── src/
│   ├── calculator/          # Lógica da calculadora
│   │   ├── calculator_4.py  # Implementação da calculadora de média
│   │   ├── calculator_4_test.py  # Testes unitários
│   │   └── info-challenge.md  # Informações do desafio
│   ├── drivers/             # Handlers para bibliotecas externas
│   │   ├── interfaces/
│   │   │   └── driver_handler_interface.py  # Interface abstrata
│   │   └── numpy_handler.py  # Handler para NumPy
│   ├── errors/              # Tratamento de erros
│   │   ├── error_controller.py  # Controller de erros
│   │   ├── http_bad_request.py
│   │   └── http_unprocessable_entity.py
│   └── main/                # Configuração da aplicação
│       ├── factories/
│       │   └── calculator4_factory.py  # Factory pattern
│       ├── routes/
│       │   └── calculators.py  # Rotas da API
│       └── server/
│           └── server.py  # Configuração do servidor Flask
├── run.py                   # Ponto de entrada da aplicação
└── README.md
```

## 🔌 Endpoints

### POST /calculator/4

Calcula a média de uma lista de números.

**Request Body:**
```json
{
  "numbers": [2.12, 4.62, 1.32]
}
```

**Response (200 OK):**
```json
{
  "data": {
    "Calculator": 4,
    "value": 2.686666666666667,
    "Sucess": true
  }
}
```

**Error Response (422 Unprocessable Entity):**
```json
{
  "errors": [
    {
      "title": "UnprocessableEntity",
      "detail": "body mal formatado!"
    }
  ]
}
```

## 🧪 Testes

Para executar os testes unitários:

```bash
python -m pytest src/calculator/calculator_4_test.py -v
```

Ou execute diretamente:
```bash
python src/calculator/calculator_4_test.py
```

## 🛠️ Tecnologias Utilizadas

- **Python** - Linguagem de programação
- **Flask** - Framework web para a API
- **NumPy** - Biblioteca para operações matemáticas

## 📝 Padrões e Práticas

- **Factory Pattern**: Utilizado para criar instâncias da calculadora
- **Dependency Injection**: Handlers são injetados na calculadora
- **Interface Segregation**: Interface abstrata para handlers
- **Error Handling**: Tratamento centralizado de erros HTTP
- **Separation of Concerns**: Cada módulo tem uma responsabilidade única

## 🎯 Desafio Rocketseat

Este projeto foi desenvolvido como solução para o Desafio 04 do curso da Rocketseat. O objetivo era criar uma nova rota que retorne a média entre uma lista de números, aplicando todos os conceitos de design de código ensinados no módulo.

## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.