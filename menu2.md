@def title = "Solutions"
@def hascode = true
@def rss = "here"
@def rss_title = "Solutions"
@def rss_pubdate = Date(2019, 5, 1)

@def tags = ["syntax", "code", "image"]

\toc
## Lab Two

I'll add more solutions here soon, you will see ... 

### Problem 9

**Q:** If `Alist=[9,-4,33,2,89,100,36,11]`, what is `Alist[2]`? What is `Alist[2][1]`?

**A:** Test it out and see for yourself! Email any questions and I'll be happy to answer. 

---

### Problem 10

**Q:** In the cases provided in the problem set, predict the behavior of the code, and check for yourself.

**A:** Covered in-depth during lecture; solution not provided.

---

### Problem 11

Write a code to find $$\sum_{j=1}^{10,000} \frac{1}{j}$$

```
val = 0
for j in range(1,10_001):
    val += 1/j

val
```
or

```
sum(1/i for i in range(1,10_001))
```


---

### Problem 12

Write code to find $$\sum_{m=1}^{600} \sum_{n=10}^{450} \frac{m}{n}$$

```
val = 0 
for m in range(1, 601):
    for n in range(10, 451):
        val += m/n

val
```
---

### Problem 13

Find the sum of all positive integers from 1 to 1000 which are not divisible by 4 or 5

```
sum([i for i in range(1,1000) if i % 4 != 0 and i % 5 != 0])
```

---


### Problem 14

Create a list of squares of all numbers $x$, where $1 \leq x \leq 20,000$, and $x$
is divisible by $7$.

```
sList = []

for i in range(1,20_001):
    if i % 7 == 0:
        sList.append(i**2)

sList
```
or

```
[x**2 for x in range(1,20_001) if x % 7 == 0]
```
---

### Problem 15

From a list of squares of numbers $x$, where $1 \leq x \leq 100,000$, remove all entries which start with $9$ and end with $0$ or $1$.

```
sList = []

for x in range(1,100_001):
    if(str(x**2)[0] == "9"):
        if(str(x**2)[-1] == "0" or str(x**2)[-1] == "1"):
            pass
        else:
            sList.append(x**2)
    else:
        sList.append(x**2)

sList
```

or

```
[x**2 for x in range(1,101) if ((str(x**2)[0] != "9") and (str(x**2)[-1] != "0") or (str(x**2)[-1] != "1"))]
```

---


### Problem 16

Write a code to determine whether a given year is a leap year or not. Input: a year between $1600$ and $2200$. Output: Year $1997$ is not a leap year. Year $2004$ is a leap year. etc.

note: years divisible by 4 are leap years, except if they are divisible by
100 but not divisible by 400. Thus, 1700, 1800, 1900, 2100 are not leap
years, but 2000, 2400 are leap years.

```
def IsLeapYear(year: int) -> bool:
    return(year in [year for year in range(1600, 2500) if ((year % 4 == 0) and not (year % 100 == 0 and year % 400 != 0))])
```

---

### Problem 17

Find the sum of all digits used in writing down the numbers from 1 to
2 million (including 1 and including 2 million).

```
sum([sum(map(int,str(x))) for x in range(1,2_000_001)])
```

---
### Problem 18


Write a Python code which computes the sum

$$S=\sum_{i^{*}=1}^{10000} \frac{1}{i^{*}}$$ 

where $i^*$ is a number written without the number seven, e.g.

$$S=\frac{1}{1}+\cdots+\frac{1}{6}+\frac{1}{8}+\cdots+\frac{1}{16}+\frac{1}{18}+\cdots+\frac{1}{69}+\frac{1}{80}+\cdots+\frac{1}{10000}$$

```
sum([int for int in range(1,10001) if "7" not in str(int)])
```

---

### Problem 19

You are speeding on a highway and a police officer stops you. Write a
code to compute the fine that you might have to pay (call the variable
fine), based on the following rules (assume that the speed is a positive
integer):

- If your speed is 110 km/h or less, the fine is zero.
- If your speed is between 111 and 130 inclusive, the fine is 150.
- If your speed is above 130 km/h, the fine is 350.
- If it is your birthday, your speed can be 5 km/h higher in all cases (use your actual birthday, or make one up)
- For instance, if you drive 114 km/h on your birthday, your fine is zero.
If you drive 118 km/h on your birthday, your fine \$150. If you drive
114 km/h and it’s not your birthday, your fine is \$150.

```
def FineValue(speed: int, isBirthday: bool) -> int:

    fine = 0

    if(isBirthday == 1):
        speed -= 5

    if(111 <= speed <= 130):
        fine = 150

    if( 130< speed):
        fine = 350

    return fine
```
---

### Problem 20


Let $M = 123456 ... 99979998999910000$ (i.e., M is obtained by writing all numbers from $1$ to $10000$ next to each other)

-  How many digits does $M$ have?
-  How many times does the number $7$ appear in $M$?

```
digits = 0
sevens = 0
for i in range(1, 10_001):
    for j in str(i):
        digits += 1
        if j == "7":
            sevens += 1

print(digits)
print(sevens)
```

### Problem 21


### Problem 22

### Problem 23

*Problem Twenty Three*

Write a code that computes the transpose of some matrix M, of the form:

`M=[[1,2,3],[4,5,6],[7,8,9]]`

```
from typing import List

def Transpose(M:List[List]) -> List[List]:
    """This transposes a matrix :D"""
    return([[row[i] for row in M] for i in range(len(M[0]))])
```


### Problem 24

### Problem 25

### Problem 26

### Problem 27

### Problem 28

### Problem 29

