# 🐳 Configuração Docker

Este projeto utiliza **Docker Compose** para gerenciar os containers de forma prática e padronizada.  
Abaixo estão os principais comandos e um exemplo de configuração.

---

## 🚀 Subindo os containers

O parâmetro `--build` garante que qualquer alteração na imagem seja reconstruída antes de iniciar os serviços:

```bash
docker-compose up --build
```

🔄 Rodando em segundo plano (detached)

Caso queira manter os containers rodando em background:

```bash
docker-compose up -d
```

🛑 Parando os containers

Para parar os serviços em execução:

```bash
docker-compose down
```

🧹 Limpando containers, imagens e volumes

Se precisar remover tudo e começar do zero:

```bash
docker-compose down --volumes --rmi all
```

📦 Exemplo de docker-compose.yml

Aqui está um exemplo básico com uma aplicação Flask e um banco PostgreSQL:

```yaml
version: "3.9"

services:
  app:
    build: ./app
    container_name: flask_app
    ports:
      - "5000:5000"
    environment:
      - DATABASE_URL=postgresql://postgres:postgres@db:5432/mydb
    depends_on:
      - db

  db:
    image: postgres:15
    container_name: postgres_db
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: mydb
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```
📌 Estrutura do projeto
.
├── app/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── src/
│       └── app.py
├── docker-compose.yml
└── README.md


📌 Observações

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

Você pode verificar os logs de execução com:

```bash
docker-compose logs -f

```