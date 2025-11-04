PATTERN: backtrack with pruning 

KEY INSIGHT: 
- if total % buckets != 0, no solution
- max a bucket can hold = total // buckets
- 2 approaches try putting each element in a bucket or try filling buckets with all the elements we have and then move
- Putting each element in a bucket and trying is more intuitive
- Prune the branch if the current bucket was 0, as the next bucket would be invalid as well

TEMPLATE:
```python
def backtrack(num_index):
  if num_index == nums_len:
    return True #we have found a valid solution
  
  # small trick to prune even more
  prev_cap = float("inf")

  for bucket_cap in buckets:
    if prev_cap == bucket_cap:
      continue

    if bucket_cap + nums[num_index] < max_bucket_cap:
      
      bucket_cap += nums[num_index]

      if backtrack(num_index+1):
        return True

      # backtrack the change
      bucket_cap -= nums[num_index]
    
    # because if we couldn't place this one in an empty bucket, we won't be placing this anywhere
    if bucket_cap == 0:
      break

    prev_cap = bucket_cap
```

GOTCHAS:
- This one is just about realising how to organize things in a bucket
