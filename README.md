# serving-files-with-nginx-and-minio

## Descrição

Um estudo simples de como servir via Nginx, arquivos estáticos localizados num bucket da da vida. Neste exemplo usei o Minio como bucket.

## Criando o bucket

Utilize o serviço `minio_mc` no docker-compose para interagir com o Minio via CLI

1. Adicione as credenciais do Minio:

```sh
docker-compose run --rm minio_mc alias set local http://minio:9000 admin adminadmin
```

2. Crie um bucket:

```sh
docker-compose run --rm minio_mc mb local/mybucket
```

3. Dê permissão de download para o bucket recém criado:

```sh
docker-compose run --rm minio_mc anonymous set download local/mybucket
```
