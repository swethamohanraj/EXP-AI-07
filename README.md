# EXP07 - Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python

#### NAME: K.M.Swetha
#### REG NO: 212221240055

## AIM:
To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python

## PROCEDURE:

<b> Input and Output </b> 
Input: This algorithm will take three words.

B A S E

B A L L

----------

G A M E S

Output: It will show which letter holds which number from 0 – 9. For this case it is like this.


          B A S E                         2 4 6 1
          B A L L                         2 4 5 5
         ---------                       ---------
         G A M E S                       0 4 9 1 6

## ALGORITHM:
For this problem, we will define a node, which contains a letter and its corresponding values.

isValid(nodeList, count, word1, word2, word3)

Input − A list of nodes, the number of elements in the node list and three words.

Output − True if the sum of the value for word1 and word2 is same as word3 value.


Begin
m := 1
for each letter i from right to left of word1, do
ch := word1[i]
for all elements j in the nodeList, do
if nodeList[j].letter = ch, then
break
done
val1 := val1 + (m * nodeList[j].value)
m := m * 10
done

m := 1
for each letter i from right to left of word2, do
ch := word2[i]
for all elements j in the nodeList, do
if nodeList[j].letter = ch, then
break
done



  val2 := val2 + (m * nodeList[j].value)
  m := m * 10



done

m := 1
for each letter i from right to left of word3, do
ch := word3[i]
for all elements j in the nodeList, do
if nodeList[j].letter = ch, then
break


  val3 := val3 + (m * nodeList[j].value)
  m := m * 10


done

if val3 = (val1 + val2), then
return true
return false
End



## PROGRAM:
```python
from itertools import permutations

def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Check for leading zeros
        if S == 0 or M == 0:
            continue

        # Check the equation constraints
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None

solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution
    print(f'SEND = {SEND}')
    print(f'MORE = {MORE}')
    print(f'MONEY = {MONEY}')
else:
    print("No solution found.")

```
### Sample Input and Output:
![image](https://github.com/Aashima02/AI07-Solve-Cryptarithmetic-Problem-a-CSP-Constraint-Satisfaction-Problem-using-Python/assets/93427086/0136aad2-b3d4-4105-a96f-c85db8675c09)



## RESULT:
Thus a Cryptarithmetic Problem was solved using Python successfully
