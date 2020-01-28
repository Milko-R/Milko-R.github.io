---
layout: post
title: "Convert space separated data to csv with python"
date: 2020-01-25 1:45:30
categories: [Data, Python, Modules]
tags: [sys, re]

---

**Convert space separated data to csv with python**

Use the Python standard module re to convert the data separated by spaces as follows into a comma-separated csv file.
{% highlight python %}
#Before conversion
datetime  data1 data2
2019-01-01 15 25
2019-01-02  20 30
2019-01-03  25 40
{% endhighlight %}

{% highlight python %}
#After conversion
datetime,data1,data2
2019-01-01,15,25
2019-01-02,20,30
2019-01-03,25,40
{% endhighlight %}

with this code
{% highlight python %}
#! /usr/bin/python3 import re
import sys
pattern=re.compile(' +') 
ifile=sys.argv[1]       
ofile=open('c'+ifile.split('.')[0]+'.csv','tw') 
with open(ifile,'tr') as fin:
    for iline in fin:
        ofile.write(pattern.sub(',',iline))
    ofile.close()
    {% endhighlight %}
    
You can execute the file directly 
```
$ python3 mkcsv.py test.txt
```

