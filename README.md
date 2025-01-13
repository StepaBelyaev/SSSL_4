![image](https://github.com/user-attachments/assets/0c6c323e-f3e9-47a8-97b3-a4955337cbd7)Системы сбора событий и логов.

ББМО-02-23 Беляев С.К.

## Практика № 4 Network Threat Hunting

# Скачиваем и разворачиваем образ.
![1](https://github.com/user-attachments/assets/9f187af5-f882-4c1c-a264-b7778a424347)

Входим в систему с логином и паролем, приложенным к заданию практической работы.
![2](https://github.com/user-attachments/assets/5c3d2c84-dcb8-448c-bac3-3aef77e9a937)

Сначала, проверим, работает ли веб версия AC Hunter.
![3](https://github.com/user-attachments/assets/1b66ac12-9682-47f1-8e5b-8903273b24fc)

Запустим для теста системы, используя предложенный датасет
![4](https://github.com/user-attachments/assets/d907410f-0734-4a35-bef4-78da5ed023a0)
![5](https://github.com/user-attachments/assets/da6a62d9-09b7-4893-8ac9-343b9d2dae05)
![6](https://github.com/user-attachments/assets/a32f2c96-d809-4d57-ac43-7afa739eb0ec)

Все работает. Значит, теперь, мы можем приступить к загрузке нужных нам логов и датасетов. Проверим наличие необходимых утилит.
![7](https://github.com/user-attachments/assets/b2f95f32-be90-4fcd-b0a1-33c250ec7892)

Сразу импортируем все датасеты сразу для трех заданий практики.
![8](https://github.com/user-attachments/assets/409ac779-8da4-4388-831d-eeb27f9e864f)
![9](https://github.com/user-attachments/assets/201d26d8-a4e6-4d4d-a634-3785429c0ab2)
![10](https://github.com/user-attachments/assets/5c33b4b3-8142-4433-b38f-ae729cbb2c12)

В AC-Hunter появились наши датасеты
![11](https://github.com/user-attachments/assets/805ed525-67e5-4087-a249-ad8450d4e2a4)

# lab1
Запустим с датасетом lab1
![12](https://github.com/user-attachments/assets/caa136ed-f8b7-4acb-a748-2237666e227e)

Перейдем в beacons web для анализа
![13](https://github.com/user-attachments/assets/c9287a4b-9df9-44b4-964b-91b1a1742b85)
![14](https://github.com/user-attachments/assets/acea0852-9fff-4722-bfaf-8c617678ac0e)

Анализ выявил следующее:
1) Высокий показатель метрик
2) Большое количество общих соединений, что, в теории, может свидетельствовать о нежелательном повидении
3) Встречаются использование HTTP без шифрования

Безопасные адреса добавим в белый список
![15](https://github.com/user-attachments/assets/f05903ac-0438-42e5-91f6-cfd8f1032cd7)
![16](https://github.com/user-attachments/assets/21680718-68b0-43e4-b201-88e91e58db7f)

Проверим, дополнился ли наш белый список
![17](https://github.com/user-attachments/assets/3a0765f4-3f2a-4f6f-9375-1c9fd476864f)

Проверим какие у нас есть подозрительные подключения с большим временем продолжительности подключения (в данном случае 5 часов)
![18](https://github.com/user-attachments/assets/bd233950-b7d3-4456-be0d-c4343e95880b)

Проверка проводилась через virus total. Были получены следующие результаты:
![19](https://github.com/user-attachments/assets/7836da35-fd72-4c95-ba56-673c131a9b91)
![20](https://github.com/user-attachments/assets/81d26e4e-b881-4304-90f1-e86f2b40f332)

Как видим, на одном из адресов была выявлена вредоносная составляющая.

# lab2
В данной работе проводился анализ подозрительного домена
![22](https://github.com/user-attachments/assets/1902defa-b0b5-47ff-9432-cfd9c466bc63)
![23](https://github.com/user-attachments/assets/04e55517-5535-4f76-b3f3-e95562b3b782)

Анализ выявил следующее:
1) Наличие подозрительного домена
2) Аномально большое количество DNS-запросов
3) Наличие длинных поддоменов
4) Налчие C2-активности

# lab3
![25](https://github.com/user-attachments/assets/f0efe2ab-0427-4c9d-b474-40db1c33e900)
![26](https://github.com/user-attachments/assets/7e23118b-56a3-4e38-a8ef-f0fe67c10412)
![27](https://github.com/user-attachments/assets/c926bef7-01ed-44f8-b21b-cad718e66e8e)

Есть адрес с подозрительной активностью:
![28](https://github.com/user-attachments/assets/1b73b910-0b87-45ef-b603-373f396903aa)
Проверим его через virus total
![29](https://github.com/user-attachments/assets/b950c4eb-36ec-4dfd-8bf1-8a29c746c713)
Была выявлена вредоносная составляющая. Безопасные адреса можем добавить в белый список
![30](https://github.com/user-attachments/assets/57000457-91f6-4b90-8c40-c7e13c666058)
![31](https://github.com/user-attachments/assets/b0cd5109-9b13-4910-b540-ca9e07390010)











