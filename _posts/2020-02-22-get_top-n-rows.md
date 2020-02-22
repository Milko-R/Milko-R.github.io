
---
layout: post
title: "Titanic_Data_3(Get the top N rows) "
date: 2020-02-22 1:45:30
categories: [Data, Python, Modules]
tags: [ cvs]

---
We can get the top N  rows of the huge Titanic.csv file with itemgetter.

With this  code:

{% highlight python %}
#gettop-nrows.py
import csv
from operator import itemgetter
N=11 # to get 10 rows need use 10+1=11
fname='titanic_csv.csv'
get_columns=itemgetter('survived', 'pclass', 'name', 'sex', 'age')
with open(fname,'r') as csvfile:
    reader = csv.DictReader(csvfile.readlines()[0:N])
    [print(*get_columns(row)) for row in reader]
     # or for all fields : use [print(row)) for row in reader]
     
{% endhighlight %}
    
You can execute the file directly 
```
$ python3 ettop-nrows.py
