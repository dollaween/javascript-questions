<div align="center">

# Вопросы по бинарным данным

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)

</div>

---

##### 1. Что такое `ArrayBuffer`?

<details><summary><b>Ответ</b></summary>
<p>

`ArrayBuffer` — объект для работы с бинарными данными. Он представляет собой ссылку на поток "сырых" двоичных данных, однако напрямую работать с ними возможности не дает.

Для чтения/записи данных в `ArrayBuffer` используются `TypedArray` (типизированные массивы) или `DataView`.

```javascript
new ArrayBuffer(length)
```

</p>
</details>

---

##### 2. Что такое TextDecoder и TextEncoder?

<details><summary><b>Ответ</b></summary>
<p>

**TextDecoder** — объект, который позволяет декодировать данные из бинарного массива в обычную строку.

```javascript
let uint8Array = new Uint8Array([72, 101, 108, 108, 111])
console.log(new TextDecoder().decode(uint8Array))
// Hello
```

**TextEncoder** — объект, который позволяет кодировать строку в бинарный массив.
```javascript
let encoder = new TextEncoder();
console.log(encoder.encode('Привет'));
// [208, 159, 209, 128, 208, 184, 208, 178, 208, 181, 209, 130]
```

</p>
</details>

---

Ссылки:
* [ArrayBuffer, бинарные массивы](https://learn.javascript.ru/arraybuffer-binary-arrays)
* [TextDecoder и TextEncoder](https://learn.javascript.ru/text-decoder)
* [Blob](https://learn.javascript.ru/blob)
