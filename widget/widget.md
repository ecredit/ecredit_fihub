# Интеграция с помощью виджета

## Назначение
Виджет позволяет легко разместить ярлыки быстрого доступа к продуктам F&I Hub еКредита на стороннем сайте.

Классический пример - кнопка, по клику на которой, происходит переход на страницу Кредит Онлайн. В момент перехода будут переданы параметры автомобиля, и при открытии страницы Кредит Онлайн уже будет выбран переданный автомобиль.

## Формат виджета
Виджет может или встроить iframe на текущей странице, в котором будет загружен контент страницы сервиса F&I Hub (Кредит Онлайн, еОсаго или еКаско), или отрисовать кнопку, по клику на которой произойдет переход в сервис F&I Hub на новой странице.

## Внедрение
Виджет представляет собой javascript код. В коде виджета, согласно предложенным комментариям, необходимо заполнить параметры автомобиля и после этого разместить код виджета на странице сайта.
Если на одной странице требуется разместить много кнопок для перехода в Кредит Онлайн, то нужно скопировать код виджета под каждую кнопку.

## Код виджета и параметры
Код виджета можно получить через интерфейс swagger или через тестовую форму виджета. Для этого необходимо знать Ваш публичный токен доступа к продуктам F&I Hub.

### Получить код через тестовую форму виджета
Тестовая форма виджета расположена по адресу [https://test-api-online.ecredit.one/fipage/widget](https://test-api-online.ecredit.one/fipage/widget)

На данной странице необходимо внести параметры виджета и нажать кнопку "Показать код виджета". Полученный код необходимо вставить на страницу сайта.

### Получить код через swagger
1.  Зайти на страницу Swagger UI. [Адрес страницы swagger можно узнать здесь](https://github.com/ecredit/ecredit_api_online/blob/master/work_with_api/work_with_api.md)
1. Авторизоваться с помощью своего токена (нажать на кнопку Authorize, в поле Value ввести публичный токен доступа и нажать кнопку Authorize и после этого закрыть данную форму)
1. запросить метод /v1/dictionary/widget-code

*Примечание:* это стандартное API Online. Данный метод можно использовать при интеграциях для автоматического получения кода виджета с заданными параметрами. Например, для получения кода виджета может быть использована такая ссылка [https://test-api-online.ecredit.one/v1/dictionary/widget-code?brand=Mazda&model=CX-5&configuration=Maximal%20equipment&price=1500000&initial_fee=50&car_condition=1&year=2020&access-token=goodevening](https://test-api-online.ecredit.one/v1/dictionary/widget-code?brand=Mazda&model=CX-5&configuration=Maximal%20equipment&price=1500000&initial_fee=50&car_condition=1&year=2020&access-token=goodevening)

Ссылка указана исключельно для примера. Актуальный список параметров всегда указан в сваггере и на тестовой форме виджета. А так же в коде виджета описаны все возможные параметры.

