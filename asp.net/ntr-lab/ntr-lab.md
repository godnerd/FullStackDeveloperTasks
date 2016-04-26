# Task 1

В бд есть две таблички:

1. Customer

Id |Name

------------------

| 1 | Ivanov |

2 |Petrov

3 |Sidorov

2. CustomerInfo

Id |Field |Value

----------------------------------------

1 |FirstName |Ivan

1 |Phone |+7-903-1234567

2 |FirstName |Peter

2 |Phone |+7-903-2222222

3 |FirstName |Sidor

Таблички связаны по полю Id

Требуется написать SQL-запрос, возвращающий следующий резултат

ID |FirstName |Name |Phone

-----------------------------------------------

1 |Ivan |Ivanov |+7-903-1234567

2 |Peter |Petrov |+7-903-2222222

3 |Sidor |Sidorov|

# Task 2

Write a listbox-style binary search for an ordered array of integers.

 Listbox-style means that you should return the index of the first item greater than or equal to the item being searched for; if all items are less, you should return the index of the last item.

 You are guaranteed that there is at least one item in the array.

# Task 3
Suppose you have an array of integers, both positive and negative, in no particular order. 

Find the largest possible sum of any continuous subarray. For example, if you have all positive numbers, the largest sum would be the sum of the whole array; if you have all negative numbers, the largest sum is 0 (the null subarray)

Please report how long did it take you to do these tasks. We will review and performance test your answers and let you know how it went.
