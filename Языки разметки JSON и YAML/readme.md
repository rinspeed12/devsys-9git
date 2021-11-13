# Netology Homework (Ivan Kurlykov DevSys-9)

## Задание 1
Не хватало кавычки в строке 9

     1: { "info" : "Sample JSON output from our service\t",
     2:     "elements" :[
     3:         { "name" : "first",
     4:         "type" : "server",
     5:         "ip" : 7175 
     6:         },
     7:         { "name" : "second",
     8:         "type" : "proxy",
     9:         "ip": "71.78.22.43"
    10:         }
    11:     ]
    12: }

## Задание 2

    #!/usr/bin/env python3
    
    import socket as s
    import time as t
    import datetime as dt
    import json
    import yaml
    
    # set variables 
    i     = 1
    wait  = 2 # Интервал проверок в секундах
    srv   = {'drive.google.com':'0.0.0.0', 'mail.google.com':'0.0.0.0', 'google.com':'0.0.0.0'}
    init  = 0
    fpath = "/home/ikurlykov/python/" #Путь к конфигам
    flog  = "/home/ikurlykov/python/error.log" #Путь к логам
    
    # start script workflow
    print('*** start script ***')
    print(srv)
    print('********************')
    
    while 1 == 1 : # Для бесконечного цикла, else  установить условие i >= чилу треуемых итераций
      for host in srv:
        is_error = False 
        ip = s.gethostbyname(host)
        if ip != srv[host]:
          if i==1 and init !=1: # Выводим ошибку, если нет инициализации или есть иниц. и не первый шаг
            is_error=True
            # Вывод ошибок в файл
            with open(flog,'a') as fl:
              print(str(dt.datetime.now().strftime("%Y-%m-%d %H:%M:%S")) +' [ERROR] ' + str(host) +' IP mistmatch: '+srv[host]+' '+ip,file=fl)
            # В отдельные файлы
            # json
            with open(fpath+host+".json",'w') as jsf:
              json_data= json.dumps({host:ip})
              jsf.write(json_data) 
            # yaml
            with open(fpath+host+".yaml",'w') as ymf:
              yaml_data= yaml.dump([{host : ip}])
              ymf.write(yaml_data) 
        # В один общий файл     
        if is_error:
          data = []  
          for host in srv:  
            data.append({host:ip})
          with open(fpath+"services_conf.json",'w') as jsf:
            json_data= json.dumps(data)
            jsf.write(json_data)
          with open(fpath+"services_conf.yaml",'w') as ymf:
            yaml_data= yaml.dump(data)
            ymf.write(yaml_data)
            #^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
          srv[host]=ip
      #print(i) # Выводим шаг итерации для отладки
      i+=1 # Счетчик итераций для отладки, закомментировать для бесконечного цикла
      if i >=50 : # Число итераций для выхода из цикла для отладки
        break
      t.sleep(wait) # Задержка на итерации 

## Thank you for checking!
