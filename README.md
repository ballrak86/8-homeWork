## Описание файлов в директории
logFileFull.log - полный лог выполнения  
used_commands.txt - команды которые использовал  

Vagrant_folder - все что понадобится для поднятия VM и краткое описание файлов в ней  
Vagrantfile - вагрант файл  

## Описание как запустить виртуальную машину (кратко)
Выполнить команду
```
vagrant up
```
Зайти на ВМ и выполнить нужные комманды  

1. Написать сервис, который будет раз в 30 секунд мониторить лог на предмет наличия ключевого слова. Файл и слово должны задаваться в /etc/sysconfig
```
systemctl start watchlog.timer watchlog; systemctl status watchlog.timer; tail -f /var/log/messages
```
2. Из epel установить spawn-fcgi и переписать init-скрипт на unit-файл. Имя сервиса должно также называться.
```
systemctl start spawn-fcgi; systemctl status spawn-fcgi
```
3. Дополнить юнит-файл apache httpd возможностью запустить несколько инстансов сервера с разными конфигами
```
systemctl start httpd@first httpd@second; ss -tnulp | grep httpd
```

# VagrantFile 
Указал свой vagrant Cloud с подготовленным box файлом  
config.vm.box = "alenchik/systemd"