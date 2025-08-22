# Ansible.node
___
ansible.node - инструмент автоматизации деплоя и релизного управления `node`'ами с использованием Ansible.
## Требования:
Установить ansible версии 2.18.4 или выше.
## Структура проекта:
```text
ansible.node/
├── inventories/              # Инвентарные файлы (hosts)
│   └── deploy.ini
├── playbooks/                # Плейбуки Ansible
│   └── setupNodeServer.yaml
├── roles/                    # Ansible-роли
│   ├── setupDependencies     # Установка базовых пакетов
│   ├── setupNetworkd         # Настройка systemd-netword (Сеть, локальный DNS)
│   └── setupResolved         # Настройка systemd-resolved
├── vars/                     # Переменные окружений
└── README.md
```
## Использование:
1. Убедитесь, что настроен SSH-доступ к целевым серверам.
2. Заполните файл inventory - список хостов.
3. Заполните файл vars - переменные окружений.

Для деплоя `node` выполните:
```shell
ansible-playbook playbooks/setupNodeServer.yaml
```