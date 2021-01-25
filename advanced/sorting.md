<div align="center">

# Вопросы по сортировке

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)

</div>

---

##### 1. Объясните принцип сортировки слиянием (Merge Sort)

<details><summary><b>Ответ</b></summary>
<p>

**Сортировка слиянием (Merge Sort)** — алгоритм сортировки, при котором исходная задача разбивается на несколько подзадач меньшего размера, затем эти задачи решаются с помощью рекурсивного вызова или непосредственно (если их размер достаточно мало) и, наконец, их решения комбинируются.

#### Алгоритм
1. Сортируемый массив разбивается на две части примерно одинакового размера.
2. Каждая из получившихся частей сортируется отдельно, например — тем же самым алгоритмом.
3. Два упорядоченных массива половинного размера соединяются в один.

* **Time complexity** — O(N log N)
* **Space complexity** — O(N)

#### Пример

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) return arr

  const mid = Math.floor(arr.length / 2)
  const left = mergeSort(arr.slice(0, mid))
  const right = mergeSort(arr.slice(mid))

  return mergeSortedArrays(left, right)
}

function mergeSortedArrays(nums1, nums2) {
  const result = []
  let i = 0
  let k = 0

  while (i < nums1.length && k < nums2.length) {
    if (nums1[i] < nums2[k]) {
      result.push(nums1[i])
      i++
    } else {
      result.push(nums2[k])
      k++
    }
  }

  while (i < nums1.length) {
    result.push(nums1[i])
    i++
  }

  while (k < nums2.length) {
    result.push(nums2[k])
    k++
  }

  return result
}
```

</p>
</details>
