### Задание 1
```python
    def calculate_count_paths(size, is_first):
    return 1 if size[0] == 1 and size[1] == 1 and not is_first else 0 if size[0] < 1 or size[1] < 1 else calculate_count_paths([size[0]-2, size[1]-1], False) + calculate_count_paths([size[0]-1, size[1]-2], False)
    print(calculate_count_paths(list(map(int, input().split())), True))
```
<details><summary>P.S.</summary>
Когда эталонное решение в 12 строк, а ты управился за 3

![](images/makak.png)
</details>

### Задание 2

```python
n = int(input())
sequence = list(map(int, input().split()))
medians = []

for i in range(n):
    sequence[:i+1]= sorted(sequence[:i+1])
    if (i + 1) % 2 == 1:
        median = sequence[(i + 1) // 2]
    else:
        median = sequence[i // 2]
    medians.append(median)

sum = 0
for median in medians:
    sum += median
print(sum)
```

### Задание 3
```python
text = input()
histo_dict = {}
for i in text:
    if i != " ":
        if i in histo_dict:
            histo_dict[i] = histo_dict[i] + 1
        else:
            histo_dict[i] = 1
sorted_dict = dict(sorted(histo_dict.items()))
for i in range(0, max(sorted_dict.values())):
    for j in sorted_dict:
        if sorted_dict[j] >= (max(sorted_dict.values()) - i):
            print("#", end="")
        else:
            print(" ", end="")
    print("\n", end="")
print("".join(list(sorted_dict.keys())))
```
