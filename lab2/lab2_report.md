University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Eliseeva Polina Fedorovna\
Lab: Lab2\
Date of create: 03.05.2026\
Date of finished: 

# Лабораторная работа №2  
## Развертывание сервиса в Cloud Run

## Цель работы  
Ознакомиться с сервисом Cloud Run, изучить процесс развертывания контейнерного приложения, а также проанализировать работу сервиса с использованием логов и метрик.

## Ход работы  

### 1. Создание сервиса Cloud Run  
В рамках лабораторной работы был создан сервис в Google Cloud Run.

Для развертывания использовался контейнерный образ:
us-docker.pkg.dev/cloudrun/container/hello

Параметры сервиса:
- имя: lab2-hello  
- регион: europe-west1  
- доступ: публичный (Allow public access)  
- тип биллинга: request-based  
- масштабирование: автоматическое  

Сервис был успешно развернут и получил публичный URL.

<img width="700" src="https://github.com/user-attachments/assets/d5e182ce-3c93-4adf-a98b-26290d03ac97" />

---

### 2. Тестирование сервиса  
Был выполнен переход по URL сервиса.

Результат:
отображается страница "It's running!"

Это подтверждает, что сервис корректно работает и обрабатывает HTTP-запросы.

<img width="700" src="https://github.com/user-attachments/assets/e9b2f92a-81f8-4337-91a1-595e3f1699aa" />

---

### 3. Анализ логов  
В разделе Logs были проанализированы записи работы сервиса.

В логах зафиксировано:
- успешный запуск контейнера  
- прохождение health-check (TCP probe succeeded)  
- HTTP-запросы с кодом 200  
- сообщения о готовности ревизии  

Ошибок обнаружено не было.

<img width="700" src="https://github.com/user-attachments/assets/c4158ced-3ede-4c50-9566-248ae8c5e79c" />


---

### 4. Анализ метрик  
В разделе Metrics были проанализированы следующие показатели:
- количество запросов (Request count)  
- задержка обработки (Latency)  
- загрузка CPU и памяти  
- количество инстансов  

Вывод:
- сервис корректно масштабируется  
- нагрузка минимальная  
- задержки находятся в пределах нормы  
- ошибок нет  

<img width="1280" height="808" alt="image" src="https://github.com/user-attachments/assets/a067c71a-4562-4057-8366-7c469fd9e0fb" />
<img width="1280" height="624" alt="image" src="https://github.com/user-attachments/assets/c695f61d-3027-4427-86db-4068de1cbba0" />




---

### 5. Изменение конфигурации (порт)  
Была создана новая ревизия с изменением порта с 8080 на 8090.

<img width="1280" height="912" alt="image" src="https://github.com/user-attachments/assets/11615885-77ca-45cf-9028-ee9fdfec5a2b" />

Результат:
- сервис продолжил работать корректно  
- контейнер успешно запустился  
- ошибки отсутствуют  

Причина:
Cloud Run использует переменную окружения PORT, поэтому контейнер автоматически адаптируется к заданному порту.
<img width="1280" height="778" alt="image" src="https://github.com/user-attachments/assets/11012afa-4d42-46c5-bb92-4dc4e920df0a" />
<img width="1280" height="989" alt="image" src="https://github.com/user-attachments/assets/9b303c09-b67f-4d45-8d68-9a29df081680" />


---

### 6. Переключение трафика между версиями  
Было выполнено распределение трафика между двумя ревизиями:

- первая ревизия — 50%  
- вторая ревизия — 50%  

Результат:
- обе версии обрабатывают запросы  
- сервис остается доступным  
- ошибок не возникает  

<img width="1280" height="650" alt="image" src="https://github.com/user-attachments/assets/fceaaf8d-52e2-415b-aae7-a46708285fb3" />
<img width="1280" height="827" alt="image" src="https://github.com/user-attachments/assets/cc744189-1b4f-4067-bccf-cfdc24581b69" />
<img width="1280" height="622" alt="image" src="https://github.com/user-attachments/assets/1b260be1-a908-47fe-a41d-01a79955583a" />



---


## Вывод  
В ходе лабораторной работы был изучен сервис Cloud Run.

Были получены навыки:
- развертывания контейнерного приложения  
- тестирования сервиса  
- анализа логов и метрик  
- изменения конфигурации  
- управления версиями и трафиком  

Cloud Run позволяет быстро развертывать приложения и автоматически масштабировать их без управления инфраструктурой.
