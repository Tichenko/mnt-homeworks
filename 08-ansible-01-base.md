# Домашнее задание к занятию "08.01 Введение в Ansible"

## Подготовка к выполнению
1. Установите ansible версии 2.10 или выше.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/9faca369-242c-48bb-87ed-737220d7a73c)

2. Создайте свой собственный публичный репозиторий на github с произвольным именем.
3. Скачайте [playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.
 
## Основная часть  
1. Попробуйте запустить playbook на окружении из `test.yml`, зафиксируйте какое значение имеет факт `some_fact` для указанного хоста при выполнении playbook'a.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/456f57b8-ecd8-4cea-9551-3b16b24a573b)

2. Найдите файл с переменными (group_vars) в котором задаётся найденное в первом пункте значение и поменяйте его на 'all default fact'.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/ad8d9a0a-e3b2-4453-a18c-d09a344e08c2)

3. Воспользуйтесь подготовленным (используется `docker`) или создайте собственное окружение для проведения дальнейших испытаний.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/428a324b-2593-4f8d-9806-d01d93dd25a4)

4. Проведите запуск playbook на окружении из `prod.yml`. Зафиксируйте полученные значения `some_fact` для каждого из `managed host`.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/b0edcf98-5dcc-4da9-8306-67c7946e90ff)


5. Добавьте факты в `group_vars` каждой из групп хостов так, чтобы для `some_fact` получились следующие значения: для `deb` - 'deb default fact', для `el` - 'el default fact'.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/90439a35-b0b1-4e9d-bc4e-7a05dbe5d855)

6. Повторите запуск playbook на окружении `prod.yml`. Убедитесь, что выдаются корректные значения для всех хостов.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/f64150c7-0508-4cd9-8ef2-0eda0a6751bc)

7. При помощи `ansible-vault` зашифруйте факты в `group_vars/deb` и `group_vars/el` с паролем `netology`.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/8672e400-f4f8-4fec-9916-3d3ceca42d4e)

8. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь в работоспособности.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/f93dc7b0-71b2-42a5-bbe4-f375424cebe2)


9. Посмотрите при помощи `ansible-doc` список плагинов для подключения. Выберите подходящий для работы на `control node`.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/83806ce3-fb3f-41e6-9003-fada153f030d)

10. В `prod.yml` добавьте новую группу хостов с именем  `local`, в ней разместите localhost с необходимым типом подключения.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/2473827c-0879-403a-a84e-d6b03b49291f)

11. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь что факты `some_fact` для каждого из хостов определены из верных `group_vars`.

![image](https://github.com/Tichenko/mnt-homeworks/assets/116817153/2af8d747-aabd-48a4-9663-d80670578264)

12. Заполните `README.md` ответами на вопросы. Сделайте `git push` в ветку `master`. В ответе отправьте ссылку на ваш открытый репозиторий с изменённым `playbook` и заполненным `README.md`.


## Необязательная часть

1. При помощи `ansible-vault` расшифруйте все зашифрованные файлы с переменными.
2. Зашифруйте отдельное значение `PaSSw0rd` для переменной `some_fact` паролем `netology`. Добавьте полученное значение в `group_vars/all/exmp.yml`.
3. Запустите `playbook`, убедитесь, что для нужных хостов применился новый `fact`.
4. Добавьте новую группу хостов `fedora`, самостоятельно придумайте для неё переменную. В качестве образа можно использовать [этот](https://hub.docker.com/r/pycontribs/fedora).
5. Напишите скрипт на bash: автоматизируйте поднятие необходимых контейнеров, запуск ansible-playbook и остановку контейнеров.
6. Все изменения должны быть зафиксированы и отправлены в вашей личный репозиторий.

---

### Как оформить ДЗ?

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

