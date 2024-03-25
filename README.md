# Домашнее задание к занятию 2 «Работа с Playbook» - Подус Сергей

## Основная часть

1. Подготовьте свой inventory-файл `prod.yml`.
2. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает [vector](https://vector.dev). Конфигурация vector должна деплоиться через template файл jinja2. От вас не требуется использовать все возможности шаблонизатора, просто вставьте стандартный конфиг в template файл. Информация по шаблонам по [ссылке](https://www.dmosk.ru/instruktions.php?object=ansible-nginx-install). не забудьте сделать handler на перезапуск vector в случае изменения конфигурации!
3. При создании tasks рекомендую использовать модули: `get_url`, `template`, `unarchive`, `file`.
4. Tasks должны: скачать дистрибутив нужной версии, выполнить распаковку в выбранную директорию, установить vector.
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
9. Подготовьте README.md-файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги. Пример качественной документации ansible playbook по [ссылке](https://github.com/opensearch-project/ansible-playbook). Так же приложите скриншоты выполнения заданий №5-8
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-02-playbook` на фиксирующий коммит, в ответ предоставьте ссылку на него.

## Ответ:

1. Был дописан inventory файл:

![Скриншот 1](https://github.com/Wanderwille/scrinshot/blob/main/ansible2-prod.png)

5. При запуске `ansible-lint site.yml` были обнаружены ошибки, в файле было много пустых строк и ошибка "Есть задача, которая изменяет что-то, даже если ничего не нужно делать."

![Скриншот 2](https://github.com/Wanderwille/scrinshot/blob/main/anible2-lint.png)

После исправления ошибок 

![Скриншот 3](https://github.com/Wanderwille/scrinshot/blob/main/ansible2%20-%20lint()UPD.png)

6. Запуск playbook с параметром --check

![Скриншот 4](https://github.com/Wanderwille/scrinshot/blob/main/ansible2.1-check.png)

7. Запуск playbook с параметром --diff

![Скриншот 5](https://github.com/Wanderwille/scrinshot/blob/main/ansible-vector.png)

8. Повторный запуск playbook с параметром --diff

![Скриншот 6](https://github.com/Wanderwille/scrinshot/blob/main/ansible-vector2.png)

9. Файл README.md 