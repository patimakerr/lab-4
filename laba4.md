Первым делом я создала Dockerfile в gedit с следующим содержимым
![Image alt](https://github.com/patimakerr/patimakerr-in-ITMO/blob/main/текст%20файла%20лаба4.JPG)
Дале  при помощи следующей команды, которую мы вводим в терминале, создается образ 
```
sudo docker build . -t aafire-image
```
Потом этот контейнер запускается
```
sudo docker run -it --name aafire-container aafire-image
```
Далее я создала контейнеры
```
docker run -it --name aafire-container aafire-image
docker run -it --name aafire-container2 aafire-image
```
что привело к следующему результату 
![Image alt](https://github.com/patimakerr/patimakerr-in-ITMO/blob/main/огонь%20лаба4.JPG)

Следующий шаг выполненеия работы - это создание сети между двумя этими контейнерами. С этим нам поможет следующая команда
```
sudo docker network create myNetwork
```
Далее подключаем контейнеры к сети
```
sudo docker network connect myNetwork aafire-container
sudo docker network connect myNetwork aafire-container2
```
Проверяем настройки сети
```
sudo docker network inspect myNetwork
```
и получаем следующий результат
![Image alt](https://github.com/patimakerr/patimakerr-in-ITMO/blob/main/проверка%20настроек%20сети%20лаба4.JPG)

Теперь пингуем контейнеры 
```
ping <ip>
```
![Image alt](https://github.com/patimakerr/patimakerr-in-ITMO/blob/main/проверка%20соединения%20лаба4.JPG)
