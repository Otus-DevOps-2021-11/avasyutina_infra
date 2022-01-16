# avasyutina_infra
avasyutina Infra repository

# Знакомство с облачной инфраструктурой. Yandex.Cloud
someinternalhost_IP = 10.128.0.11
bastion_IP = 62.84.126.2

способ подключения к someinternalhost в одну команду
ssh -i ~/.ssh/appuser -A appuser@62.84.126.2 ssh -tt appuser@10.128.0.11

# Деплой тестового приложения
testapp_IP = 51.250.13.103
testapp_port = 9292

1.установлен packer
2.создан сервисный аккаунт и делегированы права
3.создан key файл и скрипты install_ruby.sh, install_mongod.sh
4.создан образ и на его основе создана ВМ
5.проверено приложение

# terraform-1
    Установлен terraform
    Создана и настроена VM
    Создан файл с фейковыми значениями переменных
    
# terraform-2

	разбита на модули app и db конфигурация terraform
	сделаны конфигурации окружений
