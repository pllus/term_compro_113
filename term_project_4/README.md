numpy คือ ไลเบอรี่ที่ พวกเราชอบใช้ แต่ อ.โต้ๆนั้นไม่ชอบใจเพราะฉะนั้นจงสร้างคลาส Matrix ที่สมามารถทำได้แบบ numpy ขึ้นมาซะ

### case 1
```python
>>> A = Matrix([[1,2,3],[4,5,6]])
>>> A
matrix([[1, 2, 3]
        [4, 5, 6]])
```
### case 2
```python
>>> a = '1 -3 4 3\n2 -5 6 6\n-3 3 4 6'
>>> A = Matrix(a)
>>> A
matrix([[1, -3, 4, 3]
         [2, -5, 6, 6]
         [-3, 3, 4, 6]])
>>> print(A)
[[1, -3, 4, 3]
 [2, -5, 6, 6]
 [-3, 3, 4, 6]]
>>> A.print()
[[1, -3, 4, 3]
 [2, -5, 6, 6]
 [-3, 3, 4, 6]]
>>> A.print("/nEnd of the print")
[[1, -3, 4, 3]
 [2, -5, 6, 6]
 [-3, 3, 4, 6]]
End of the print
>>> A.T
matrix([[1, 2, -3]
        [-3, -5, 3]
        [4, 6, 4]
        [3, 6, 6]])
>>> A.shape
(3,4)
>>> A.T.shape
(4, 3)
```
### case 3
```python
>>> f = open('matrix_A.txt','w')
>>> f.write('1 -3 4 3\n2 -5 6 6\n-3 3 4 6')
26
>>> f.close()
>>> A = Matrix.from_file('matrix_A.txt')
>>> A
matrix([[1, -3, 4, 3]
        [2, -5, 6, 6]
        [-3, 3, 4, 6]])
```
### case 4
```python
>>> A = Matrix([[1,2,3],[4,5,6]])
>>> B = Matrix([[7,8,9],[10,11,12]])
>>> A + B
matrix([[8, 10, 12]
        [14, 16, 18]])
>>> A - B
matrix([[-6, -6, -6]
        [-6, -6, -6]])
>>> A + B.T
raise Matrix_addition_error
>>> A - B.T
raise Matrix_subtraction_error
```
### case 5
```python
>>> A = Matrix([[1, -3, 4, 3], [2, -5, 6, 6], [-3, 3, 4, 6]])
>>> A
matrix([[1, -3, 4, 3]
        [2, -5, 6, 6]
        [-3, 3, 4, 6]])
>>> A * A
raise Martix_multiplication_error
>>> A*A.T
matrix([[35, 59, 22]
        [59, 101, 39]
        [22, 39, 70]])
>>>  A * 2
matrix([[2, -6, 8, 6]
        [4, -10, 12, 12]
        [-6, 6, 8, 12]])
>>> 2 * A
matrix([[2, -6, 8, 6]
        [4, -10, 12, 12]
        [-6, 6, 8, 12]])
>>> A * A
raise Martix_multiplication_error
```
### case 6
```python
>>> A = Matrix([[1, 3, 4, 3], [2, 5, 6, 6], [3, 3, 4, 6]])
>>> A
matrix([[1, 3, 4, 3]
        [2, 5, 6, 6]
        [3, 3, 4, 6]])
>>> A.sqrt()
matrix([[1, 1.7320508100147274, 2.0000000929222947, 1.7320508100147274]
        [1.4142135623746899, 2.236067977499978, 2.4494897427875517, 2.4494897427875517]
        [1.7320508100147274, 1.7320508100147274, 2.0000000929222947, 2.4494897427875517]])
```
### case 7
```python
>>> A = Matrix([[1,2,3],[4,5,6]])
>>> A
matrix([[1, 2, 3]
        [4, 5, 6]])
>>> B = Matrix([[1,2,3],[4,5,6],[7,8,9]])
>>> B
matrix([[1, 2, 3]
        [4, 5, 6]
        [7, 8, 9]])
>>> B * (2 * A.T * A)
matrix([[284, 376, 468]
        [680, 898, 1116]
        [1076, 1420, 1764]])
```

### Don't edit this code and use only this to find a square_root in "self.sqrt method"
```python
def square_root(a,l=10**-6):
    x = a
    while abs(x**2 - a) >=l:
        x = (x + a/x)*0.5
    return x
```
```python
# submit your code
```
