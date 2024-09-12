## Deploy X-UI

Плейбук для установки и предварительной конфигурации панели X-UI https://github.com/alireza0/x-ui


### Требования
1. Ubuntu 20.04 или Ubuntu 22.04 
2. Docker и docker-compose, установленные из репозиториев Ubuntu. Используется docker-compose (вместо docker compose)

### Запуск

1. Заполните Inventory inventory/inventory.ini

2. Заполните обязательные параметры в inventory/group_vars/remote_servers.yaml

| Имя параметра                | Описание параметра                             |
| :--------------------------- | ---------------------------------------------- |
| ansible_ssh_username         | имя пользователя ssh (root или с правами sudo) |
| vaulted_ansible_ssh_password | пароль пользователя ssh                        |
| web_interface_username       | имя пользователя веб интерфейса x-ui           |
| web_interface_password       | пароль пользователя веб интерфейса x-ui        |

3. Заполните необязательные параметры (иначе будут использованы значения по умолчанию)

| Имя параметра      | Описание параметра       |
| :----------------- | ------------------------ |
| web_interface_port | порт веб интерфейса x-ui |

4. Запустите плейбук командой
```
ansible-playbook main.yml 
```

5. Адрес, логин и пароль веб интерфейса x-ui будут отображены в выводе таски Print URL and credentials