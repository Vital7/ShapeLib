# ShapeLib

## Тестовое задание для отклика на вакансию Mindbox

Файл `query.sql` содержит ответ на задание с SQL (включая запросы на создание таблиц и ввод данных).

Для проекта настроен CI для автоматической компиляции и тестирования.

### Немного о реализации

* Абстрактный класс `Shape` содержит функционал для кэширования (ленивая инициализация) площади.
* Класс `Distance` является обёрткой над значением `double`, валидируя его при создании объекта.
* `Triangle` имеет дополнительное свойство `IsEquilateralTriangle` для определения, является ли треугольник равносторонним.
* В целях оптимизации операция возведения в квадрат реализована перемножением значения на себя - см. [сравнение на SharpLab](https://sharplab.io/#v2:C4LghgzgtgPgAgJgIwFgBQcDMACR2DC2A3utmbjnEgGzYAmA9gK4BGANgKbYCyTbwASwAObAQGMwghgDsAFI1adsANzBsAlNgC8APhVrsAKn1sA3KXIWyWXDXrN2XbpIAWABQYB3eQ6WqN2nrOwC4AdB7e/gA02Ajq5mgAvkA===).
* Интерфейс `IShape` наследуется от интерфейса `IEquatable<IShape>`, что позволяет сравнивать фигуры (реализующие данный интерфейс).
* Также каждый класс реализует интерфейс `IEquatable<T>` (к примеру, `IEquatable<Circle>` для класса `Circle`) для сравнения фигур себе подобных (к примеру, два треугольника с равными сторонами равны вне зависимости от их порядка).
* Класс `Circle` реализует интерфейс `IComparable<Circle>`, что позволяет сравнивать величину разных кругов (чей радиус больше или меньше).
* Unit test coverage составляет 100%.
