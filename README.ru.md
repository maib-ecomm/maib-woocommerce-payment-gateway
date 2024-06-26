[![N|Solid](https://www.maib.md/images/logo.svg)](https://www.maib.md)
#  Maib Payment Gateway Plugin for WooCommerce
Этот плагин позволяет интегрировать ваш WooCommerce интернет-магазин с **maib** e-commerce API для приема онлайн-платежей (Visa/Mastercard/Google Pay/Apple Pay).

## Описание
Этот плагин разработан [maib](https://www.maib.md/en) на базе [maib e-commerce API](https://docs.maibmerchants.md/en).

Подробнее об этапах интеграции и требованиях к сайту можно узнать [здесь](https://docs.maibmerchants.md/ru/etapy-i-trebovaniya-k-integracii).

Чтобы протестировать интеграцию, вам понадобятся данные доступа к тестовому проекту (Project ID / Project Secret / Signature Key). Для этого просим вас отправить запрос на электронную почту: ecom@maib.md.

Для осуществления реальных платежей вам необходимо заключить договор e-commerce и выполнить как минимум одну успешную транзакцию, используя данные тестового проекта и данные карты для тестирования.

После подписания договора вы получите доступ к платформе maibmerchants и сможете активировать Производственный Проект.

## Функционал
**Платежи онлайн**: Visa / Mastercard / Apple Pay / Google Pay.

**Два типа платежей** (в зависимости от настроек вашего проекта):

  *1. Прямые платежи* - if the transaction is successful the amount is withdrawn from the customer's account.

  *2. Двухэтапные платежи* - в случае успешной транзакции сумма блокируется на счете клиента (авторизованная транзакция), для вывода суммы необходимо будет завершить транзакцию из созданного заказа с помощью действии - _Завершить двухэтапный платеж_.

**Три валюты**: MDL / USD / EUR (в зависимости от настроек вашего проекта).

**Возврат платежа**: через стандартную функцию возврата WooCommerce из созданного заказа. Возвращаемая сумма может быть меньше или равна сумме транзакции. Действие возврата возможно только один раз для каждой успешной транзакции.

## Требования
- Регистрация на платформе maibmerchants.md
- WordPress ≥ v. 4.8
- WooCommerce ≥ v. 3.3
- PHP ≥ v. 5.6 (с включенными расширениями curl и json)

## Установка

### Через FTP
1. Загрузите плагин из репозитория GitHub.
2. Разархивируйте загруженный файл.
3. Если плагин был загружен из GitHub, переименуйте извлеченную папку в _maib-payment-gateway-for-woocommerce_.
4. Загрузите папку _maib-payment-gateway-for-woocommerce_ в каталог _/wp-content/plugins/_.
5. Перейдите в меню **Плагины** в панели управления WordPress и активируйте плагин.

## Активировать метод оплаты
1. Перейдите в **WooCommerce> Настройки> Платежи**.
2. Активируйте _Maib Payment Gateway_.
3. Нажмите _Управление_, чтобы выполнить необходимые настройки.

## Настройки
1. Включить/Выключить метод оплаты
2. Заголовок - Название метода оплаты, отображаемое покупателю.
3. Описание - Описание метода оплаты, отображаемое покупателю.
4. Режим отладки - Включить отладку метода оплаты. Чтобы просмотреть сообщения отладки, нажмите _Посмотреть логи_ и выберите файл _maib_gateway__ с датой, для которой вы хотите просмотреть логи.
5. Тип платежей - Прямые платежи или двухэтапные платежи.
6. Описание заказа - Информация о заказе отображаемая Покупателю на странице ввода данных карты.
7. Project ID - ID Проекта из maibmerchants.
8. Project Secret - Пароль проекта. Доступен после активации Проекта.
9. Signature Key - Ключ подписи для проверки уведомлений о состоянии транзакции на Callback URL. Доступен после активации Проекта.
10. Статус заказа: Платеж завершен - Статус заказа, если транзакция успешно завершена. По умолчанию: Обработка.
11. Статус заказа: Двухэтапный платеж авторизован - Статус заказа, если транзакция успешно авторизована. По умолчанию: На удержание.
12. Статус заказа: Платеж не удался - Статус заказа, если транзакция не удалась. По умолчанию: Не удалась.
13. Настройки Проекта - Добавьте ссылки для Ok URL / Fail URL / Callback URL в соответствующих полях Проекта в maibmerchants.

## Отладка
Включите режим отладки и проверьте логи.

Если вам требуется дополнительная помощь, обращайтесь в службу поддержки ecommerce **maib**, отправив сообщние по адресу ecom@maib.md.

В письме обязательно укажите следующую информацию:
- Название компании
- Project ID 
- Дата и время транзакции с ошибками
- Ошибки из файл с логами
