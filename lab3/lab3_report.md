University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Eliseeva Polina Fedorovna\
Lab: Lab1\
Date of create: 03.05.2026\
Date of finished: 

## Лабораторная работа №3  
**Тема:** Исследование Cloud Storage  

---

## Цель работы  
Ознакомиться с основными принципами работы облачного хранилища, изучить объектное хранение данных и получить практические навыки работы с Google Cloud Storage.

---

## Ход работы  

### 1. Создание Cloud Storage bucket  
Был создан bucket со следующими параметрами:

- Имя: `lab3-0305`  
- Регион: Multi-region (US)  
- Класс хранения: Standard  
- Тип доступа: Uniform

<img width="700" src="https://github.com/user-attachments/assets/cdda9d13-845c-4d93-bb3d-d245b06bc59d" />

---

### 2. Загрузка файлов  
В созданный bucket было загружено 4 изображения формата `.jpg`.

<img width="600" src="https://github.com/user-attachments/assets/8d941c0d-c946-41db-bcb7-9027a0b2c791" />

---

### 3. Создание папки и перемещение файлов  
Внутри bucket была создана папка `tie`, после чего все изображения были перемещены в неё.

<img width="700" src="https://github.com/user-attachments/assets/2fabd865-ec15-48af-9028-b5c8008fd6e2" />


---

### 4. Настройка публичного доступа  
Для обеспечения публичного доступа был выполнен следующий шаг:

- Добавлен: `allUsers`  
- Назначена роль: `Storage Object Viewer`  

Это позволило предоставить доступ к файлам только на чтение без возможности их изменения.

<img width="700" src="https://github.com/user-attachments/assets/ed429c12-7a56-473c-bfbe-16937a856ac3" />

---

### 5. Получение ссылки на файл  
Ссылка на файл была получена через контекстное меню объекта

Пример ссылки: https://storage.googleapis.com/lab3-0305/tie/_MG_3983.jpg

Ссылка была открыта в браузере, изображение успешно загрузилось

<img width="700" src="https://github.com/user-attachments/assets/07488194-6542-4f6e-98c8-f98e08026559" />

<img width="700" src="https://github.com/user-attachments/assets/0b90492e-5257-4948-9a5e-6aa74ea7cb13" />


### 6. Удаление ресурсов  
После завершения работы:

- все файлы были удалены  
- bucket `lab3-0305` был удалён  

---

## Вывод  

В ходе лабораторной работы были изучены основные принципы работы объектного хранилища Google Cloud Storage. Был создан bucket, загружены и структурированы файлы, настроен публичный доступ через IAM, а также получена и проверена публичная ссылка на объект.  
