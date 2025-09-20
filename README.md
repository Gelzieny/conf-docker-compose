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


📌 Observações

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

Você pode verificar os logs de execução com:

```bash
docker-compose logs -f

```