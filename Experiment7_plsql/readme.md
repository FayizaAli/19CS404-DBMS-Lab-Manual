# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

## Program:
```
DECLARE
    a NUMBER := 30;
    b NUMBER := 80;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('Greatest number is: ' || a);
    ELSIF b > a THEN
        DBMS_OUTPUT.PUT_LINE('Greatest number is: ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Both numbers are equal.');
    END IF;
END;
```

**Expected Output:**  
Greater number is: 80

<img width="882" height="267" alt="Screenshot 2026-08-24 083005" src="https://github.com/user-attachments/assets/515ea7f7-41bc-40ba-a6be-33f0851facd0" />


## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

## Program:

```
DECLARE
    n NUMBER := 10;
    sum NUMBER := 0;
    i NUMBER := 1;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
```
**Expected Output:**  
Sum of first 10 natural numbers is: 55

<img width="877" height="276" alt="Screenshot 2026-08-24 083729" src="https://github.com/user-attachments/assets/b2d1bda3-4cb0-4aee-a637-372b5fcf9e34" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

## Program:
```
DECLARE
    n NUMBER := 10;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
BEGIN
    FOR i IN 1..n LOOP
        DBMS_OUTPUT.PUT_LINE(a);
        c := a + b;
        a := b;
        b := c;
    END LOOP;
END;
```
**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

<img width="869" height="436" alt="Screenshot 2026-08-24 084141" src="https://github.com/user-attachments/assets/aca682d1-421d-4442-94a4-7f89a361ec62" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

## Program:
```
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    digit NUMBER;
BEGIN
    WHILE n > 0 LOOP
        digit := MOD(n, 10);
        rev := rev * 10 + digit;
        n := TRUNC(n / 10);
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is: ' || rev);
END;
```
**Expected Output:**  
n = 1535  
Reversed number is 5351

<img width="866" height="274" alt="Screenshot 2026-08-24 084336" src="https://github.com/user-attachments/assets/29e695a5-7cac-4f11-bf1e-e13772ad4ee0" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

## Program:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a > b AND a > c THEN
        largest := a;
    ELSIF b > a AND b > c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
```
**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

<img width="876" height="286" alt="Screenshot 2026-08-24 084525" src="https://github.com/user-attachments/assets/1f45dbca-09be-435e-a9cb-a792ab4a85c1" />



## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
