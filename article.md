# Создаем сервис обучения для ВУЗов

Существует множество сервисов обучения.
Но хочется сделать такой сервис-фреймворк,
который можно будет легко реализовать
и так же без проблем писать контент курсов.

Сначала рассмотрим несколько существующих сервисов
(будем искать что-нибудь интересное),
затем попробуем создать архитектуру своей версии.

> Примечание:<br>
> Пользователя сервисом буду называть `Студентом`<br>
> Создателя контента для сервиса буду называть `Преподавателем`

## Что уже есть

### Сервисы, которые использует Матмех УрФУ

#### Ulearn

+ [Ссылка на сервис](https://ulearn.azurewebsites.net/)
+ [Ссылка на GitHub](https://github.com/kontur-edu/uLearn)

Сервис от компании [СКБ Контур](https://kontur.ru/).

Состоит из некоторого количества курсов.

Каждый курс разделен на темы.
Темы состоят из теории и практики.
Практические задания могут проходить
только авторизованные  студенты.
За практики ведется учет очков,
максимальное количество которых установлено преподавателем.

Состав темы:
  1. лекции
  + тесты (проверяются автоматически)
  + задание для практики (проверяются преподавателем)

\+ в конце каждой части темы есть форма для комментариев
и оценивания понятности материала

##### 1. Лекции
Лекции представлены в виде видеолекции с youtube,
некоторого пояснения к ней и представленного в видео кода.

Панель для просмотра кода является неким code-reader'ом,
имеющим подсветку синтаксиса и нумерацию строк.

##### 2. Тесты
Тесты существуют двух видов:
+ Выбор правильных ответов
+ Написание небольшого количества кода

###### Тестирование с выбором ответов
Представлено несколькими вопросами
и вариантами ответов к ним, при чем как "выбрать один", так и "выбрать несколько".

После выполнения теста, студент нажимает на "Отправить" и получает результат.
Все его ответы отмечаются либо красным цветом (неверно отвечено), либо зеленым (верно).

Существует возможность перепройти тест, количество попыток ограничено преподавателем.
После нажатия "Выполнить заново", все ответы студента стираются.
После каждой попытки количество баллов за задание уменьшается.

###### Тестирование с написанием кода
Представлено некоторым введением-заданием
и окном (далее редактор), в котором студент пишет свой вариант решения.

Редактор имеет подсветку синтаксиса,
подчеркивание синтаксических ошибок и автодополнение.

Под редактором есть набор кнопок, а именно:
+ Отправить
+ Подсказка
+ Посмотреть код других

После того, как студент нажимает "Отправить",
под редактором и кнопками появляется окно,
где, в случае верного решения, написано "Успех",
в случае неверного решения представлено
сравнение ответов программы студента с ожидаемыми ответами.

После того, как студент нажимает "Подсказка",
появляется некоторый текст, написанный преподавателем.
Подсказок есть некоторое количество, установленное преподавателем.

После того, как студент нажимает "Посмотреть код других",
происходит переход на другую страницу,
где представлены варианты успешных решений других студентов.
Решения можно оценивать как понравившиеся.

##### 3. Задание для практики
Задание для практики в теме только одно.
Состоит из одной или нескольких задач,
за каждую из которых предлагается некоторое количество баллов.
Максимальное количество баллов за задание для практики, вообще говоря,
установлено преподавателем, но обычно оно равно четырем.
Задание проверяется очно.

##### Итог:
Итак, Ulearn - сервис, предоставляющий возможность смотреть видеолекции,
выполнять практические задания как с выбором ответов, так и те,
где студент должен писать код и возможность отслеживать свой прогресс.

#### AnyTask.urgu
+ [Ссылка на сервис](https://anytask.urgu.org/)
+ [Ссылка на GitHub](https://github.com/znick/anytask)

Менее закрытая версия [Anytask](https://anytask.org/) от [Яндекс](https://yandex.ru/).

### Чуть более популярные сервисы

#### [Coursera](https://www.coursera.org/)

#### [Udemy](https://www.udemy.com/)

#### [Codecademy](https://codecademy.com/)

#### [HTML Academy](https://htmlacademy.ru/)
