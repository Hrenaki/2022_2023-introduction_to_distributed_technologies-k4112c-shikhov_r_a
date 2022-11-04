University: [ITMO University](https://itmo.ru/ru/) \
Faculty: [FICT](https://fict.itmo.ru) \
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies) \
Year: 2022/2023 \
Group: K4112c \
Author: Shikhov Roman Alekseevich \
Lab: Lab3 \
Date of create: 01.11.2022 \
Date of finished: dd.mm.2022

- Создаем манифест, содержащий указанный configMap, deployment, исплользующий значения из configMap, и сервис NodePort, открывающий доступ к pod'a deployment'a. \
Значения переменных в configMap
react_app_username: hrenaki \
react_app_company_name: itmo \

- Создаем объекты k8s командой 'kubectl apply -f manifest_lab3.yaml' \
![kubectl_apply-objects](images/kubectl_apply-objects.png)

- Посмотрим информацию в configMap:\
![kubectl_describe-configmap](images/kubectl_describe-configmap.png)

- Генерируем самоподписанный сертификат и приватный ключ:\
![openssl_cert-and-key](images/openssl_cert-and-key.png)
![openssl_cert-and-key2](images/openssl_cert-and-key2.png)

- Расшифруем сгенерированный приватный ключ:\
![openssl_decrypt-key](images/openssl_decrypt-key.png)

- Включаем аддон 'ingress':\
![minikube_enable-ingress](images/minikube_enable-ingress.png)

- По созданному сертификату и приватному ключу создаем tls секрет:\
![kubectl_create-secret](images/kubectl_create-secret.png)

- Создаем ingress с помощью манифеста 'ingress-manifest.yaml':\
![kubectl_ingress](images/kubectl_ingress.png)

- Т.к. minikube запущен на Windows, то для доступа к ingress, необходимо создать minikube tunnel. Тогда ingress станет доступен по адресу 127.0.0.1. Именно этот адрес нужно добавить в hosts, находящийся в 'C:\Windows\System32\drivers\etc'\
Добавленная строка в файл 'hosts':\
![hosts-content](images/hosts-content.png)

- minikube tunnel\
![minikube_tunnel](images/minikube_tunnel.png)

- Перейдем на сайт по FQDN 'my-itdt.hrenaki':\
![site](images/site.png)

- Откроем сведения о сертификате:\
![cert](images/cert.png)

- Браузер 'ругается' на созданный сертификат, т.к. он является самоподписанным. Иерархия сертификатов следующая:\
![cert-hierarchy](images/hierarchy.png)

- Схема организации объектов k8s:\
![objects](images/objects.png)