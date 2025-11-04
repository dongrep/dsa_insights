PATTERN: Sliding Window - Variable Size with Constraint

KEY INSIGHT: 
- Window size = r - l + 1
- Valid when: (window_size - max_freq) <= k
- Don't update max_freq when shrinking (already saw max window)

TEMPLATE:
```python
for r in range(n):
    expand window (add s[r])
    update state
    while invalid:
        shrink window (remove s[l])
        l += 1
    update result
```

GOTCHAS:
- Max count doesn't need to decrease (we want longest anyway)
- Window size formula: r - l + 1 (NOT r - l)

## Character Replacement - MY AHA MOMENT

I was tracking rest_count separately and it was a mess.

THE INSIGHT: 
rest = window_size - max_count
window_size = r - l + 1

No need for separate tracking! 
Just check: (r - l + 1) - max_count <= k

WHY I STRUGGLED:
I was trying to update rest_count incrementally
Instead of recalculating from window size each time
