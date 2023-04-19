# serving-files-with-nginx-and-minio

## Descrição

Vem ai...

## Criando o bucket

1. Utilize o serviço `minio_mc` no docker-compose para adicionar as credenciais do Minio:

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
