### Домашнее задание к занятию "08.03 Работа с Roles"

## Что делает Playbook

Устанавливает Java, Elastic и Kibana на выбранный хост через roles

## Команды

`ansible-galaxy install -r requirements.yml -p roles`

`ansible-playbook site.yml -i inventory/prod.yml`

## Ссылки на roles
https://github.com/ArinaU/kibana-role

https://github.com/ArinaU/elastic-role
