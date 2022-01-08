# avasyutina_infra
avasyutina Infra repository

# Знакомство с облачной инфраструктурой. Yandex.Cloud
someinternalhost_IP = 10.128.0.11
bastion_IP = 62.84.126.2

способ подключения к someinternalhost в одну команду
ssh -i ~/.ssh/appuser -A appuser@62.84.126.2 ssh -tt appuser@10.128.0.11


