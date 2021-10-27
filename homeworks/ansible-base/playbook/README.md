### Домашнее задание к занятию "08.01 Введение в Ansible"


1. Где расположен файл с `some_fact` из второго пункта задания?
`/group_vars/all/examp.yml`
2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?
`ansible-playbook site.yml -i inventory/test.yml`
3. Какой командой можно зашифровать файл?
`ansible-vault encrypt group_vars/el/examp.yml`
4. Какой командой можно расшифровать файл?
`ansible-vault decrypt group_vars/el/examp.yml`
5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?
`ansible-vault view group_vars/el/examp.yml`
6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?
`ansible-playbook site.yml -i inventory/prod.yml --ask-vault-pass`
7. Как называется модуль подключения к host на windows?
win_command или win_shell (?)
8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh
`ansible-doc -t connection -s ssh`
9. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?
`- remote_user` - имя пользователя для входа на удаленный сервер, обычно задается ключевым словом remote_user.

