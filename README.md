
# ETutor

ETutor - это API система для определения вероятности отчисления студентов по полученным данным

## Установка
Для начала следует установить Docker. [Руководство по установке](https://docs.docker.com/engine/install/)

После установки Docker следует открыть консоль и перейти в расположение проекта, создать образ (image)
```bash
docker  build  -t  your_image_name
```
Далее следует создать контейнер(ы)

```bash
docker  run  -d  --name  your_container_name  -p  your_port_number:80  your_image_name
```

## Работа

Для работы с API нужно после запуска контейнера перейти по адресу:

- http://localhost:your_port_number/docs на локальной машине,
- http://your_local_IP:your_port_number/docs на другом компьютере в локальной сети.

 ### Диск Bitrix24
 
 Для непосредственной работы с файлами и диском необходимо:
 - в Диске создать рабочую папку,
 - загрузить файлы с данными в форматах: ***.csv***, ***.xlsb***, ***.xlsx*** в папку,

 - скопировать внутреннюю ссылку,
![Получение внутренней ссылки](https://drive.google.com/uc?id=1yM5Z3uB0_NWShuPOkkYFyhQIIruke-XX&export=download)
 - полученную ссылку поместить в раздел **bitrix24_path_to_folder** API
 - после выполнения программы в текущей папке будет создана папка Results (если она не была ещё создана), в которую будут загружены оценки вероятности отчисления студентов,
 - после добавления файлов обязательно нужно запустить раздел **bitrix24_path_to_folder** API
 ### Одиночная запись
 Для получения результатов необходимо заполнить поля в разделе **single_student** API
| Student | BIRTHDATA | admission_year | direction1 | direction2 | direction3 | FINANCING |
|--|--|--|--|--|--|--|
| some_name | yyyy-mm-dd | 2001 | 10.02.03 | 10.02.02 | 10.02.01 | 1 |
.........
| MODE | GENDER | SCORE1 | SCORE2 | SCORE3 | COUNTRY | REGION |
|--|--|--|--|--|--|--|
| 1| 1 | 72 | 71 | 70 | Россия | 10 |
