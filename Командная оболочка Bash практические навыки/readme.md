# Netology Homework (Ivan Kurlykov DevSys-9)

## Задание 1

- c = a+b. Во-первых строка, во-вторых нет знаков переменных, в-третьих нет двойных круглых скобок
- d = 1+2. Таже самая ситуация, что и с "c", только здесь уже передана информация о переменных ($)
- e = 3. Завершенное выражение. Здесь передана информация о переменных, установлены двойные круглые скобки, благодаря чему переменые считаются integer и складываются.

## Задание 2
    Немного переделал скрипт, т.к. проверял Яндекс и случайный домен.

 #### Что было изменено:
    1) Добавил круглую скобку, которой не хватало в выражении while
    2) К curl добавил -k чтобы отключить проверку сертификата
    3) Дописал сообщения вывода чтобы они были более читабельны
    4) Добавил блок с проверкой
    5) В блок с проверкой добавил break, чтобы проверка сервиса завершалась, как только url станет доступным

#### Код 
    #!/bin/bash
    while ((1==1))
    do
    curl -k https://yandex.ru
    if (($? != 0))
    then
    echo "$(date) Service not avaibled" >> curl.log
    else
    echo "$(date) Service avaibled" >> curl.log
    break
    fi
    done

## Задание 3
    #!/bin/bash
    array_ip=(192.168.0.1 173.194.222.113 87.250.250.242)
    for i in ${array_ip[@]}
    do
    curl -k -f --retry 5 --connect-timeout 1 http://$i
    if (($? != 0))
    then
    echo "$(date) Host $i is not avaibled" >> curl2.log
    else
    echo "$(date) Host $i is now avaibled" >> curl2.log
    fi
    done

## Задание 4
Здесь заменил != на ==, поменял местами тексты сообщений, файл лога, добавил break.

    #!/bin/bash
    array_ip=(192.168.0.1 173.194.222.113 87.250.250.242)
    for i in ${array_ip[@]}
    do
    curl -k -f --retry 5 --connect-timeout 1 http://$i
    if (($? == 0))
    then
    echo "$(date) Host $i is now avaibled" >> curl3.log
    else
    echo "$(date) Host $i is not avaibled" >> error
    break
    fi
    done


    
## Thank you for checking!
