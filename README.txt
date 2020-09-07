1. Clean all images in Docker
docker images
...
docker rmi {IMAGE ID}
---

2. Make images for our project
docker-compose build --no-cache

3. Install Laravel
docker run --rm --interactive --tty --volume "%cd%":/app composer create-project --prefer-dist laravel/laravel project

4. Edit /project/.env
Pay attention database (DB_HOST pointed in docker-compose.yaml and these names must be the same)
For example

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=secret

5. Run project
docker-compose up -d
