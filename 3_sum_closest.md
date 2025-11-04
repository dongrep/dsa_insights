PATTERN: 3 sum variation - don't overthink, we just need to track closest_sum

KEY INSIGHT: 
- sort the array get the smallest elements first
- Don't de duplicate, we actually need to check everything

TEMPLATE:
```python
for curr in range(n):
    while l < r:
        if abs(curr_sum - target) < abs(closest_sum - target):
            track this
            
        if curr_sum < target:
            move l
        elif curr_sum > target:
            move r
        else:
            # target == curr_sum, can't have better answer
            return curr_sum
```

GOTCHAS:
- Coming from 3 sum might use the dedup logic
- Overcomplicating with multiple states
