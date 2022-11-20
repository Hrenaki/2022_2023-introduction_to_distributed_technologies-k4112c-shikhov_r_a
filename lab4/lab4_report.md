University: [ITMO University](https://itmo.ru/ru/) \
Faculty: [FICT](https://fict.itmo.ru) \
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies) \
Year: 2022/2023 \
Group: K4112c \
Author: Shikhov Roman Alekseevich \
Lab: Lab4 \
Date of create: 05.11.2022 \
Date of finished: 19.11.2022

- Создаем кластер с 2мя нодами и плагином CNI = calico:\
![minikube_start](images/minikube_start.png)

- Проверяем, что pod'ы calico запустились:\
![kubectl_get-pods_calico](images/kubectl_get-pods_calico.png)

- Смотрим k8s nod'ы:\
![kubectl_get-nodes](images/kubectl_get-nodes.png)

- Удаляем default ippool и создаем кастомные:\
![calicoctl_delete_default](images/calicoctl_delete_default.png)
![calicoctl_apply_manifest](images/calicoctl_apply_manifest.png)

- Помечаем соответствующими метаки ноды:\
![kubectl_nodes_label](images/kubectl_nodes_label.png)

- Создаем deployment и service NodePort:\
![kubectl_apply_deployment-manifest](images/kubectl_apply_deployment-manifest.png)

- Проверяем IP адреса созданных pod'ов deployment'а:\
![kubectl_get_deployment-pods-manifest](images/kubectl_get_deployment-pods.png)

- Делаем port-forward на созданный сервис:\
![kubectl_port-forward](images/kubectl_port-forward.png)

- Заходим на сайт по url: http://localhost:5000 :\
![site](images/site.png)

- Заходим в pod и делаем ping другого по его IP:\
![kubectl_port-forward](images/kubectl_exec_ping.png)

- Схема организации объектов:\
![object-scheme](images/object-scheme.png)
