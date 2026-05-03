University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Eliseeva Polina Fedorovna\
Lab: Lab1\
Date of create: 24.04.2026\
Date of finished: 

# Лабораторная работа №1
## Обзор Google Cloud и исследование основных сервисов

## Цель работы

Ознакомиться с основными возможностями платформы Google Cloud, изучить сервисы IAM, Compute Engine и Cloud Storage, а также проверить влияние ролей доступа на работу с ресурсами.

## Ход работы

### 1. Получение доступа к Google Cloud

Была заполнена форма для получения доступа к Google Cloud. После этого был открыт доступ к проекту.

---

### 2. Создание Service Account

Был создан сервисный аккаунт:

`peliseeva-sa-lab1`

Аккаунту была назначена роль:

`Storage Admin`

<img width="800" alt="image" src="https://github.com/user-attachments/assets/e5f873ab-0cea-4254-bcbd-943595cbb66b" />

<img width="800" alt="image" src="https://github.com/user-attachments/assets/4a219ca9-7852-4b99-a9fc-b724992881c4" />

---

### 3. Создание виртуальной машины

Была создана виртуальная машина:

`peliseeva-vm-lab1`

Параметры:

- Machine type: e2-micro  
- Provisioning model: Spot  

Виртуальная машина была успешно запущена.

<img width="1280" height="675" alt="image" src="https://github.com/user-attachments/assets/dfd91bd2-f6fa-490f-8f68-539d6d84597f" />

---

### 4. Подключение к VM и работа с Cloud Storage

Подключение к виртуальной машине было выполнено через SSH. С помощью утилиты gcloud найден бакет lab1-bucket-itmo и скопированы 3 файла в локальную папку на VM. Командой ls -lah проверила наличие файлов на VM.

<img width="1067" height="533" alt="image" src="https://github.com/user-attachments/assets/6fe15f17-980e-43ce-a9ea-29c585ce2ef4" />

### 5. Смена роли и проверка доступа

Поменяла права доступа для моего service account с Storage Admin на Compute Viewer и попробовала скопировать файлы снова. Вышла ошибка, у service account отсутствуют права на доступ к объектам Cloud Storage.

<img width="1069" height="869" alt="image" src="https://github.com/user-attachments/assets/ec565d23-dee1-460a-831f-b651ce4a231b" />

<img width="1090" height="164" alt="image" src="https://github.com/user-attachments/assets/4c4d97fe-0f1d-4863-bd79-765a580b0e14" />

## Итоговый вывод

После изменения роли service account с Storage Admin на Compute Viewer доступ к объектам Cloud Storage был ограничен. Попытка скачать файл из бакета завершилась ошибкой 403, что подтверждает отсутствие необходимых прав.

Таким образом, IAM-роли напрямую влияют на доступ к ресурсам Google Cloud, и без соответствующих разрешений выполнение операций с Cloud Storage невозможно.
