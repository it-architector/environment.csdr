# Framework CSDR

<h3>Предисловие</h3>

Framework CSDR (Conditions, Space, Distribution и Realization) переведёт программирование на уровень сконцентрированной сборки проекта, результатом которого станет <a href="https://github.com/it-architector/structure.csdr">структурированный код</a>.

![](./Картинки/samostoatelnaia-sborka-3d-printera.jpg)


<h3>Навигация</h3>

1. <a href="#Среда">Среда</a>

     1.1. <a href="#Развёртка">Развёртка</a>
     
     1.2. <a href="#Области">Области</a>
     
     1.3. <a href="#Аутентификация">Аутентификация</a>
     
2. <a href="#Сборка">Сборка</a>

    2.1. <a href="#Действия">Действия</a>
    
    2.2. <a href="#Компиляция">Компиляция</a>
    
![---------------------](./Картинки/hr.png)

<h2>Среда</h2>

<h3>Развёртка</h3>

Среда сборки должна разворачиваться в виде программы на операционные системы: windows, mac и *nix.

<h3>Области</h3>

Для сборки проекта пределены такие области среды:
1. Программист
2. Проект
    1. Архитектура
    2. Дизайн
3. Ход сборки

![](./Картинки/program/shablon1.png)

<h3>Аутентификация</h3>

По умолчанию все области в начале заблокированы, кроме области "Программист". Здесь будет форма для идентификации, где достаточно ввести в свободной форме логин.

    
![---------------------](./Картинки/hr.png)

<h2>Сборка</h2>

<h3>Действия</h3>

Под действиями для авторизованного будут манипуляции в областях: проект, архитектура и дизайн.

Изначально области архитектуры и дизайна недоступны, их открытие начинается после того как выбрали или создали проект. Как только это совершили, в области **проект** можно будет:
1. Задать название проекта
2. Определить тип проекта
3. Управлять конструкциями

В области **архитектуры**:
1. Управлять рефлексией

В области **дизайна**:
1. Управлять местом
2. Управлять связью
3. Управлять реакцией

Каждые произведенные действия будут записываться в файл проекта, где у каждого действия будет отмечено:

1. **Тип действия**:

     1.1. Добавить
     
     1.2. Изменить
     
     1.3. Удалить
     
     1.4. Зафиксировать // чтобы убрать возможность удаления
     
     1.5. Разафиксировать
2. **Компонент**:

     1.1. Рефлекс
     
     1.2. Место
     
     1.3. Связь
     
     1.4. Реакция

3. **Индификатор** //номер для компонента

4. **Значение**

     - у рефлекса это ориентир (текст), расчёты (текст), места (массив индификаторов мест (для мест с ролями "запросы" и "ожидание" можно дополнять внутренним списком индификаторов мест)), права (код).
    
     - у мест это смысл (текст), роль (массив), связи (индификатор связи), вложение (для роли "атрибутов" текст, массив).
     
     - у связей это тип (текст), возможности и приобретение (два списка для индификаторов мест (или массив array("название_переменной" => "индефикатор_места") при типе "глобальное")), образцы возможности и приобретение (массив), реакция (индификатор реакции).
    
     - у реакций это способность (код).
     
5. **Авторство** // определение программиста
     
6. **Дата** // Дата совершенного действия

<h3>Компиляция</h3>

В области **хода сборки** можно увидеть не только лог ваших действий, но и создать структурированный код проекта кнопкой компиляции. В созданный код будут автоматически добавлены функции примененных в проекте ролей.
