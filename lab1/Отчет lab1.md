University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FTMI](https://ftmi.itmo.ru)

Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/education/labs2023-2024/lab1/lab1/#_2)

Year: 2025/2026

Group: HBM

Author: Бойко Екатерина Олеговна

Lab: Lab1

Date of create: 22.11.2025

Date of finished: 01.12.2025

# Лабораторная работа 1

## Подготовка

До начала работы я заполнила Google-форму и получил доступ к проекту в Google Cloud Platform.

## Создание сервисного аккаунта

Во время лабораторной работы я создала сервисный аккаунт с ролью **Storage Admin**.  
Имя аккаунта было выбрано по формату, указанному в задании: первая буква имени и фамилия с добавлением `-sa-lab1`.

## Создание виртуальной машины

Далее я создала виртуальную машину в разделе **Compute Engine**.  
Для этого использовал минимальную конфигурацию:
- Тип машины: `e2-micro`
- Режим работы: **Spot**

<img width="982" height="894" alt="image_2025-11-28_13-15-14" src="https://github.com/user-attachments/assets/22f952b7-cc4d-4b48-b0b2-8b4d57ce2b02" />

Название виртуальной машины также соответствовало требуемому формату: первая буква имени, фамилия и `-vm-lab1`.

## Подключение и работа с файлами

После настройки машины я подключилась к ней через SSH прямо из консоли Google Cloud.  
С помощью утилиты `gsutil` я нашла бакет `lab1-bucket-itmo`, в котором были размещены необходимые файлы.

<img width="482" height="145" alt="image" src="https://github.com/user-attachments/assets/fa62f6bd-8e4f-48da-9064-99f111e40c1e" />

Для копирования файлов я:
1. Создала на виртуальной машине новую папку.
2. Скопировала туда три файла из облачного хранилища.

Проверка командой `ls` показала, что все файлы успешно скопированы и находятся на месте.
<img width="273" height="33" alt="image_2025-12-01_12-19-51" src="https://github.com/user-attachments/assets/4a83ad67-acb4-4d12-b037-597ffa137de8" />

## Изменение прав доступа

Следующим этапом было изменение прав доступа сервисного аккаунта.  
Я изменила роль с **Storage Admin** на **Compute Viewer**, чтобы проверить, как это повлияет на возможность работы с бакетом.

<img width="392" height="311" alt="image" src="https://github.com/user-attachments/assets/01f7bd76-710e-4dbc-99e7-17a52a632fb4" />

После изменения прав я снова попыталась скопировать файлы из бакета.  
В результате возникла ошибка доступа — копирование стало невозможно, так как у сервисного аккаунта больше не было необходимых разрешений на работу с объектами в Cloud Storage.
<img width="429" height="23" alt="image_2025-12-01_12-37-50" src="https://github.com/user-attachments/assets/596a0f61-a68e-43c0-b60a-cf3636cac112" />
