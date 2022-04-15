
# Setup Docker Para Projetos Laravel

### Passo a passo
Clone Repositório
```sh
git clone https://github.com/Higor23/setup-docker-php-7-laravel-8.git my-project
cd my-project/
```

Remova o versionamento
```sh
rm -rf .git/
```

Copie e cole o conteúdo abaixo no arquivo .env
```dosini
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:GjSG/sSumo5imCspoMQAaUcwmMcYDmucdJwtdt2wiZ0=
APP_DEBUG=true
APP_URL=http://localhost:8180

LOG_CHANNEL=stack
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=root

BROADCAST_DRIVER=log
CACHE_DRIVER=redis
FILESYSTEM_DRIVER=local
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS=null
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_APP_CLUSTER=mt1

MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
```

Crie o Arquivo .env e cole (shift + Insert) o conteúdo da área de transferência
```sh
cat > .env
```

Suba os containers do projeto
```sh
docker-compose up -d
```

Acessar o container
```sh
docker-compose exec laravel_8 bash
```

Instalar as dependências do projeto
```sh
composer install
```

Gerar a key do projeto Laravel
```sh
php artisan key:generate
```

Acesse o projeto
[http://localhost:8180](http://localhost:8180)
