# Список веб камер

На этом практическом занятии предлагается сделать небольшое приложение, которое ищет веб камеры по указанным координатам при помощи [Webcams.travel API](http://developers.webcams.travel/) и показывает список найденных камер. В качестве практического задания предлагается сделать:

* Выполнение HTTP запроса Webcams.travel API при помощи [HttpURLConnection](https://developer.android.com/reference/java/net/HttpURLConnection.html)
* Разбор ответа в формате JSON при помощи [JSONObject](https://developer.android.com/reference/org/json/JSONObject.html)
* Отображение результата в списке при помощи [RecyclerView](https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html)
* Обработка ошибок выполнения запроса и ситуации отсутствия соединения

## Подготовка к заданию

Для того выполнения задания должны быть установлены:

* Android Studio, версия 2.2 или выше
* Android SDK
* Браузер Chrome (для отладки запросов)

В процессе работы с приложением потребуется постоянное соединение с интернетом для сборки (выкачивания зависимостей) и для работы самого приложения.

## Архитектура приложения

Приложение состоит из двух экранов:

* Экран ввода координат (стартовый)
* Экран со списком камер

Экран ввода координат уже релизован в классе SelectCoordsActivity, и с кодом этого экрана ничего делать не надо. Экран состоит из двух полей ввода для широты и долготы и кнопки, при нажатии на которую происходит переход на экран со списком камер.

Экран со списком камер нужно реализовать самим -- для него пока есть только заготовка в классе NearbyWebcamsActivity. Экран имеет три возможных состояния:

* Загрузка -- на экране показывается индикатор процесса загрузки, пока выполняется запрос
* Данные -- показываются загруженные данные (список камер с изображениями и заголовками)
* Ошибка -- отображается информация об ошибке (в том числе об остутствии интернета или о пустом результате)

## Webcams.travel API


