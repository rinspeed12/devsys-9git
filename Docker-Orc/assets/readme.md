
# Netology Homework (Ivan Kurlykov DevSys-14)

## Задача 1 (Packer)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/packer-1.PNG)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/packer-2.PNG)
  


## Задача 2 (Terraform)

Изначально я сделал только одну ноду, потом решил сделать **Задачу 4**, поэтому в дальнейших скринах ip могут отличаться. На всякий случай прикладываю все скриншоты.

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/terraform-1.PNG)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/terraform-2.PNG)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/terraform-3.PNG)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/terraform-4.PNG)


## Задача 3 (Grafana)

![enter image description here](https://raw.githubusercontent.com/rinspeed12/devsys-9git/main/Docker-Orc/assets/grafana-1.PNG)

## Задача 4 (Prometheus)

![enter image description here](https://github.com/rinspeed12/devsys-9git/blob/main/Docker-Orc/assets/prom-ds-all.PNG?raw=true)

![enter image description here](https://github.com/rinspeed12/devsys-9git/blob/main/Docker-Orc/assets/prom-ds-config.PNG?raw=true)

![enter image description here](https://github.com/rinspeed12/devsys-9git/blob/main/Docker-Orc/assets/Prom-ds-local.PNG?raw=true)

![enter image description here](https://github.com/rinspeed12/devsys-9git/blob/main/Docker-Orc/assets/Prom-ds-node2.PNG?raw=true)

**С чем столкнулся:**

- Был отрицательный баланс в Яндекс Облаке
- Необходимо было сгенерировать токен в Яндекс Облаке
- Пока не привязал карту к аккаунту и не создал сервисный аккаунт был ***Permission denied***
- Т.к. задачу с Terraform выполнял с Windows, Ansible не смог потом авторизоваться по RSA ключу, переделывал с ОС Linux
- Когда выполнял 4ю задачу, случайно грохнул первую ноду - не доглядел за переменными :)
- Устарела версия git, протух токен

В целом тема очень крутая, было интересно! Спасибо!

## Спасибо за проверку!
