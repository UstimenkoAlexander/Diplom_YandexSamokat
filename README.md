# Diplom_YandexSamokat
Описание заданий финального проекта.

Работа с базой данных.
Задание 1 Представь: тебе нужно проверить, отображается ли созданный заказ в базе данных. Для этого: выведи список логинов курьеров с количеством их заказов в статусе «В доставке» (поле inDelivery = true). 
Запрос: 
SELECT c.login, COUNT(o.id) AS deliverycount
FROM "Couriers" AS c LEFT JOIN "Orders" AS o ON c.ID = o."courierid"
WHERE o."InDelivery" = true
GROUP BY c.login; 

Задание 2 Ты тестируешь статусы заказов. Нужно убедиться, что в базе данных они записываются корректно. Для этого: выведи все трекеры заказов и их статусы. Статусы определяются по следующему правилу: 
если поле finished == true, то вывести статус 2. 
если поле canсelled == true, то вывести статус -1. 
если поле inDelivery == true, то вывести статус 1. 
Для остальных случаев вывести 0. запрос: SELECT track, CASE WHEN finished = true THEN 2 WHEN cancelled = true THEN -1 WHEN "inDelivery" = true THEN 1 ELSE 0 END AS status FROM "Orders"; Для данных запросов приложены скиншоты.

Автоматизация теста.
Для запуска теста необходимо в файл configuration скопировить URL В файле request нажать кнопку Run
