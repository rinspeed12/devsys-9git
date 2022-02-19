
# Netology Homework (Ivan Kurlykov DevSys-14)

## Задача 1



**docker-compose.yml:**

    web:
      image: nginx
      container_name: nginx-netology
      volumes:
       - ./html:/usr/share/nginx/html
      ports:
       - "8080:80"
      environment:
       - NGINX_HOST=localhost
       - NGINX_PORT=80

**Dockerfile**

    FROM nginx
    COPY ./html /usr/share/nginx/html


**Ссылка:** https://hub.docker.com/repository/docker/rinspeed777/nginx-netology
  


## Задача 2

-   **Высоконагруженное монолитное java веб-приложение**; - физическая машина, т.к. монолит и highload.
-   **Nodejs веб-приложение**; - можно упаковать в контейнер. удобно будет реализовать сборку и деплой приложения.
-   **Мобильное приложение c версиями для Android и iOS**; Не было опыта, но кажется, что виртуальная машина,  моб.прил. с двумя версиями ос. Хотя возможно, можно реализовать в контейнерах.
-   **Шина данных на базе Apache Kafka**; - не было опыта, его используют в кубере, значит можно реализовать в контейнере
-   **Elasticsearch кластер для реализации логирования продуктивного веб-приложения - три ноды elasticsearch, два logstash и две ноды kibana**; Раз над несколько и кластер - можно реализовать в контейнере в docker swarm или k8s. Однако хранилища необходимо примонтировать как volume. Также можно использовать GlusterFS или аналоги.
-   **Мониторинг-стек на базе Prometheus и Grafana**; Можно использовать в контейнерах (на работе делаем так). Приложения написаны на GO и почти ничего не весят.
-   **MongoDB, как основное хранилище данных для java-приложения**; Можно использовать монолотик, или же запускать в контейнерах, однако в случае с контейнером, необходимо примонтировать volume.
-   **Gitlab сервер для реализации CI/CD процессов и приватный (закрытый) Docker Registry** - я бы использовал монолит, в крайнем случае виртуализацию типа vmware, т.к. предполагается большое количество места, пользователей и высокая нагрузка.

## Задача 3

**docker-compose.yml**

    centos:
      image: centos
      container_name: centos-netology
      volumes:
       - ./data:/data
      command: "/usr/sbin/init"
    debian:
      image: debian
      container_name: debian-netology
      volumes:
       - ./data:/data
      command: "sleep infinity"

Заходим в контейнер после запуска:

    ikurlykov@Stream-HP-ProBook-440-G4:~/Документы/Нетология/Docker/z3$ docker exec -it debian-netology /bin/bash

root@0d8be51738f5:/# cd /data/
root@0d8be51738f5:/data# ls -l

total 8
-rw-r--r-- 1 root root 17 Feb 19 11:31 centos-file.txt
-rw-rw-r-- 1 1000 1000 10 Feb 19 11:32 host-file.txt

## Задача 4

 **Ссылка:**  [Ansible ](https://hub.docker.com/repository/docker/rinspeed777/ansible-netology)

## Спасибо за проверку!
