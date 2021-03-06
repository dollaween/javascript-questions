<div align="center">

# Вопросы по паттернам проектирования

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)

</div>

---

##### 1. Что такое паттерны проектирования? Как классифицируются паттерны проектирования? Перечислите несколько паттернов проектирования.

<details><summary><b>Ответ</b></summary>
<p>

Паттерны разделяют на **порождающие**, **структурные** и **поведенческие**.

1. Порождающие — отвечают за удобное и безопасное создание новых объектов.
2. Структурные — отвечают за построение удобных в поддержке иерархий классов.
3. Поведенческие — решают задачи эффективного и безопасного взаимодействия между объектами программы.

Порождающие:
* Фабрика
* Абстрактная фабрика
* Строитель
* Прототип
* Одиночка

Структурные:
* Адаптер
* Мост
* Компоновщик
* Декоратор
* Фасад
* Легковес
* Заместитель

Поведенческие:
* Цепочка обязанностей
* Команда
* Итератор
* Посредник
* Снимок
* Наблюдатель
* Состояние
* Стратегия
* Шаблонный метод
* Посетитель

</p>
</details>

---

##### 2. Объясните принцип работы паттерна "Стратегия"? Приведите пример.

<details><summary><b>Ответ</b></summary>
<p>

**Паттерн "Стратегия"** — определяет семейство схожих алгоритмов и помещает каждый из них в собственный класс, после чего алгоритмы можно взаимозаменять прямо во время исполнения программы.

Аналогия из жизни:

Вам нужно добраться до аэропорта. Можно доехать на автобусе, такси или велосипеде. Здесь вид транспорта является стратегией. Вы выбираете конкретную стратегию в зависимости от контекста — наличия денег или времени до отлёта.

```javascript
// Объединяющий класс, который будет воспроизводить заданную стратегию
class Delivery {
  constructor(strategy) {
    this.strategy = strategy
  }

  setStrategy(strategy) {
    this.strategy = strategy
  }

  calculate(cost) {
    return this.strategy.calculate(cost)
  }
}

// Расчет стоимости доставки от компании A
class StrategyCompanyA {
  calculate(cost) {
    return cost * 2
  }
}

// Расчет стоимости доставки от компании B
class StrategyCompanyB {
  calculate(cost) {
    return cost * 3
  }
}

// Задаем стратегию компании А
const delivery = new Delivery(new StrategyCompanyA)
console.log(delivery.calculate(1000))
// => 2000

// Задаем стратегию компании B
delivery.setStrategy(new StrategyCompanyB)
console.log(delivery.calculate(1000))
// => 3000
```

[Стратегия](https://refactoring.guru/ru/design-patterns/strategy)

</p>
</details>

---

##### 3. Объясните принцип работы паттерна "Итератор"? Приведите пример.

<details><summary><b>Ответ</b></summary>
<p>

**Паттерн "Итератор"** — дает возможность последовательно обходить элементы составных объектов, не раскрывая их внутреннего представления.

```javascript
class Iterator {
  constructor(items) {
    this.items = items
    this.index = 0
  }

  // Проверяет наличие следующего элемента в коллекции
  hasNext() {
    return this.index < this.items.length
  }

  // Возвращает следующий элемент коллекции
  next() {
    return this.items[this.index++]
  }
}

const items = ['one', 'two', 'three', 'four']
const iterator = new Iterator(items)

while (iterator.hasNext()) {
  console.log(iterator.next())
}
// => 'one'
// => 'two'
// => 'three'
// => 'four'
```

[Итератор](https://refactoring.guru/ru/design-patterns/iterator)

</p>
</details>

---
