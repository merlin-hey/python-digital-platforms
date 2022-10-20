+ [Search min](#search-min)
+ [Search two sum](#search-two-sum)

## Search min

Найти первые три минимума в списке

```python
def search_min(numb, exclude_ind):
    min = numb[0]
    min_index = 0
    
    for i, elem in enumerate(numb):
        if elem < min and i not in exclude_ind:
            min = elem
            min_index = i
            
    return min_index          

lst = [1, 3, -5, -3, 10, 20, 15]
first_min_index = search_min(lst, [-1])

print("First Min", lst[first_min_index])
print("First Min Index", first_min_index)

second_min_index = search_min(lst, [first_min_index])

print("Second Min", lst[second_min_index])
print("Second Min Index", second_min_index)

third_min_index = search_min(lst, [first_min_index, second_min_index])

print("Third Min", lst[third_min_index])
print("Third Min Index", third_min_index)
```

## Search two sum

Данные отсортированы в неубывающем порядке. Найти два таких индекса i и j, что numb[i] + numb[j] == k

```python
def search_two_sum(numb, k):
    numb_copy = numb.copy()
    numb_copy.sort()
    left = 0 
    right = len(numb_copy)-1
    while left < right:
        if numb_copy[left] + numb_copy[right] == k:
            return [left, right]
        elif numb_copy[left] + numb_copy[right] < k:
            left = left + 1
        else:
            right = right - 1
            
    return [-1, -1]    
```
