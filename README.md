# Kt-team
Структура

─dev

├───MySQL

├───Nginx

│___├───core

│___│_____└───conf.d

|____|______└───nginx.conf

│___├───html

│___├───Logs

│___└───www

│________└───magento2

├───PHP

|____├───Dockerfile

|____└───php.ini

│________docker-compose.yml

Перед установкой, разархивировать файлы магенты https://magento.com/tech-resources/download в папку Nginx/www/magento2

Не забудьте удалить файлы "deleteme"


После установки Magento2 запускается с артефактами (не прорисовывает фреймы)
Нашел как это исправить, но пока не автоматизировал.

в SQL

insert into core_config_data (config_id, scope, scope_id, path, value) values (null, 'default', 0, 'dev/static/sign', 0)

и в PHP

php bin/magento cache:clean config

php bin/magento setup:static-content:deploy

После этого все корректно отображается.
