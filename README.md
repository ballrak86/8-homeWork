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
```
systemctl start watchlog.timer watchlog; systemctl status watchlog.timer; tail -f /var/log/messages

systemctl start spawn-fcgi; systemctl status spawn-fcgi

systemctl start httpd@first httpd@second; ss -tnulp | grep httpd
```

# VagrantFile 
Указал свой vagrant Cloud с подготовленным box файлом
config.vm.box = "alenchik/systemd"