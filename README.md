## E4.10. Итоговое задание
___
#### Задача

Как системному администратору данной организации вам поставлена задача собрать
на докер образ Django (Linux, nginx, Django, Postgres, Gunicorn) сервера,
который можно было бы выложить в публичный доступ на Docker Hub,
предоставляя кандидату только ссылку на образ и команду для установки.  
Все нужные сервисы должны быть проброшены на хост по стандартным портам, 
реализация HTTPS не требуется, версии Django, nginx и Postgres не имеют значения,
как и версия ядра Linux.  
В проекте просто должна работать админка с заранее прописанным логином и паролем.
___
### Запуск приложения

**Есть два варианта запуска приложения:** 

*Вариант 1 (с Гит-хаба):*  
1. Скачать архив с гита, распаковать, перейти в каталог с файлом "Dockerfile".
2. Построения образа командой:  
     "docker build -t dj_im:01 ."
3. Запуск контейнера:  
     "docker run -it --rm --name dj_container -p 8000:80 dj_im:01".  
   (опция "--rm" - удалит контейнер после выхода или прерывания работы,
    при необходимости убрать!)
4. Запуск в браузере:  
  http://localhost:8000/  - Начальная страница
  http://localhost:8000/admin/  - Админка (Логин: admin, пароль: admin)  

*Вариант 2 (с Докер-хаба):*  
1. Запуск контейнера напрямую из Докер-хаба:  
     "docker run -it --rm --name dj_container -p 8000:80 marat2010/dj_image_no_postgres:01".  
   (опция "--rm" - удалит контейнер после выхода или прерывания работы,
    при необходимости убрать!)
2. Запуск в браузере:  
  http://localhost:8000  - Начальная страница  
  http://localhost:8000/admin/  - Админка (Логин: admin, пароль: admin)    

*Для доступа к данным проекта создается том (Volume) в Linux по пути:*    
  **"/var/lib/docker/volumes/...id_тома..../_data/"**  






