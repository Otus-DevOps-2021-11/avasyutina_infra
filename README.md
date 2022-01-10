# avasyutina_infra
avasyutina Infra repository

# Знакомство с облачной инфраструктурой. Yandex.Cloud
someinternalhost_IP = 10.128.0.11
bastion_IP = 62.84.126.2

способ подключения к someinternalhost в одну команду
ssh -i ~/.ssh/appuser -A appuser@62.84.126.2 ssh -tt appuser@10.128.0.11

команда генерации ключенй для пользователя appuser
ssh-keygen -t rsa -f ~/.ssh/appuser -C appuser -P ""

поджключение к созданной ВМ
ssh -i ~/.ssh/appuser appuser@62.84.126.2
ssh -i ~/.ssh/appuser -A appuser@62.84.126.2

Настройка SSH Forwarding
$ ssh-add -L
The agent has no identities.
Если данная комманда не верный ответ выполнить команду:  eval `ssh-agent`

Добавть приватный ключ в ssh агент авторизации (выполняла с ubuntu):
$ ssh-add ~/.ssh/appuser
Identity added: /home/otus/.ssh/appuser (/home/otus/.ssh/appuser)

выполнение команд setupvpn.sh.(sudo позволяет разрешенному пользователю выполнять команду как суперпользователь)
$ sudo bash setupvpn.sh

# Деплой тестового приложения

testapp_IP = 62.84.113.170
testapp_port = 9292

yc compute instance create \
  --name reddit-app \
  --hostname reddit-app \
  --memory=4 \
  --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB \
  --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
  --metadata serial-port-enable=1 \
  --metadata-from-file user-data=./metadata.yml