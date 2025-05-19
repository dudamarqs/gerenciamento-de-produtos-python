# Documentação Técnica - Sistema de Estoque

## Visão Geral

Este é um sistema de controle de estoque composto por:

* Uma **API REST** desenvolvida com **FastAPI** para gerenciamento de produtos em memória.
* Uma **interface gráfica** usando **PyQt6** que se comunica com a API via HTTP.
* Um inicializador que executa ambos os componentes.
* Um conjunto de testes automatizados para garantir o correto funcionamento da API e da interface, incluindo testes end-to-end com Cypress.

## Estrutura do Projeto

```
projeto_estoque/
├── src/
│   ├── api.py         # API FastAPI
│   ├── estoque.py     # Interface gráfica PyQt6
│   └── start.py       # Inicializa API e GUI
├── test/
│   └── test_api.py    # Testes automatizados da API (Pytest)
├── cypress/
│   ├── e2e/           # Testes E2E com Cypress
│   └── ...            # Arquivos de configuração do Cypress
├── requirements.txt   # Dependências Python
├── package.json       # Dependências do Cypress (Node.js)
├── README.md          # Guia de uso
└── docs/
    └── documentacao.md  # Documentação completa
```

## Instalação

### 1. Clonagem e ambiente

```bash
git clone https://github.com/dudamarqs/gerenciamento-de-produtos-python.git
cd gerenciamento-tarefas-python
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate no Windows
```

### 2. Instalar dependências

```bash
pip install -r requirements.txt
```

## Execução

### 1. Comando principal

```bash
python src/start.py
```

Esse comando:

* Inicia a API em segundo plano na porta `8000`
* Inicia a interface gráfica PyQt6 para login e gerenciamento

### 2. Comandos alternativos

Rodar a API separadamente:

```bash
uvicorn src.api:app --reload
```

Rodar apenas a interface:

```bash
python src/estoque.py
```

> Obs: A API deve estar rodando antes de abrir a interface diretamente.

## Funcionalidades

### API (FastAPI)

| Método | Rota                | Descrição                               |
| ------ | ------------------- | --------------------------------------- |
| GET    | `/produtos`         | Retorna a lista de produtos cadastrados |
| POST   | `/produtos`         | Adiciona um novo produto                |
| PUT    | `/produtos/{index}` | Atualiza um produto pelo índice         |
| DELETE | `/produtos/{index}` | Remove um produto pelo índice           |

### Interface Gráfica (PyQt6)

* Tela de login
* Cadastro de produtos (nome, quantidade, preço, categoria)
* Listagem em tabela
* Remoção de produtos via seleção na tabela
* Atualização de produtos via seleção, preenchimento dos campos e clique no botão Atualizar Produto

## Dados de Acesso

* **Usuário:** `usuario`
* **Senha:** `123`

## Considerações

* O sistema não possui banco de dados; os dados ficam em memória durante a execução.
* Ideal para fins didáticos ou como base para evolução com banco de dados.
* O código é modular, facilitando a expansão com autenticação real, banco de dados, interface web etc.
