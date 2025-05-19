# 📦 Sistema de Estoque com FastAPI + PyQt6

Este projeto é um sistema simples de **gerenciamento de estoque**, com uma API FastAPI e uma interface gráfica em PyQt6, desenvolvido como atividade avaliativa da matéria de **Teste de Software**.

## 🚀 Como Executar

1. **Clone o repositório**

```bash
clone https://github.com/dudamarqs/gerenciamento-de-produtos-python.git
cd gerenciamento-tarefas-python
```

2. **Instale as dependências**

```bash
pip install -r requirements.txt
```

Ou, se preferir instalar manualmente:

```bash
pip install fastapi uvicorn pydantic requests PyQt6
```

3. **Execute o sistema**

```bash
python src/start.py
```

## 🔑 Login

- Usuário: ```usuario```
- Senha: ```123```


## 🧠 Tecnologias Utilizadas

- FastAPI
- PyQt6
- Uvicorn
- Requests
- Pydantic
- Threading
- httpx (para testes)
- Pytest (para testes unitários)
- Cypress (teste E2E)

## 📁 Arquivos

| Arquivo/Pasta      | Descrição                                          |
| ------------------ | -------------------------------------------------- |
| `src/api.py`       | Define a API com os endpoints REST                 |
| `src/estoque.py`   | Interface gráfica com funcionalidades de estoque   |
| `src/start.py`     | Inicializa a API e a interface gráfica juntas      |
| `test/test_api.py` | Testes automatizados da API com FastAPI TestClient |
| `cypress/`         | Testes E2E simulando ações reais na interface      |
| `requirements.txt` | Dependências do projeto Python                     |
| `package.json`     | Configurações e scripts do Cypress (via Node.js)   |


## 💠 Comandos Úteis

Rodar só a API:

```bash
uvicorn src.api:app --reload
```

Rodar só a interface (a API precisa já estar rodando):

```bash
python src/estoque.py
```

Rodar os testes automatizados

```bash
set PYTHONPATH=src  # Windows
pytest test/

PYTHONPATH=src pytest test/  # Linux/macOS
```

## 👩🏻‍💻 Desenvolvedores

- Isabela Martins Bandeira
- João Felipe Alves de Albuquerque da Silva
- Louie Nery Silva
- Maria Eduarda Rita Marques Noleto
- Natália Ematné Kruchak 
