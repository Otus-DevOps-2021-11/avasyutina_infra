# avasyutina_infra
avasyutina Infra repository

# Знакомство с облачной инфраструктурой. Yandex.Cloud
someinternalhost = 10.128.0.11 (appuser@10.128.0.11)
bastion = 62.84.126.2 (appuser@62.84.126.2)

способ подключения к someinternalhost в одну команду
$ ssh -i ~/.ssh/appuser -A appuser@62.84.126.2 ssh -tt appuser@10.128.0.11


