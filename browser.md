<div align="center">

<h1>Вопросы по Javascript: Браузер</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Для чего нужен Web Storage API?

<details><summary><b>Ответ</b></summary>
<p>

**Web Storage API** предоставляет механизмы при помощи которых браузеры могут безопасно хранить пары ключ/значение.

Web Storage API расширяет объект `window`, добавляя в него:
* `window.sessionStorage`
* `window.localStorage`

</p>
</details>

---

##### 2. Что такое `localStorage` и `sessionStorage`? В чем между ними разница?

<details><summary><b>Ответ</b></summary>
<p>

`localStorage` и `sessionStorage` позволяют получить доступ к объекту `Storage` и манипулировать парами `key` `value` (которые могут быть только в виде строк).

* `Storage.getItem(key)` — получить значение по ключу.
* `Storage.setItem(key, value)` — установить значение `value` для ключа `key`.
* `Storage.removeItem(key)` — удалить ключ из `Storage`.
* `Storage.clear()` — удалить все ключи из `Storage`.
* `Storage.key(index)` — получить имя `index`-ного ключа.

**Особенности `localStorage`:**
1. Этот объект один на все вкладки и окна в рамках источника (один и тот же домен/протокол/порт).
2. Данные не имеют срока давности. Сохраняются после перезапуска браузера и ОС.

**Особенности `sessionStorage`:**
1. Объект существует только в рамках текущей вкладки браузера. Но он разделен между `iframe` на той же вкладке.
2. Данные продолжают существовать после перезагрузки страницы, но не после закрытия/открытия вкладки.

</p>
</details>

---

