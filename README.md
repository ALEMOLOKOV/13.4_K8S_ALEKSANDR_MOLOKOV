# 13.4_K8S_ALEKSANDR_MOLOKOV

### Задание 1. Создайте конфигурацию для подключения пользователя

Создайте и подпишите SSL-сертификат для подключения к кластеру.

Настройте конфигурационный файл kubectl для подключения.

Создайте роли и все необходимые настройки для пользователя.

Предусмотрите права пользователя. Пользователь может просматривать логи подов и их конфигурацию (kubectl logs pod <pod_id>, kubectl describe pod <pod_id>).

Предоставьте манифесты и скриншоты и/или вывод необходимых команд.

### Ответ

#### Активация rbac ( управления доступом, основанное на ролях)

![enable rbac](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/697e5db9-1493-45be-a114-4da65b1edb99)

### Задание выполнено в namespace my-ns
#### Создание пользователя

![add user](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/fde68f5b-109b-4201-ac2e-f60ebbb1ed4f)

#### Генерация rsa
![gen rsa](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/55a0644b-370a-4f27-ba64-3574a92e2c38)

#### Генерация ssl

![gen ssl](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/0862a376-bda2-4d3f-95af-d064fa75afbb)

#### Создание контекста

![create context](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/ef057868-feb0-4d63-998f-75d2778cc749)

#### Config файл

![config после изменений](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/b75545f4-54ee-4166-8828-b0209af8335e)

#### Создаем объекты
![Deployment](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/blob/13c2f4c64ba89d7cb7896c094ba4e0b20806d9f7/deployment.yaml)

![Role](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/blob/13c2f4c64ba89d7cb7896c094ba4e0b20806d9f7/role.yaml)

![RoleBinding](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/blob/13c2f4c64ba89d7cb7896c094ba4e0b20806d9f7/rolebinding.yaml)

#### Статусы объектов

![статус всех объектов](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/e3d47a6b-b325-4f8e-b73a-70516ae7d4c1)

#### Проверка доступности подов вне namespace my-ns

![запрет просомтра подов ](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/269cc7de-4a1c-40d0-97c7-a7adb807b07e)

#### Проверка доступности подов в namespace my-ns

![доступность логов и describe](https://github.com/ALEMOLOKOV/13.4_K8S_ALEKSANDR_MOLOKOV/assets/109212419/55aee51e-8ccb-4184-85ec-547dc3a9e726)










