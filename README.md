# Лабораторная работа 3.2
## Модель машинного обучения
Для создания модели была использована библиотека Sklearn, меотд RandomForestClassifier

Цель обученной модели - поиск в данных трафика, связанного с WEB-ом

Ничего сложного в написании кода не нет, но нужно было оптимизировать параметры модели, чтобы получить наилучший результат.
Для этого методом подбора был выбран критерий gini, а для более отпимального выбора критериев количества деревьев и максимальной глубины была сделана диаграмма, показывающая результаты раобты модели в заисимости от этих параметров.

![Количество деревьев](https://user-images.githubusercontent.com/87607801/163709705-71f83b5d-a408-413c-ba6f-a475d3537747.png)
Количество деревьев

![Максимальная глубина](https://user-images.githubusercontent.com/87607801/163709763-e8307ecd-9c6b-4625-afcc-9ec576325a44.png)
Максимальная глубина

В результате замеров были выбраны оптимальные параметры
Результат работы модели с выбранными параметрами представлен ниже

![Результат](https://user-images.githubusercontent.com/87607801/163709820-35ddfb4b-ff0e-47a3-a78e-36a0d7ce1960.png)


# Лабораторная работа 3.1
## Wireguard
1. Создаём калю на DO, подключаемся по ssh, делаем основные вещи(apt update, apt upgrade, apt install wireguard).
2. Генерируем ключи для сервера и для клиентов: 
![image](https://user-images.githubusercontent.com/46522218/160557152-1e12694f-32ca-4f7d-95ba-68ef3a5f693e.png)
3. Создаём кофиг wg0.conf на сервере, и добавляем туда следующую информацию:
![image](https://user-images.githubusercontent.com/46522218/160555937-2cc8bf81-02dc-4d2c-aa0e-02c7b06630c4.png)
4. На клиентском компьютере тоже создаём файл с расширением .conf и записываем туда следующую информацию:
![image](https://user-images.githubusercontent.com/46522218/160556242-05c89153-ed2c-436f-8297-b93ad213ea87.png)
5. Подключаемся, видим, что подключение прошло успешно
![image](https://user-images.githubusercontent.com/46522218/160556578-7385d009-38a6-4e1f-8fbc-7095a33a3a44.png)
6. Результат ifconfig:
![image](https://user-images.githubusercontent.com/46522218/160556789-9d4a55f6-789f-494b-b00e-594b9fc3509e.png)


Настройка подключения IKEv2

1. Создаём каплю на digitalocean
2. Следуя инструкции генерируем случайные учётные данные (wget https://git.io/vpnsetup -qO vpn.sh && sudo sh vpn.sh)
![Скрин результата](https://user-images.githubusercontent.com/87607801/160533172-cff073b4-5c59-4567-b5dd-260e471e8afd.png)
3. Сохраняем наши логин и пароль куда-нибудь
4. Теперь создаём подключение на нашем компьютере
5. Для этого нужно сохранить файл vpnclient.p12
6. Для того, чтобы скачать этот файл, воспользуемся сторонним софтом - FileZilla
7. Через менеджер сайтов создаём подключение к нашему серверу
![image](https://user-images.githubusercontent.com/87607801/160531824-b5bf2961-6b7a-4807-ba99-5ba173847ff2.png)
8. Вводим пароль, который задавали при создании сервера
9. В конечном итоге получаем полный доступ к файловой системе своей капли и скачиваем нужный нам vpnclient.p12
![image](https://user-images.githubusercontent.com/87607801/160532008-c9097c2b-4f45-4fb6-8e8a-fd62cf798e75.png)
10. Переносим этот файл в отдельную папку и к нему же кидаем файл ikey_config_impport.cmd
![image](https://user-images.githubusercontent.com/87607801/160532132-433f6d95-4441-4dd9-a7a8-fe6ea5d8cb16.png)
11. Дважды нажимаем на vpnclient.p12 и подтверждаем всё, что у нас спрашивают
![image](https://user-images.githubusercontent.com/87607801/160532294-6ea09bd2-a32f-4e32-8d2e-abb51b32a0c4.png)
12. В свойствах ikey_config_impport.cmd разрешаем файл, а потом запускаем его от имени администратора и так же соглашаемся со всем, что там написано, не внося никаких изменений.
13. В итоге в параметрах сети появляется нужное нам подключение VPN:
![image](https://user-images.githubusercontent.com/87607801/160567225-b28aa3a1-e625-45c4-84a2-4603c78f5003.png)
14. Тестим и радуемся. Ведь он работает очень быстро и можно зайти на рутрекер!
![image](https://user-images.githubusercontent.com/87607801/160532653-fde10a5c-9ace-4d7e-bbd9-ad75d750978a.png)
15. Проверяем свой ip адрес
![image](https://user-images.githubusercontent.com/87607801/160566981-d80869e9-3b10-407f-8abd-54a9287630ad.png)
16. Тестим через wireshark в течении минуты - двух. (Полученные файлы храняться в папке wiresharkTests)
![image](https://user-images.githubusercontent.com/87607801/160538521-68358d4e-b426-4e05-9e5c-727c0776ae7b.png)
17. Проверка через Ipconfig

![image](https://user-images.githubusercontent.com/87607801/160552871-cfcdd25c-bafc-4601-a668-e7cd5e9fe5d0.png)
