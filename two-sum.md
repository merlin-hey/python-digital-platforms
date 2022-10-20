+ [Search two sum](#search-two-sum)

## Search two sum

Данные отсортированы в неубывающем порядке. Найти два таких индекса i и j, что numb[i] + numb[j] == k

```python
def search_two_sum(numb, k):
    numb_copy = numb.copy()
    numb_copy.sort() #не обязательно
    left = 0
    right = len(numb_copy)-1
    while left < right:
        if numb_copy[left] + numb_copy[right] == k:
            return [left, right]
        elif numb_copy[left] + numb_copy[right] < k:
            left = left + 1
        else:
            right = right - 1
            
    return [-1, -1]```
