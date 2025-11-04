PATTERN: 2 sum extension - with de duplication logic 

KEY INSIGHT: 
- sort the array get the smallest elements first
- should skip - check if last element is same as current
- when we find a valid 3 sum update both pointers and keep updating till we find unique elements

TEMPLATE:
```python
for curr in range(n):
    if last == curr: skip
    while l < r:
        if valid 3 sum:
            track this
            l+=1 r-=1
            (r_last is r+1 and r_next would be r-1)
            while r_last == r:
                move r
            while l_last == l:
                move l
        elif sum < 0:
            move l
        else:
            move r
```

GOTCHAS:
- Max count doesn't need to decrease (we want longest anyway)
- Window size formula: r - l + 1 (NOT r - l)
