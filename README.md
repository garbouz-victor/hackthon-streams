# hackathon-streams

В рамках хакатона предлагается сделать телеграм-бота, который будет уметь отдавать стоимость любой криптовалюты, торгующейся на популярных биржах.

В качестве подзадач можно выделить следующие шаги:<br/>
1. Создание простейшего телеграм-бота, который умеет здороваться и по команде отдать стоимость запрошенной валюты.<br/>
  1.1 Провзаимодействовать с botfather, получить пререквезиты для создания.<br/>
  1.2 Написать бота, который умеет ходить в бд(предлагается использовать mongodb) и отдавать стоимость.<br/>
  1.3 ...Бота можно докрутить на всякие предсказания.<br/>
<del>2. Создать crawler, который будет раз в несколько минут(ограничение бесплатного api) ходить на coinmarketcap и забирать данные.<br/>
  2.1 Получить ключ для доступа на coinmarketcap.<br/>
  2.2 Создать клиента-crawler-а, который умеет ходить по расписанию и забирать данные.<br/>
  2.3 Т.к. данных там "до дури" отдается достаточно большой json, поэтому предлагается реализовать поточную обработку этого json(поточный json-парсер). Тут-то нам и потреьуется akka-streams(да и вообще парочка "акторов" точно потребуется)<br/>
  2.4 После парсинга каждой значащей лексемы(в нашем случае это стоимость монетки на текущий момент) мы складываем в mongo json с информацие по стоимости.<br/>
      Этот пункт позволит нам хранить историю стоимостей(она доступна только в платной версии api).</del>

2. Обработка потока с изменением стоимости валют.<br/>
  2.1 Участникам будет предоставлен генератор данных, который будет эмулировать изменения стоимости валют.<br/>
  2.2 Предлагается создать обработчик, реагирующий на эти изменения и умеющий отдавать информацию клиенту в телеграм.<br/>
  2.3 Тут разгул для творчества: можно установить коридор для оповещений(при выходе из него клиенту телеграм шлется уведомление), подписка на иные виды событий...
