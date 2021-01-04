<div align="center">

<h1>Вопросы по Javascript: Браузер</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tasks">Задачи</a>

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

##### 3. Что такое Cookie?

<details><summary><b>Ответ</b></summary>
<p>

`document.cookie` — это небольшие строки данных, которые хранятся в браузере в виде пары `ключ=значение;`. Куки обычно устанавливаются сервером при помощи заголовка `Set-Cookie`. Затем браузер будет автоматически добавлять их почти в каждый запрос на тот же домен при помощи заголовка `Cookie`.

Пример `document.cookie`:
```javascript
document.cookie = "login=Batman; path=/; expires=Tue, 01 Jan 2047 01:23:45 GMT"
``` 

Опции:
* `path=/` — делает куки видимым только по указанному пути и нижу, по умолчанию устанавливает текущий путь.
* `domain=site.com` — по умолчанию куки видно только на текущем домене, если явно указан домен, то куки видно и на поддоменах.
* `expires` или `max-age` — устанавливает дату истечения срока действия, без них куки умрет при закрытии браузера.
* `secure` — делает куки доступным только при использовании HTTPS.
* `samesite` — запрещает браузеру отправлять куки с запросами, поступающими извне, помогает предотвратить XSRF-атаки.

</p>
</details>

---

##### 4. Что такое IndexedDB?

<details><summary><b>Ответ</b></summary>
<p>

**IndexedDB** — это низкоуровневое API для клиентского хранилища большого объема структурированных данных, включая файлы/blobs. Эти API используют индексы для обеспечения высоко-производительного поиска данных.

</p>
</details>

---

Ссылки:
* [Куки, document.cookie](https://learn.javascript.ru/cookie)
* [LocalStorage, sessionStorage](https://learn.javascript.ru/localstorage)
