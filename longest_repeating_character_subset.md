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
