## Задание 1

В данном задании представлен [Ansible-playbook](https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/site.yml), устанавливающий на удаленной машине следующие программное обеспечение:
- **Сервер БД PostgreSQL 14**
- [**Средство управления PGAdmin**](http://46.146.220.219/pgadmin4)
     - Логин: `mail@domain.com`
     - Пароль: `e84XpAk5`
- **Скрипты резервного копирования и обслуживания баз**:
     - [*Запланированные задания по обслуживанию баз**:](https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/templates/backup_cron.sh.j2)
          - [резервное копирование баз, в каждую глухую полночь](https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/templates/psql_backup.sh.j2), 
          - через час после начала резервного копирования с сервера начинают таинственно исчезать бэкапы старше 7 дней (см. скрипт планировщика) 
          - [в 9 утра по воскресеньям запускает светлый обряд реиндексации и сборки мусора для рабочей базы test_db](https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/templates/psql_reindex_vacuum.sh.j2).
- [**Средство мониторинга pgDash**](https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/templates/pgdash_setup.sh.j2)       
     - Логин: `gregory78@yandex.ru`
     - Пароль: `e84XpAk5`
     
     
     https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/pg_dash.png
     https://github.com/GrigoriyAzatyan/test-task/blob/master/Task%201/pgadmin.png
