<div align="center">

<h1>Вопросы по Javascript: Дебаггинг</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Как работает выражение `debugger`?

<details><summary><b>Ответ</b></summary>
<p>

Выражение `debugger` открывает доступ к любому доступному в конкретном окружении отладочному функционалу, например, к установке брейкпоинтов.

В примере ниже, при вызове отладчика выполнение скрипта приостановится в том месте, где находится выражение `debugger`. В **Chrome Dev Tools** мы можем посмотреть значение аргумента `props`.
```javascript
function buggyFunction(props) {
  debugger
}
buggyFunction();
```

</p>
</details>

---

##### 2. Какие инструменты есть на вкладке "Source" в Chrome Dev Tools?

<details><summary><b>Ответ</b></summary>
<p>

На вкладке "Source" мы можем:
1. Работать с брейкпоинтами: добавлять/удалять, двигаться по ним.
2. Работать с **Event Listeners**.
3. Смотреть **Scope** функции.
4. Смотреть **Call Stack**.
5. Следить за переменными во вкладке **Watch**.

</p>
</details>

---

