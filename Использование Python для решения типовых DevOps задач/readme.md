# Netology Homework (Ivan Kurlykov DevSys-9)

## Задание 1

1) Будет ошибка, т.к. типы не соответсвуют для операции , int и str
2) Привести a к строке:       c=str(a)+b
3) Привести b к целому числу: c=a+int(b)

## Задание 2

Переменная is_change и команда breake лишние
    
    #!/usr/bin/env python3
    
    import os
    
    bash_command = ["cd ~/devops9-netology", "git status"]
    result_os = os.popen(' && '.join(bash_command)).read()
    for result in result_os.split('\n'):
        if result.find('изменено') != -1:
            prepare_result = result.replace('\tизменено:   ', '')
            print(prepare_result)
## Задание 3

    #!/usr/bin/env python3
    
    import os
    import sys
    
    cmd = sys.argv[1]
    bash_command = ["cd "+cmd, "git status"]
    result_os = os.popen(' && '.join(bash_command)).read()
    for result in result_os.split('\n'):
        if result.find('изменено') != -1:
            prepare_result = result.replace('\tизменено: ', '')
            prepare_result = prepare_result.replace(' ', '') 
            print(cmd+prepare_result)



## Задание 4

Дополнил вывод временем, и инициализацией 1й итерации без проверки

    #!/usr/bin/env python3
    
    import socket as s
    import time as t
    import datetime as dt
    
    # set variables 
    i = 1
    wait = 2 # Интервал проверок в секундах
    srv = {'drive.google.com':'0.0.0.0', 'mail.google.com':'0.0.0.0', 'google.com':'0.0.0.0'}
    init=0
    
    print('*** start script ***')
    print(srv)
    print('********************')
    
    while 1==1 : # Число проверок 
      for host in srv:
        ip = s.gethostbyname(host)
        if ip != srv[host]:
          if i==1 and init !=1:
            print(str(dt.datetime.now().strftime("%Y-%m-%d %H:%M:%S")) +' [ERROR] ' + str(host) +' IP mistmatch: '+srv[host]+' '+ip)
          srv[host]=ip
    # Счетчик для отладки, закомментировать для бесконечного цикла 3й строки
      i+=1 
      if i >= 50 : 
        break
      t.sleep(wait)

## Thank you for checking!
