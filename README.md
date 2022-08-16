# Самоконтроль выполненения задания

1. Где расположен файл с `some_fact` из второго пункта задания?
2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?
3. Какой командой можно зашифровать файл?
4. Какой командой можно расшифровать файл?
5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?
6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?
7. Как называется модуль подключения к host на windows?
8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh
9. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?

## Решение
1. Файл расположен по пути `group_vars/all/examp.yml`
2. `ansible-playbook -i inventory/test.yml site.yml`
3. `ansible-vault encrypt group_vars/el/examp.yml`
4. `ansible-vault decrypt group_vars/el/examp.yml`
5. Содержимое зашифрованного файла без команды расшифровки можно посмотреть так: `ansible-vault view group_vars/el/examp.yml`
6. Необходимо добавить параметр `--ask-vault-pass` команде запуска playbook'а: `ansible-playbook -i inventory/prod.yml site.yml --ask-vault-pass`
7. Модуль подключения к host на windows называется `winrm`
8. Полный текст команды: `ansible-doc -t connection ssh`
9. Для определения пользователя, под которым необходимо совершать подключение, необходимо использовать параметр `remote_user`