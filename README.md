# VPN

![image](https://user-images.githubusercontent.com/46523068/160524234-daaa1212-3db6-4855-bcd7-e2330fcda971.png)

![image](https://user-images.githubusercontent.com/46523068/160526785-391a45ae-2f41-4536-a589-0f3ec8977ff7.png)

![image](https://user-images.githubusercontent.com/46523068/160531042-a3d7a2e9-600b-400e-8957-ed4d16f63f2f.png)

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
![image](https://user-images.githubusercontent.com/87607801/160532556-ebddbd50-6b8d-45f2-9388-6f1ff95e90c4.png)
14. Тестим и радуемся, как маленькие. Ведь он работает очень быстро и даже на рутрекер можно зайти!!!!
![image](https://user-images.githubusercontent.com/87607801/160532653-fde10a5c-9ace-4d7e-bbd9-ad75d750978a.png)
15. Проверяем свой ip адрес
![image](https://user-images.githubusercontent.com/87607801/160538611-cd155cd9-927e-48c0-bc6a-76556fb86ff2.png)
16. Тестим через wireshark в течении минуты - двух. (Полученные файлы храняться в папке wiresharkTests)
![image](https://user-images.githubusercontent.com/87607801/160538521-68358d4e-b426-4e05-9e5c-727c0776ae7b.png)
