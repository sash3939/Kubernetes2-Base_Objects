# Домашнее задание к занятию «Базовые объекты K8S»

### Цель задания

В тестовой среде для работы с Kubernetes, установленной в предыдущем ДЗ, необходимо развернуть Pod с приложением и подключиться к нему со своего локального компьютера. 

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключенным Git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. Описание [Pod](https://kubernetes.io/docs/concepts/workloads/pods/) и примеры манифестов.
2. Описание [Service](https://kubernetes.io/docs/concepts/services-networking/service/).

------

### Задание 1. Создать Pod с именем hello-world

1. Создать манифест (yaml-конфигурацию) Pod.

[pod.yaml](https://github.com/sash3939/Kubernetes2-Base_Objects/blob/main/pod.yaml)

kubectl apply -f pod.yaml

2. Использовать image - gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Подключиться локально к Pod с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

Проверка созданного пода
kubectl get pod

<img width="646" alt="Connect to Pod" src="https://github.com/user-attachments/assets/9ff528bf-da0e-437e-907b-bfaed10ebafe">

<img width="793" alt="Pods in console" src="https://github.com/user-attachments/assets/4b6f1744-8b1e-4055-b6af-e509e531da9d">

------

### Задание 2. Создать Service и подключить его к Pod

1. Создать Pod с именем netology-web.

[netology-web.yaml](https://github.com/sash3939/Kubernetes2-Base_Objects/blob/main/netology-web.yaml)

<img width="314" alt="2 Pods" src="https://github.com/user-attachments/assets/b03bcb85-41c4-4ed5-b55a-d1a1234e935d">

2. Использовать image — gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Создать Service с именем netology-svc и подключить к netology-web.

[netology-svc.yaml](https://github.com/sash3939/Kubernetes2-Base_Objects/blob/main/netology-svc.yaml)

<img width="329" alt="Service" src="https://github.com/user-attachments/assets/8257b330-0c7c-409d-9d5a-2b1f3391807e">

<img width="392" alt="Service status" src="https://github.com/user-attachments/assets/148a3981-2b85-44ab-83d2-6317f97933bd">

4. Подключиться локально к Service с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

kubectl port-forward services/netology-svc 8081:8080


<img width="479" alt="Port forward" src="https://github.com/user-attachments/assets/3ddb78e4-c2b3-432f-994e-c36e5a7b57bd">

<img width="479" alt="Port forward" src="https://github.com/user-attachments/assets/7f43d2b9-d081-44b0-a9be-8b1bb340d4a3">

<img width="444" alt="Web service" src="https://github.com/user-attachments/assets/f83edba5-d850-4da5-979a-06f412fd78c4">

<img width="490" alt="curl service" src="https://github.com/user-attachments/assets/2c9b3d7a-e234-4101-b3a9-dc5e82f7ea8a">

------

### Правила приёма работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода команд `kubectl get pods`, а также скриншот результата подключения.
3. Репозиторий должен содержать файлы манифестов и ссылки на них в файле README.md.

------

### Критерии оценки
Зачёт — выполнены все задания, ответы даны в развернутой форме, приложены соответствующие скриншоты и файлы проекта, в выполненных заданиях нет противоречий и нарушения логики.

На доработку — задание выполнено частично или не выполнено, в логике выполнения заданий есть противоречия, существенные недостатки.
