# Prime-Number-Multiplication-Finder
the way of finding prime number which use scalar multiplication for checking prime number

# usage:
`
fn(half_of_maxNumber)
`
+ half_of_maxNumber: signless integer
> it is 2-10 times slower than Euler's Sieve during maxNumber 1000-2000.

# content:

```python
import time

def fn(n):
	t = 1;
	i = 1;
	limit = int(0.34*n) +1;
	result = [];
	result.append(2);
	while i < limit:
		x = 2*i+1;
		if (t % x) != 0:
			result.append(x);
			t = t*x;
		else:
			t = t*x*(x-2);
		i = i + 1;
	while i < n:
		x = 2*i+1;
		if (t % x) != 0:
			result.append(x);
		i = i + 1;
	return result;

start = time.time();
result = fn(500);
end = time.time();
run = end - start;
print(result);
print("ran time:", run, "s");
```
