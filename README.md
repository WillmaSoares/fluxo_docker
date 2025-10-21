# Projeto Fluxo Docker

Este projeto é um exemplo de configuração com Docker para um ambiente HTML estático. Ele demonstra como criar uma imagem personalizada usando o NGINX, configurar arquivos essenciais e executar containers de forma prática.

## Estrutura

- `index.html`: página principal
- `style.css`: estilos
- `Dockerfile`: configura o container
- `.dockerignore`: ignora arquivos desnecessários

## Como usar

## 📸 Prints do Terminal Pasta

`prints_terminal`.

### 1º Fluxo – PostgreSQL

```bash
docker run --name meu-postgres -e POSTGRES_PASSWORD=senha -p 5430:5432 -d postgres
```

### 2º Fluxo – NGINX com HTML

```bash
docker build -t meu-nginx .
docker run --name nginx-html -p 80:80 -d meu-nginx
```

### 3º Fluxo – Logs

```bash
docker logs --tail 100 nginx-html
```

### 4º Fluxo – Execução e Remoção

```bash
docker run --name nginx-demo -d -p 8080:80 nginx:alpine
docker logs nginx-8080
docker exec -it nginx-8080 sh
ls /usr/share/nginx/html
exit
docker rm -f nginx-8080
docker rmi nginx:alpine
```
