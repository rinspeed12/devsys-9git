
# Netology Homework (Ivan Kurlykov DevSys-14)

## Задача 1

**Преимущества IaaC** 
- Отсутствие необходимости производить одни и те же действия вручную на нескольких ПК / виртуалках.

- Идемпотентность
- Если что-то случится с виртуалкой/пк, можно быстро восстановить инфраструктуру
- В случае работы с докером, он соотносит желаемое состояние инфраструктуры и текущее. В случае различия, подтягивает изменения из кода.
- Возможность реализовать CI/CD (возвращаясь к пункту 1, больше нет необходимости делать все вручную) - более быстрая и эффективная разработка
- Тестирование инфраструктуры
- Удобство масштабирования
- Отсутствие дрейфа конфигурации
  
**Основополагающие принципы IaaC**
- Процесс настройки инфраструктуры аналогичен процессу разработки программного обеспечения.

## Задача 2

- Ansible использует соединение по ssh, в то время, как другие инструменты требует настройки PKI окружения.
- На первый взгляд push, т.к. он запускает, когда мы решили, что-то запушить. Не знаю, как pull - с ним не работал, но мне кажется, что он тоже должен быть привязан к какому-нибудь action'у. Поэтому считаю, что оба подхода надежны.

## Задача 3

Virtualbox 6.1

    D:\vagrant>vagrant -v
    Vagrant 2.2.18

    vagrant@vagrant:~$ ansible --version
    ansible 2.9.6
      config file = /etc/ansible/ansible.cfg
      configured module search path = ['/home/vagrant/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
      ansible python module location = /usr/lib/python3/dist-packages/ansible
      executable location = /usr/bin/ansible
      python version = 3.8.10 (default, Jun  2 2021, 10:49:15) [GCC 9.4.0]

## Задача 4

    root@vagrant:~# docker ps
    
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    
    root@vagrant:~# docker -v
    
    Docker version 20.10.12, build e91ed57

## Спасибо за проверку!
