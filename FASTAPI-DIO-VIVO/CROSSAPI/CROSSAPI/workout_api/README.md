Claro, aqui está uma versão revisada do README que mantém o mesmo sentido, mas com uma redação diferente:

---

# FastAPI
### O que é o FastAPI?
O FastAPI é um framework web moderno e de alta performance para a construção de APIs, fácil de aprender e usar, pronto para produção. Ele permite criar APIs com Python 3.6 ou superior, aproveitando os type hints padrão do Python.

### Async
Código assíncrono permite que a linguagem informe ao computador/programa que, em determinado momento, será necessário esperar que algo finalize em outro lugar.

# Projeto
## WorkoutAPI

Esta é uma API chamada WorkoutAPI, focada em competições de crossfit. Trata-se de uma API compacta, desenvolvida como um projeto prático e simplificado, contendo poucas tabelas.

## Diagrama de Entidade e Relacionamento (MER)
![image](https://github.com/Djalves424/Workout-FastAPI/assets/108296040/072091fd-7078-4e87-8fa0-54158826d927)

## Tecnologias Utilizadas

A API foi desenvolvida utilizando o `fastapi` (assíncrono), juntamente com as bibliotecas `alembic`, `SQLAlchemy` e `pydantic`. Para o armazenamento dos dados, foi utilizado o `postgres` via `docker`.

## Como Executar a API

Para rodar o projeto, utilizamos a [pyenv](https://github.com/pyenv/pyenv) com a versão 3.11.4 do `python` para criar o ambiente virtual.

Se você optar por usar pyenv, após a instalação, siga os passos abaixo:

```bash
pyenv virtualenv 3.11.4 workoutapi
pyenv activate workoutapi
pip install -r requirements.txt
```

Para iniciar o banco de dados, instale o [docker-compose](https://docs.docker.com/compose/install/linux/) se ainda não o tiver, e depois execute:

```bash
make run-docker
```

Para criar uma nova migration, execute:

```bash
make create-migrations d="nome_da_migration"
```

Para criar o banco de dados, execute:

```bash
make run-migrations
```

## API

Para iniciar a API, execute:

```bash
make run
```

E acesse: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

# Desafio Final
    - Adicionar query parameters nos endpoints:
        - Atleta:
            - Nome
            - CPF
    - Customizar a resposta dos endpoints:
        - get all:
            - Atleta:
                - Nome
                - Centro de treinamento
                - Categoria
    - Manipular exceção de integridade dos dados em cada módulo/tabela:
        - sqlalchemy.exc.IntegrityError, retornando a mensagem: “Já existe um atleta cadastrado com o cpf: x”
        - status_code: 303
    - Adicionar paginação utilizando a biblioteca: fastapi-pagination:
        - limit e offset

# Referências

- FastAPI: [https://fastapi.tiangolo.com/](https://fastapi.tiangolo.com/)
- Pydantic: [https://docs.pydantic.dev/latest/](https://docs.pydantic.dev/latest/)
- SQLAlchemy: [https://docs.sqlalchemy.org/en/20/](https://docs.sqlalchemy.org/en/20/)
- Alembic: [https://alembic.sqlalchemy.org/en/latest/](https://alembic.sqlalchemy.org/en/latest/)
- Fastapi-pagination: [https://uriyyo-fastapi-pagination.netlify.app/](https://uriyyo-fastapi-pagination.netlify.app/)

---
