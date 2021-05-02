---
layout: post
title: How to extract data from csv file and store it in numpy array
tags: first markdown example
categories: python
mathjax: true
---

# Problem Statement
Suppose you have some data in the csv (which is short for comma-seperated-values) format. 
We want to import this data in the form of numpy array. The goal of this post is to create
a quick template which you can copy, paste and modify to suit your need.

# The data

Consider a warehouse where there are 8 types of items are availble. For productivity tracking
purposes the warehouse management stores the data of the items being sold at different time 
by diffent shift of workers. Lets assume the data is given in the following format.

| Warehouse : SK3502 | | | | | | | | | | 
| date | 23 May 1980 | | | | | | | | | 
| Shift No. | Time \ Item_id -> | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 

| 1 | 100 | 10 | 20 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 101 | 0 | 0 | 21 | 4 | 5 | 6 | 0 | 7 | 

| 2 | 105 | 1 | 1 | 2 | 4 | 5 | 6 | 0 | 1 | 
| 2 | 106 | 8 | 8 | 8 | 8 | 8 | 7 | 0 | 0 | 
| 2 | 108 | 1 | 1 | 2 | 2 | 3 | 2 | 1 | 1 | 

| 3 | 110 | 2 | 5 | 5 | 4 | 4 | 2 | 7 | 4 | 
| 3 | 111 | 1 | 2 | 2 | 3 | 5 | 7 | 8 | 9 | 
| 3 | 112 | 1 | 5 | 5 | 2 | 9 | 2 | 0 | 0 | 

| 4 | 115 | 0 | 0 | 0 | 4 | 4 | 5 | 2 | 0 | 

## What we want to achieve?

We want to import the table in python such that we have the data of all the shifts in on array
and also we have the array of the items in the warehouse.

```python
> shift[0]
[1, [ [100, [10 , 20 , 0 , 0 , 0 , 0 , 0 , 0 ]],
    [101 , [0 , 0 , 21 , 4 , 5 , 6 , 0 , 7]] ] ]

> item_id
[1 , 2 , 3 , 4 , 5 , 6 , 7 , 8]

```

## Now the code

To achieve the above we need to first import the csv module. Use this to open the csv file and 
convert data in the form of the python list.

```python
import csv

with open('warehouse_SK3502.csv', newline='') as f:
    f_data = csv.reader(f, delimiter=',')
    f_list = list(f_data)

```

If we print the f_list we would get the following output.

```python
[['Warehouse : SK3502'],
 ['date ', ' 23 May 1980 '],
 ['Shift No. ',
  ' Time \\ Item -> ',
  ' 1 ',
  ' 2 ',
  ' 3 ',
  ' 4 ',
  ' 5 ',
  ' 6 ',
  ' 7 ',
  ' 8 '],
 ['1 ', ' 100 ', ' 10 ', ' 20 ', ' 0 ', ' 0 ', ' 0 ', ' 0 ', ' 0 ', ' 0 '],
 ['1 ', ' 101 ', ' 0 ', ' 0 ', ' 21 ', ' 4 ', ' 5 ', ' 6 ', ' 0 ', ' 7  '],
 ['2 ', ' 105 ', ' 1 ', ' 1 ', ' 2 ', ' 4 ', ' 5 ', ' 6 ', ' 0 ', ' 1  '],
 ['2 ', ' 106 ', ' 8 ', ' 8 ', ' 8 ', ' 8 ', ' 8 ', ' 7 ', ' 0 ', ' 0  '],
 ['2 ', ' 108 ', ' 1 ', ' 1 ', ' 2 ', ' 2 ', ' 3 ', ' 2 ', ' 1 ', ' 1  '],
 ['3 ', ' 110 ', ' 2 ', ' 5 ', ' 5 ', ' 4 ', ' 4 ', ' 2 ', ' 7 ', ' 4  '],
 ['3 ', ' 111 ', ' 1 ', ' 2 ', ' 2 ', ' 3 ', ' 5 ', ' 7 ', ' 8 ', ' 9  '],
 ['3 ', ' 112 ', ' 1 ', ' 5 ', ' 5 ', ' 2 ', ' 9 ', ' 2 ', ' 0 ', ' 0  '],
 ['4 ', ' 115 ', ' 0 ', ' 0 ', ' 0 ', ' 4 ', ' 4 ', ' 5 ', ' 2 ', ' 0  ']]

```

Now it's a piece of cake to to get the list of item-ids.

```python
> item_id = [int(s) for s in f_list[2][2:]]
> item_id
[1, 2, 3, 4, 5, 6, 7, 8]

```

Also lets store rest of data in a list called 'd'.

```python
>  d=f_list[3:]
> d
[['1 ', ' 100 ', ' 10 ', ' 20 ', ' 0 ', ' 0 ', ' 0 ', ' 0 ', ' 0 ', ' 0 '],
 ['1 ', ' 101 ', ' 0 ', ' 0 ', ' 21 ', ' 4 ', ' 5 ', ' 6 ', ' 0 ', ' 7  '],
 ['2 ', ' 105 ', ' 1 ', ' 1 ', ' 2 ', ' 4 ', ' 5 ', ' 6 ', ' 0 ', ' 1  '],
 ['2 ', ' 106 ', ' 8 ', ' 8 ', ' 8 ', ' 8 ', ' 8 ', ' 7 ', ' 0 ', ' 0  '],
 ['2 ', ' 108 ', ' 1 ', ' 1 ', ' 2 ', ' 2 ', ' 3 ', ' 2 ', ' 1 ', ' 1  '],
 ['3 ', ' 110 ', ' 2 ', ' 5 ', ' 5 ', ' 4 ', ' 4 ', ' 2 ', ' 7 ', ' 4  '],
 ['3 ', ' 111 ', ' 1 ', ' 2 ', ' 2 ', ' 3 ', ' 5 ', ' 7 ', ' 8 ', ' 9  '],
 ['3 ', ' 112 ', ' 1 ', ' 5 ', ' 5 ', ' 2 ', ' 9 ', ' 2 ', ' 0 ', ' 0  '],
 ['4 ', ' 115 ', ' 0 ', ' 0 ', ' 0 ', ' 4 ', ' 4 ', ' 5 ', ' 2 ', ' 0  ']]
 
```

Lets now first create the list of shifts id, time, list of number of items sold.

```python
> shift_id_list=[]
> shift_items_sold = []
> shift_time =[]
> for i in range(len(d)):
>     shift_id_list.append(int(d[i][0]))
>     shift_time.append(float(d[i][1]))
>     shift_items_sold.append([int(s) for s in d[i][2:]])

> shift_id_list
[1, 1, 2, 2, 2, 3, 3, 3, 4]

> shift_time
[100.0, 101.0, 105.0, 106.0, 108.0, 110.0, 111.0, 112.0, 115.0]

> shift_items_sold
[[10, 20, 0, 0, 0, 0, 0, 0],
 [0, 0, 21, 4, 5, 6, 0, 7],
 [1, 1, 2, 4, 5, 6, 0, 1],
 [8, 8, 8, 8, 8, 7, 0, 0],
 [1, 1, 2, 2, 3, 2, 1, 1],
 [2, 5, 5, 4, 4, 2, 7, 4],
 [1, 2, 2, 3, 5, 7, 8, 9],
 [1, 5, 5, 2, 9, 2, 0, 0],
 [0, 0, 0, 4, 4, 5, 2, 0]]

```

Now lets use python dictionary to group the shift_id and get the repeatation and make 
the required list for shift.

```python
d_ = {i : shift_id_list.count(i) for i in shift_id_list}

start_row = 0
for shift_id, shift_entry in d_.items():
    shift.append([shift_id, [[shift_time[i], shift_items_sold[i]] for i in range(start_row, start_row + shift_entry)]])

```

Finally lets check it.

```python
> shift
[[1,
  [[100.0, [10, 20, 0, 0, 0, 0, 0, 0]], [101.0, [0, 0, 21, 4, 5, 6, 0, 7]]]],
 [2,
  [[100.0, [10, 20, 0, 0, 0, 0, 0, 0]],
   [101.0, [0, 0, 21, 4, 5, 6, 0, 7]],
   [105.0, [1, 1, 2, 4, 5, 6, 0, 1]]]],
 [3,
  [[100.0, [10, 20, 0, 0, 0, 0, 0, 0]],
   [101.0, [0, 0, 21, 4, 5, 6, 0, 7]],
   [105.0, [1, 1, 2, 4, 5, 6, 0, 1]]]],
 [4, [[100.0, [10, 20, 0, 0, 0, 0, 0, 0]]]]]

> shift[0]
[1, [[100.0, [10, 20, 0, 0, 0, 0, 0, 0]], [101.0, [0, 0, 21, 4, 5, 6, 0, 7]]]]

```

