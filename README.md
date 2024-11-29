# ansible_base
# Основная часть
1) Попробуйте запустить playbook на окружении из test.yml, зафиксируйте какое значение имеет факт some_fact для указанного хоста при выполнении playbook'a.
2) Найдите файл с переменными (group_vars) в котором задаётся найденное в первом пункте значение и поменяйте его на 'all default fact'.
3) Воспользуйтесь подготовленным (используется docker) или создайте собственное окружение для проведения дальнейших испытаний.
4) Проведите запуск playbook на окружении из prod.yml. Зафиксируйте полученные значения some_fact для каждого из managed host.
5) Добавьте факты в group_vars каждой из групп хостов так, чтобы для some_fact получились следующие значения: для deb - 'deb default fact', для el - 'el default fact'.
6) Повторите запуск playbook на окружении prod.yml. Убедитесь, что выдаются корректные значения для всех хостов.
7) При помощи ansible-vault зашифруйте факты в group_vars/deb и group_vars/el с паролем netology.
8) Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль. Убедитесь в работоспособности.
9) Посмотрите при помощи ansible-doc список плагинов для подключения. Выберите подходящий для работы на control node.
10) В prod.yml добавьте новую группу хостов с именем local, в ней разместите localhost с необходимым типом подключения.
11) Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль. Убедитесь что факты some_fact для каждого из хостов определены из верных group_vars.

# Ответы на задания

1) Факт some_fact имеет значение 12.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%201.PNG)

2) Назначение нового значения some_fact.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%202.PNG)

3) Запуск окружения.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%203.PNG)

4) Запуск playbook на окружении prod.yml.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%204.PNG)

Значение some_fact для managed host "ubuntu" deb.
Значение some_fact для managed host "centos7" el.

5) Новые факты в group_vars для групп хостов.
6) Повторный запуск playbook на окружении prod.yml.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%206.PNG)

Значение some_fact для managed host "ubuntu" deb default fact.
Значение some_fact для managed host "centos7" el default fact.

7) Шифрование фактов с помощью ansible-vault

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%207.PNG)

8) Запуск playbook с окружением prod.yml и ключом --ask-vault-pass для запроса пароля шифрования.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%208.PNG)

9) Для подключения к control node выбран плагин local.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%209.PNG)

10) Новая группа хостов с именем local в prod.yml.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%2010.PNG)

11) Запуск playbook на окружении prod.yml.

![alt text](https://github.com/stepanovsa061/ansible_base/blob/main/Ansible%2011.PNG)

Значение some_fact для managed host "ubuntu" deb default fact.
Значение some_fact для managed host "centos7" el default fact.
Значение some_fact для managed host "localhost" all default fact.



