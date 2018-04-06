

```python
from plotly import __version__
from plotly.offline import download_plotlyjs, init_notebook_mode, plot, iplot
init_notebook_mode(connected=True)
import sys
import re
import vaderSentiment as vs
!{sys.executable} -m pip install textblob
from textblob import TextBlob
from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer
analyzer = SentimentIntensityAnalyzer()
```


<script>requirejs.config({paths: { 'plotly': ['https://cdn.plot.ly/plotly-latest.min']},});if(!window.Plotly) {{require(['plotly'],function(plotly) {window.Plotly=plotly;});}}</script>


    Requirement already satisfied: textblob in ./anaconda3/lib/python3.6/site-packages
    Requirement already satisfied: nltk>=3.1 in ./anaconda3/lib/python3.6/site-packages (from textblob)
    Requirement already satisfied: six in ./anaconda3/lib/python3.6/site-packages (from nltk>=3.1->textblob)



```python
with open('1980.txt', 'r') as myfile:
    DietaryGuidelines1980=myfile.read()
    
with open('1985.txt', 'r') as myfile:
    DietaryGuidelines1985=myfile.read()
    
with open('1990.txt', 'r') as myfile:
    DietaryGuidelines1990=myfile.read()
    
with open('1995.txt', 'r') as myfile:
    DietaryGuidelines1995=myfile.read()

with open('2000.txt', 'r') as myfile:
    DietaryGuidelines2000=myfile.read()

with open('2005.txt', 'r') as myfile:
    DietaryGuidelines2005=myfile.read()

with open('2010.txt', 'r') as myfile:
    DietaryGuidelines2010=myfile.read()

with open('2015.txt', 'r') as myfile:
    DietaryGuidelines2015=myfile.read()
```


```python
DietaryGuidelines1980=DietaryGuidelines1980.replace('\n________________\n','\n')
DietaryGuidelines1985=DietaryGuidelines1985.replace('\n________________\n','\n')
DietaryGuidelines1990=DietaryGuidelines1990.replace('\n________________\n','\n')
DietaryGuidelines1995=DietaryGuidelines1995.replace('\n________________\n','\n')
DietaryGuidelines2000=DietaryGuidelines2000.replace('\n________________\n','\n')
DietaryGuidelines2005=DietaryGuidelines2005.replace('\n________________\n','\n')
DietaryGuidelines2010=DietaryGuidelines2010.replace('\n________________\n','\n')
DietaryGuidelines2015=DietaryGuidelines2015.replace('\n________________\n','\n')

```


```python
DietaryGuidelines1980 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines1980)
DietaryGuidelines1985 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines1985)
DietaryGuidelines1990 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines1990)
DietaryGuidelines1995 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines1995)
DietaryGuidelines2000 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines2000)
DietaryGuidelines2005 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines2005)
DietaryGuidelines2010 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines2010)
DietaryGuidelines2015 = re.sub(r'\n([a-z]+)',r' \1', DietaryGuidelines2015)
```


```python
DietaryGuidelines1980list1 = [sentence for sentence in DietaryGuidelines1980.split('\n')]

DietaryGuidelines1985list1 = [sentence for sentence in DietaryGuidelines1985.split('\n')]

DietaryGuidelines1990list1 = [sentence for sentence in DietaryGuidelines1990.split('\n')]

DietaryGuidelines1995list1 = [sentence for sentence in DietaryGuidelines1995.split('\n')]

DietaryGuidelines2000list1 = [sentence for sentence in DietaryGuidelines2000.split('\n')]

DietaryGuidelines2005list1 = [sentence for sentence in DietaryGuidelines2005.split('\n')]

DietaryGuidelines2010list1 = [sentence for sentence in DietaryGuidelines2010.split('\n')]

DietaryGuidelines2015list1 = [sentence for sentence in DietaryGuidelines2015.split('\n')]

```


```python
DietaryGuidelines1980list2 = []
for i in DietaryGuidelines1980list1:
    DietaryGuidelines1980list2.append(i.split('.'))
    
    DietaryGuidelines1985list2 = []
for i in DietaryGuidelines1985list1:
    DietaryGuidelines1985list2.append(i.split('.'))
    
    DietaryGuidelines1990list2 = []
for i in DietaryGuidelines1990list1:
    DietaryGuidelines1990list2.append(i.split('.'))
    
    DietaryGuidelines1995list2 = []
for i in DietaryGuidelines1995list1:
    DietaryGuidelines1995list2.append(i.split('.'))
    
    DietaryGuidelines2000list2 = []
for i in DietaryGuidelines2000list1:
    DietaryGuidelines2000list2.append(i.split('.'))
    
    DietaryGuidelines2005list2 = []
for i in DietaryGuidelines2005list1:
    DietaryGuidelines2005list2.append(i.split('.'))
    
    DietaryGuidelines2010list2 = []
for i in DietaryGuidelines2010list1:
    DietaryGuidelines2010list2.append(i.split('.'))
    
    DietaryGuidelines2015list2 = []
for i in DietaryGuidelines2015list1:
    DietaryGuidelines2015list2.append(i.split('.'))


```


```python
DietaryGuidelines1980FinalList = []
for i in DietaryGuidelines1980list2:
    for j in i:
        DietaryGuidelines1980FinalList.append(j)
        
DietaryGuidelines1985FinalList = []
for i in DietaryGuidelines1985list2:
    for j in i:
        DietaryGuidelines1985FinalList.append(j)
        
        
DietaryGuidelines1990FinalList = []
for i in DietaryGuidelines1990list2:
    for j in i:
        DietaryGuidelines1990FinalList.append(j)
        
        
DietaryGuidelines1995FinalList = []
for i in DietaryGuidelines1995list2:
    for j in i:
        DietaryGuidelines1995FinalList.append(j)
        
        
DietaryGuidelines2000FinalList = []
for i in DietaryGuidelines2000list2:
    for j in i:
        DietaryGuidelines2000FinalList.append(j)
        
        
DietaryGuidelines2005FinalList = []
for i in DietaryGuidelines2005list2:
    for j in i:
        DietaryGuidelines2005FinalList.append(j)
        
        
DietaryGuidelines2010FinalList = []
for i in DietaryGuidelines2010list2:
    for j in i:
        DietaryGuidelines2010FinalList.append(j)
        
        
DietaryGuidelines2015FinalList = []
for i in DietaryGuidelines2015list2:
    for j in i:
        DietaryGuidelines2015FinalList.append(j)
        
        
        

```


```python
sugarlist1980 = []
for i in DietaryGuidelines1980FinalList:
    if 'sugar' in i:
        sugarlist1980.append(i)
#sugarlist1980

sugarlist1985 = []
for i in DietaryGuidelines1985FinalList:
    if 'sugar' in i:
        sugarlist1985.append(i)
#sugarlist1985

sugarlist1990 = []
for i in DietaryGuidelines1990FinalList:
    if 'sugar' in i:
        sugarlist1990.append(i)
#sugarlist1990

sugarlist1995 = []
for i in DietaryGuidelines1995FinalList:
    if 'sugar' in i:
        sugarlist1995.append(i)
#sugarlist1995

sugarlist2000 = []
for i in DietaryGuidelines2000FinalList:
    if 'sugar' in i:
        sugarlist2000.append(i)
#sugarlist2000

sugarlist2005 = []
for i in DietaryGuidelines2005FinalList:
    if 'sugar' in i:
        sugarlist2005.append(i)
#sugarlist2005

sugarlist2010 = []
for i in DietaryGuidelines2010FinalList:
    if 'sugar' in i:
        sugarlist2010.append(i)
#sugarlist2010

sugarlist2015 = []
for i in DietaryGuidelines2015FinalList:
    if 'sugar' in i:
        sugarlist2015.append(i)
#sugarlist2015


```


```python
sugarsentimentlist1980 = []
for i in sugarlist1980:
        sugarsentimentlist1980.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist1980

sugarsentimentlist1985 = []
for i in sugarlist1985:
        sugarsentimentlist1985.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist1985

sugarsentimentlist1990 = []
for i in sugarlist1990:
        sugarsentimentlist1990.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist1990

sugarsentimentlist1995 = []
for i in sugarlist1995:
        sugarsentimentlist1995.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist1995

sugarsentimentlist2000 = []
for i in sugarlist2000:
        sugarsentimentlist2000.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist2000

sugarsentimentlist2005 = []
for i in sugarlist2005:
        sugarsentimentlist2005.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist2005

sugarsentimentlist2010 = []
for i in sugarlist2010:
        sugarsentimentlist2010.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist2010

sugarsentimentlist2015 = []
for i in sugarlist2015:
        sugarsentimentlist2015.append(TextBlob(i).sentiment.polarity)
#sugarsentimentlist2015



```


```python
def mean(numbers):
    return float(sum(numbers)) / max(len(numbers), 1)

meansugarSentiment1980 = mean(sugarsentimentlist1980)

meansugarSentiment1985 = mean(sugarsentimentlist1985)

meansugarSentiment1990 = mean(sugarsentimentlist1990)

meansugarSentiment1995 = mean(sugarsentimentlist1995)

meansugarSentiment2000 = mean(sugarsentimentlist2000)

meansugarSentiment2005 = mean(sugarsentimentlist2005)

meansugarSentiment2010 = mean(sugarsentimentlist2010)

meansugarSentiment2015 = mean(sugarsentimentlist2015)


def normailizedMean(numbers):
    return float(float(sum(numbers)) / max(len(numbers), 1))/max(len(numbers), 1)






```


```python
positivesugarsentimentlist1980 = []
negativesugarsentimentlist1980 = []
neutralsugarsentimentlist1980 = []
for i in sugarsentimentlist1980:
        if i>0:
               positivesugarsentimentlist1980.append(i)
        elif i==0:
               neutralsugarsentimentlist1980.append(i)
        else:
               negativesugarsentimentlist1980.append(i)
                
positivesugarsentimentlist1985 = []
negativesugarsentimentlist1985 = []
neutralsugarsentimentlist1985 = []
for i in sugarsentimentlist1985:
        if i>0:
               positivesugarsentimentlist1985.append(i)
        elif i==0:
               neutralsugarsentimentlist1985.append(i)
        else:
               negativesugarsentimentlist1985.append(i)
                
positivesugarsentimentlist1990 = []
negativesugarsentimentlist1990 = []
neutralsugarsentimentlist1990 = []
for i in sugarsentimentlist1990:
        if i>0:
               positivesugarsentimentlist1990.append(i)
        elif i==0:
               neutralsugarsentimentlist1990.append(i)
        else:
               negativesugarsentimentlist1990.append(i)
                
positivesugarsentimentlist1995 = []
negativesugarsentimentlist1995 = []
neutralsugarsentimentlist1995 = []
for i in sugarsentimentlist1995:
        if i>0:
               positivesugarsentimentlist1995.append(i)
        elif i==0:
               neutralsugarsentimentlist1995.append(i)
        else:
               negativesugarsentimentlist1995.append(i)
                
positivesugarsentimentlist2000 = []
negativesugarsentimentlist2000 = []
neutralsugarsentimentlist2000 = []
for i in sugarsentimentlist2000:
        if i>0:
               positivesugarsentimentlist2000.append(i)
        elif i==0:
               neutralsugarsentimentlist2000.append(i)
        else:
               negativesugarsentimentlist2000.append(i)
                
positivesugarsentimentlist2005 = []
negativesugarsentimentlist2005 = []
neutralsugarsentimentlist2005 = []
for i in sugarsentimentlist2005:
        if i>0:
               positivesugarsentimentlist2005.append(i)
        elif i==0:
               neutralsugarsentimentlist2005.append(i)
        else:
               negativesugarsentimentlist2005.append(i)
                
positivesugarsentimentlist2010 = []
negativesugarsentimentlist2010 = []
neutralsugarsentimentlist2010 = []
for i in sugarsentimentlist2010:
        if i>0:
               positivesugarsentimentlist2010.append(i)
        elif i==0:
               neutralsugarsentimentlist2010.append(i)
        else:
               negativesugarsentimentlist2010.append(i)
                
positivesugarsentimentlist2015 = []
negativesugarsentimentlist2015 = []
neutralsugarsentimentlist2015 = []
for i in sugarsentimentlist2015:
        if i>0:
               positivesugarsentimentlist2015.append(i)
        elif i==0:
               neutralsugarsentimentlist2015.append(i)
        else:
               negativesugarsentimentlist2015.append(i)


```


```python
import plotly
plotly.tools.set_credentials_file(username='shivam.saith', api_key='xCijI2Ae8pZolWXkXMxN')
import plotly.plotly as py
import plotly.graph_objs as go

import numpy as np


trace0 = go.Scatter(
    x = np.arange(0,20),
    y = positivesugarsentimentlist1980,
    name = 'Positive',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(0, 153, 51, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)

trace1 = go.Scatter(
    x = np.arange(0,20),
    y = negativesugarsentimentlist1980,
    name = 'Negative',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(204, 51, 0, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)

trace2 = go.Scatter(
    x = np.arange(0,20),
    y = neutralsugarsentimentlist1980,
    name = 'Neutral',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(179, 179, 204, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)
data = [trace0, trace1,trace2]
#data = [trace0]

layout = dict(title = 'Sugar sentiment scatter plot(1980)',
              yaxis = dict(zeroline = False),
              xaxis = dict(zeroline = False)
             )

fig = dict(data=data, layout=layout)
iplot(fig, filename='sugar-sentiment-scatter-1980')

```


<div id="a996c924-45d6-46c3-8a35-67969ef313dc" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("a996c924-45d6-46c3-8a35-67969ef313dc", [{"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19], "y": [0.2, 0.07842857142857143, 0.13125, 0.1, 0.19999999999999998, 0.1, 0.3333333333333333, 0.2, 0.1, 0.175, 0.03333333333333333, 0.1, 0.18095238095238095], "name": "Positive", "mode": "markers", "marker": {"size": 10, "color": "rgba(0, 153, 51, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19], "y": [-0.125, -0.0625, -0.25, -0.08333333333333333, -0.23076923076923078], "name": "Negative", "mode": "markers", "marker": {"size": 10, "color": "rgba(204, 51, 0, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19], "y": [0.0, 0.0], "name": "Neutral", "mode": "markers", "marker": {"size": 10, "color": "rgba(179, 179, 204, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}], {"title": "Sugar sentiment scatter plot(1980)", "yaxis": {"zeroline": false}, "xaxis": {"zeroline": false}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
import plotly
plotly.tools.set_credentials_file(username='shivam.saith', api_key='xCijI2Ae8pZolWXkXMxN')
import plotly.plotly as py
import plotly.graph_objs as go

import numpy as np


trace0 = go.Scatter(
    x = np.arange(0,100),
    y = positivesugarsentimentlist2000,
    name = 'Positive',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(0, 153, 51, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)

trace1 = go.Scatter(
    x = np.arange(0,100),
    y = negativesugarsentimentlist2000,
    name = 'Negative',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(204, 51, 0, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)

trace2 = go.Scatter(
    x = np.arange(0,100),
    y = neutralsugarsentimentlist2000,
    name = 'Neutral',
    mode = 'markers',
    marker = dict(
        size = 10,
        color = 'rgba(179, 179, 204, .8)',
        line = dict(
            width = 2,
            color = 'rgb(0, 0, 0)'
        )
    )
)
data = [trace0, trace1,trace2]
#data = [trace0]

layout = dict(title = 'Sugar sentiment scatter plot(2015)',
              yaxis = dict(zeroline = False),
              xaxis = dict(zeroline = False)
             )

fig = dict(data=data, layout=layout)
iplot(fig, filename='sugar-sentiment-scatter-2015')

```


<div id="57baf7ec-ae92-4e7d-9174-fe3b9009d812" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("57baf7ec-ae92-4e7d-9174-fe3b9009d812", [{"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99], "y": [0.2125, 0.25, 0.25, 0.05333333333333334, 0.2966666666666667, 0.5, 0.1, 0.1, 0.1, 0.0625, 0.13, 0.4, 0.16, 0.1, 0.5, 0.14, 0.22, 0.16, 0.265, 0.08974358974358974], "name": "Positive", "mode": "markers", "marker": {"size": 10, "color": "rgba(0, 153, 51, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99], "y": [-0.03, -0.021875000000000006, -0.0625, -0.06944444444444443, -0.15555555555555559, -0.2, -0.2], "name": "Negative", "mode": "markers", "marker": {"size": 10, "color": "rgba(204, 51, 0, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0], "name": "Neutral", "mode": "markers", "marker": {"size": 10, "color": "rgba(179, 179, 204, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}], {"title": "Sugar sentiment scatter plot(2015)", "yaxis": {"zeroline": false}, "xaxis": {"zeroline": false}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
len(positivesugarsentimentlist2015)
```




    60




```python
sugarSentimentAcrossYears = []

sugarSentimentAcrossYears.append(meansugarSentiment1980)
sugarSentimentAcrossYears.append(meansugarSentiment1985)
sugarSentimentAcrossYears.append(meansugarSentiment1990)
sugarSentimentAcrossYears.append(meansugarSentiment1995)
sugarSentimentAcrossYears.append(meansugarSentiment2000)
sugarSentimentAcrossYears.append(meansugarSentiment2005)
sugarSentimentAcrossYears.append(meansugarSentiment2010)
sugarSentimentAcrossYears.append(meansugarSentiment2015)


print(meansugarSentiment1980) 

print(meansugarSentiment1985) 

print(meansugarSentiment1990) 

print(meansugarSentiment1995) 

print(meansugarSentiment2000) 

print(meansugarSentiment2005) 

print(meansugarSentiment2010) 

print(meansugarSentiment2015) 

```

    0.05903475274725276
    0.12014715034069876
    0.07654761904761904
    0.07473804023804025
    0.07445263532763534
    0.024055859264192597
    0.03384568632250752
    0.07404909967809967



```python
import plotly.plotly as py
import plotly.graph_objs as go

import pandas as pd
import numpy as np

df = pd.read_csv("https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv")

data = [go.Scatter(
          x=np.arange(1980,2020,5),
          y=sugarSentimentAcrossYears)]

iplot(data)
```


<div id="2fc45305-f2c8-4a3a-ba5b-1fbab3dd4289" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("2fc45305-f2c8-4a3a-ba5b-1fbab3dd4289", [{"type": "scatter", "x": [1980, 1985, 1990, 1995, 2000, 2005, 2010, 2015], "y": [0.05903475274725276, 0.12014715034069876, 0.07654761904761904, 0.07473804023804025, 0.07445263532763534, 0.024055859264192597, 0.03384568632250752, 0.07404909967809967]}], {}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
def getNutrientRelevantStatementsPolarityListUsingTextBlob(year, nutrientName): 
    with open(year + '.txt', 'r') as myfile:
        text = myfile.read()
    text1 =text.replace('\n________________\n','\n')
    text2 = re.sub(r'\n([a-z]+)',r' \1', text1)
    list1 = [sentence for sentence in text2.split('\n')]
    list2 = []
    for i in list1:
        list2.append(i.split('.'))
    
    finalList = []
    
    for i in list2:
            for j in i:
                finalList.append(j)
    
    nutrientStatementList = []
    
    for i in finalList:
        if nutrientName.lower() in i:
            nutrientStatementList.append(i)
    
    
    statementsPolarityList = []
    
    for i in nutrientStatementList:
            statementsPolarityList.append(TextBlob(i).sentiment.polarity)
        
        
    return statementsPolarityList; 


#with open('1980thin.pdf.txt', 'r') as myfile:
 #   DietaryGuidelines1980=myfile.read()

test = getNutrientRelevantStatementsPolarityListUsingTextBlob(year = '2000',nutrientName = 'vitamin' )
print(test)
```

    [0.0, 0.0, -0.01333333333333333, 0.19, 0.1875, 0.3333333333333333, 0.125, 0.15625, 0.0, -0.010416666666666671, -0.012500000000000011, 0.06666666666666665, 0.0, 0.10714285714285714, 0.19375, -0.2875, 0.325, -0.11666666666666665, 0.24375, 0.6875, 1.0, 0.0, 0.0, 0.5, -0.1, -0.2, 0.16]



```python
def getPositivePolarityList(nutrientPolarityList): 
    positivePolarityList = []
    for i in nutrientPolarityList:
        if i>0:
               positivePolarityList.append(i)
    return positivePolarityList;  

def getNegativePolarityList(nutrientPolarityList): 
    negativePolarityList = []
    for i in nutrientPolarityList:
        if i<0:
               negativePolarityList.append(i)
    return negativePolarityList; 

def getNeutralPolarityList(nutrientPolarityList): 
    neutralPolarityList = []
    for i in nutrientPolarityList:
        if i==0:
               neutralPolarityList.append(i)
    return neutralPolarityList; 
    
```


```python
def plotPolarityScatterPlot (nutrient,nutrientStatementPolarityList,year):
    import plotly
    plotly.tools.set_credentials_file(username='shivam.saith', api_key='xCijI2Ae8pZolWXkXMxN')
    import plotly.plotly as py
    import plotly.graph_objs as go

    import numpy as np


    trace0 = go.Scatter(
        x = np.arange(1,1000,2),
        y = getPositivePolarityList(nutrientStatementPolarityList),
        name = 'Positive',
        mode = 'markers',
        marker = dict(
            size = 10,
            color = 'rgba(0, 153, 51, .8)',
            line = dict(
                width = 2,
                color = 'rgb(0, 0, 0)'
            )
        )
    )

    trace1 = go.Scatter(
        x = np.arange(2,1001,2),
        y = getNegativePolarityList(nutrientStatementPolarityList),
        name = 'Negative',
        mode = 'markers',
        marker = dict(
            size = 10,
            color = 'rgb(230, 46, 0)',
            line = dict(
                width = 2,
                color = 'rgb(0, 0, 0)'
            )
        )
    )

    trace2 = go.Scatter(
        x = np.arange(3,1002,3),
        y = getNeutralPolarityList(nutrientStatementPolarityList),
        name = 'Neutral',
        mode = 'markers',
        marker = dict(
            size = 10,
            color = 'rgba(179, 179, 204, .8)',
            line = dict(
                width = 2,
                color = 'rgb(0, 0, 0)'
            )
        )
    )
    data = [trace0, trace1]
    #data = [trace0]

    layout = dict(title = 'Sentiment scatter plot for ' + nutrient + ' ' + '(' + year +')',
                  yaxis = dict(title = 'Polarity',zeroline = False),
                  xaxis = dict(title = 'Statement #(not in original order)',zeroline = False)
                 )

    fig = dict(data=data, layout=layout)
    return fig;


```


```python
requiredNutrient = 'Vitamin'
requiredYear = '2010'

iplot(plotPolarityScatterPlot(nutrient = requiredNutrient,nutrientStatementPolarityList = getNutrientRelevantStatementsPolarityListUsingTextBlob(year = requiredYear,nutrientName = requiredNutrient ), year = requiredYear), filename='sugar-polarity-scatter-2015')
```


<div id="99fd5f11-370e-4844-8784-f98bd7892cba" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("99fd5f11-370e-4844-8784-f98bd7892cba", [{"type": "scatter", "x": [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99, 101, 103, 105, 107, 109, 111, 113, 115, 117, 119, 121, 123, 125, 127, 129, 131, 133, 135, 137, 139, 141, 143, 145, 147, 149, 151, 153, 155, 157, 159, 161, 163, 165, 167, 169, 171, 173, 175, 177, 179, 181, 183, 185, 187, 189, 191, 193, 195, 197, 199, 201, 203, 205, 207, 209, 211, 213, 215, 217, 219, 221, 223, 225, 227, 229, 231, 233, 235, 237, 239, 241, 243, 245, 247, 249, 251, 253, 255, 257, 259, 261, 263, 265, 267, 269, 271, 273, 275, 277, 279, 281, 283, 285, 287, 289, 291, 293, 295, 297, 299, 301, 303, 305, 307, 309, 311, 313, 315, 317, 319, 321, 323, 325, 327, 329, 331, 333, 335, 337, 339, 341, 343, 345, 347, 349, 351, 353, 355, 357, 359, 361, 363, 365, 367, 369, 371, 373, 375, 377, 379, 381, 383, 385, 387, 389, 391, 393, 395, 397, 399, 401, 403, 405, 407, 409, 411, 413, 415, 417, 419, 421, 423, 425, 427, 429, 431, 433, 435, 437, 439, 441, 443, 445, 447, 449, 451, 453, 455, 457, 459, 461, 463, 465, 467, 469, 471, 473, 475, 477, 479, 481, 483, 485, 487, 489, 491, 493, 495, 497, 499, 501, 503, 505, 507, 509, 511, 513, 515, 517, 519, 521, 523, 525, 527, 529, 531, 533, 535, 537, 539, 541, 543, 545, 547, 549, 551, 553, 555, 557, 559, 561, 563, 565, 567, 569, 571, 573, 575, 577, 579, 581, 583, 585, 587, 589, 591, 593, 595, 597, 599, 601, 603, 605, 607, 609, 611, 613, 615, 617, 619, 621, 623, 625, 627, 629, 631, 633, 635, 637, 639, 641, 643, 645, 647, 649, 651, 653, 655, 657, 659, 661, 663, 665, 667, 669, 671, 673, 675, 677, 679, 681, 683, 685, 687, 689, 691, 693, 695, 697, 699, 701, 703, 705, 707, 709, 711, 713, 715, 717, 719, 721, 723, 725, 727, 729, 731, 733, 735, 737, 739, 741, 743, 745, 747, 749, 751, 753, 755, 757, 759, 761, 763, 765, 767, 769, 771, 773, 775, 777, 779, 781, 783, 785, 787, 789, 791, 793, 795, 797, 799, 801, 803, 805, 807, 809, 811, 813, 815, 817, 819, 821, 823, 825, 827, 829, 831, 833, 835, 837, 839, 841, 843, 845, 847, 849, 851, 853, 855, 857, 859, 861, 863, 865, 867, 869, 871, 873, 875, 877, 879, 881, 883, 885, 887, 889, 891, 893, 895, 897, 899, 901, 903, 905, 907, 909, 911, 913, 915, 917, 919, 921, 923, 925, 927, 929, 931, 933, 935, 937, 939, 941, 943, 945, 947, 949, 951, 953, 955, 957, 959, 961, 963, 965, 967, 969, 971, 973, 975, 977, 979, 981, 983, 985, 987, 989, 991, 993, 995, 997, 999], "y": [0.25, 0.26666666666666666, 0.03125, 0.03787878787878787, 0.2, 0.1, 0.11363636363636363, 0.25, 0.26666666666666666, 0.2708333333333333, 0.13333333333333333, 0.5, 0.09999999999999999, 0.05000000000000002, 0.5, 0.24166666666666664, 0.03333333333333333, 0.41666666666666663, 0.5583333333333333, 0.375, 0.012500000000000004, 0.2833333333333333, 0.41111111111111115, 0.21458333333333335, 0.25, 0.1, 0.15, 0.2833333333333333, 0.25, 0.3333333333333333, 0.28125, 0.5, 0.11704545454545455, 0.1, 0.3333333333333333, 0.04666666666666667, 0.15, 0.5, 0.1, 0.5], "name": "Positive", "mode": "markers", "marker": {"size": 10, "color": "rgba(0, 153, 51, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122, 124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150, 152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178, 180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206, 208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234, 236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260, 262, 264, 266, 268, 270, 272, 274, 276, 278, 280, 282, 284, 286, 288, 290, 292, 294, 296, 298, 300, 302, 304, 306, 308, 310, 312, 314, 316, 318, 320, 322, 324, 326, 328, 330, 332, 334, 336, 338, 340, 342, 344, 346, 348, 350, 352, 354, 356, 358, 360, 362, 364, 366, 368, 370, 372, 374, 376, 378, 380, 382, 384, 386, 388, 390, 392, 394, 396, 398, 400, 402, 404, 406, 408, 410, 412, 414, 416, 418, 420, 422, 424, 426, 428, 430, 432, 434, 436, 438, 440, 442, 444, 446, 448, 450, 452, 454, 456, 458, 460, 462, 464, 466, 468, 470, 472, 474, 476, 478, 480, 482, 484, 486, 488, 490, 492, 494, 496, 498, 500, 502, 504, 506, 508, 510, 512, 514, 516, 518, 520, 522, 524, 526, 528, 530, 532, 534, 536, 538, 540, 542, 544, 546, 548, 550, 552, 554, 556, 558, 560, 562, 564, 566, 568, 570, 572, 574, 576, 578, 580, 582, 584, 586, 588, 590, 592, 594, 596, 598, 600, 602, 604, 606, 608, 610, 612, 614, 616, 618, 620, 622, 624, 626, 628, 630, 632, 634, 636, 638, 640, 642, 644, 646, 648, 650, 652, 654, 656, 658, 660, 662, 664, 666, 668, 670, 672, 674, 676, 678, 680, 682, 684, 686, 688, 690, 692, 694, 696, 698, 700, 702, 704, 706, 708, 710, 712, 714, 716, 718, 720, 722, 724, 726, 728, 730, 732, 734, 736, 738, 740, 742, 744, 746, 748, 750, 752, 754, 756, 758, 760, 762, 764, 766, 768, 770, 772, 774, 776, 778, 780, 782, 784, 786, 788, 790, 792, 794, 796, 798, 800, 802, 804, 806, 808, 810, 812, 814, 816, 818, 820, 822, 824, 826, 828, 830, 832, 834, 836, 838, 840, 842, 844, 846, 848, 850, 852, 854, 856, 858, 860, 862, 864, 866, 868, 870, 872, 874, 876, 878, 880, 882, 884, 886, 888, 890, 892, 894, 896, 898, 900, 902, 904, 906, 908, 910, 912, 914, 916, 918, 920, 922, 924, 926, 928, 930, 932, 934, 936, 938, 940, 942, 944, 946, 948, 950, 952, 954, 956, 958, 960, 962, 964, 966, 968, 970, 972, 974, 976, 978, 980, 982, 984, 986, 988, 990, 992, 994, 996, 998, 1000], "y": [-0.032575757575757584, -0.1, -0.1875, -0.15, -0.016666666666666673, -0.032575757575757584], "name": "Negative", "mode": "markers", "marker": {"size": 10, "color": "rgb(230, 46, 0)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}], {"title": "Sentiment scatter plot for Vitamin (2010)", "yaxis": {"title": "Polarity", "zeroline": false}, "xaxis": {"title": "Statement #(not in original order)", "zeroline": false}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
def getNutrientPolarityTrendLineUsingTextBlob (nutrient):
    import numpy as np
    yearsList = np.arange(1980,2020,5)
    polarityMeansAcrossYearsList = []
    for i in yearsList:
        polarityMeansAcrossYearsList.append(normailizedMean(getNutrientRelevantStatementsPolarityListUsingTextBlob(year=str(i),nutrientName = nutrient)))
    data = [go.Scatter(
          x=np.arange(1980,2020,5),
          y=polarityMeansAcrossYearsList)]
    layout = dict(
         title = "Trends in the sentiment of " + nutrient + '(s) ' + '(1980-2015)' ,
         yaxis = dict(title = 'Average Polarity(Normalized)'),
         xaxis = dict(title = 'Year')
    )

    fig = dict(data=data, layout=layout)
    return fig;

  



    
```


```python
import plotly.plotly as py
init_notebook_mode(connected=True)

nutrientName = 'Carbohydrate'

iplot(getNutrientPolarityTrendLineUsingTextBlob(nutrientName))  
```


<script>requirejs.config({paths: { 'plotly': ['https://cdn.plot.ly/plotly-latest.min']},});if(!window.Plotly) {{require(['plotly'],function(plotly) {window.Plotly=plotly;});}}</script>



<div id="8b1dbd5a-06fe-4141-b971-8fff104a77de" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("8b1dbd5a-06fe-4141-b971-8fff104a77de", [{"type": "scatter", "x": [1980, 1985, 1990, 1995, 2000, 2005, 2010, 2015], "y": [0.005887223202038016, -0.0017968749999999999, -0.0024724702380952385, 0.004736483134920635, -0.008159722222222223, 0.01063904761904762, 0.0022434567901234567, 0.004726851851851853]}], {"title": "Trends in the sentiment of Carbohydrate(s) (1980-2015)", "yaxis": {"title": "Average Polarity(Normalized)"}, "xaxis": {"title": "Year"}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
def getNutrientRelevantStatementsPolarityDictionaryUsingTextBlob(year, nutrientName): 
    with open(year + '.txt', 'r') as myfile:
        text = myfile.read()
    text1 =text.replace('\n________________\n','\n')
    text2 = re.sub(r'\n([a-z]+)',r' \1', text1)
    list1 = [sentence for sentence in text2.split('\n')]
    list2 = []
    for i in list1:
        list2.append(i.split('.'))
        
    
    
    finalList = []
    
    for i in list2:
            for j in i:
                finalList.append(j)
    
    nutrientStatementList = []
    
    for i in finalList:
        if nutrientName.lower() in i:
            nutrientStatementList.append(i)
    
    
    dict = {}
    
    for i in nutrientStatementList:
            dict[i] = TextBlob(i).sentiment.polarity
        
        
    return dict; 



```


```python
def getNutrientRelevantStatementsPolarityDictionaryUsingVader(year, nutrientName): 
    with open(year + '.txt', 'r') as myfile:
        text = myfile.read()
    text1 =text.replace('\n________________\n','\n')
    text2 = re.sub(r'\n([a-z]+)',r' \1', text1)
    list1 = [sentence for sentence in text2.split('\n')]
    list2 = []
    for i in list1:
        list2.append(i.split('.'))
        
    
    
    finalList = []
    
    for i in list2:
            for j in i:
                finalList.append(j)
    
    nutrientStatementList = []
    
    for i in finalList:
        if nutrientName.lower() in i:
            nutrientStatementList.append(i)
    
    
    dict = {}
    
    for i in nutrientStatementList:
            dict[i] = (analyzer.polarity_scores(i))['compound']
        
        
    return dict; 


```


```python
for statement, polarity in getNutrientRelevantStatementsPolarityDictionaryUsingTextBlob(year = '2015', nutrientName = 'Carbohydrate').items():
    print('{} ==> {}'.format(statement, polarity))
```

    NOTE: The total eating pattern should not exceed Dietary Guidelines limits for intake of calories from added sugars and saturated fats and alcohol and should be within the Acceptable Macronutrient Distribution Ranges for calories from protein, carbohydrate, and total fats ==> 0.0
     On average, carbohydrates and protein contain 4 calories per gram, fats contain 9 calories per gram, and alcohol has 7 calories per gram ==> -0.15
     Strong evidence from mostly prospective cohort studies but also randomized controlled trials has shown that eating patterns that patterns can accommodate other nutrient- dense foods with small amounts of added sugars, such as whole-grain breakfast cereals or fat-free yogurt, as long as calories from added sugars do not exceed 10 percent per day, total carbohydrate intake remains within the AMDR, and total calorie intake remains within limits ==> 0.06354166666666666
     with carbohydrates reduces blood levels ==> 0.0
    Dietary Guidelines to limit consumption saturated fats with carbohydrates is not of dietary cholesterol to 300 mg per day associated with reduced risk of CVD ==> 0.0
     is not included in the 2015 edition, but Additional research is needed to determine this change does not suggest that dietary whether this relationship is consistent cholesterol is no longer important to consider across categories of carbohydrates (e ==> 0.325
     The OmniHeart Trial found that replacing some of the carbohydrates in DASH with the same amount of either protein or unsaturated fats lowered blood pressure and LDL-cholesterol levels more than the original DASH dietary pattern ==> 0.2916666666666667
     Additionally, healthy eating patterns can be flexible with respect to the intake of carbohydrate, protein, and fat within the context of the AMDR ==> 0.5
     Alcohol for additional guidance); and calories from protein, carbohydrate, and total fats should be within the Acceptable Macronutrient Distribution Ranges (AMDRs) ==> 0.0
     Dietary fiber consists of nondigestible carbohydrates and lignin that are intrinsic and intact in plants (i ==> 0.0
     Functional fiber consists of isolated, nondigestible carbohydrates that have beneficial physiological effects in humans ==> 0.0
    • Estimated Average Requirements (EAR)—The average daily Diabetes—A disorder of metabolism— nutrient intake level estimated to the way the body uses digested food meet the requirement of half the (specifically carbohydrate) for growth and healthy individuals in a particular energy ==> 0.03333333333333333
    , carbohydrate, ==> 0.0
     protein, fats, carbohydrates, and alcohol ==> 0.0



```python
for statement, polarity in getNutrientRelevantStatementsPolarityDictionaryUsingVader(year = '2015', nutrientName = 'Carbohydrate').items():
    print('{} ==> {}'.format(statement, polarity))
```

    NOTE: The total eating pattern should not exceed Dietary Guidelines limits for intake of calories from added sugars and saturated fats and alcohol and should be within the Acceptable Macronutrient Distribution Ranges for calories from protein, carbohydrate, and total fats ==> 0.3182
     On average, carbohydrates and protein contain 4 calories per gram, fats contain 9 calories per gram, and alcohol has 7 calories per gram ==> 0.0
     Strong evidence from mostly prospective cohort studies but also randomized controlled trials has shown that eating patterns that patterns can accommodate other nutrient- dense foods with small amounts of added sugars, such as whole-grain breakfast cereals or fat-free yogurt, as long as calories from added sugars do not exceed 10 percent per day, total carbohydrate intake remains within the AMDR, and total calorie intake remains within limits ==> 0.2846
     with carbohydrates reduces blood levels ==> 0.0
    Dietary Guidelines to limit consumption saturated fats with carbohydrates is not of dietary cholesterol to 300 mg per day associated with reduced risk of CVD ==> -0.2732
     is not included in the 2015 edition, but Additional research is needed to determine this change does not suggest that dietary whether this relationship is consistent cholesterol is no longer important to consider across categories of carbohydrates (e ==> -0.1531
     The OmniHeart Trial found that replacing some of the carbohydrates in DASH with the same amount of either protein or unsaturated fats lowered blood pressure and LDL-cholesterol levels more than the original DASH dietary pattern ==> -0.0352
     Additionally, healthy eating patterns can be flexible with respect to the intake of carbohydrate, protein, and fat within the context of the AMDR ==> 0.7717
     Alcohol for additional guidance); and calories from protein, carbohydrate, and total fats should be within the Acceptable Macronutrient Distribution Ranges (AMDRs) ==> 0.3182
     Dietary fiber consists of nondigestible carbohydrates and lignin that are intrinsic and intact in plants (i ==> 0.2023
     Functional fiber consists of isolated, nondigestible carbohydrates that have beneficial physiological effects in humans ==> 0.1531
    • Estimated Average Requirements (EAR)—The average daily Diabetes—A disorder of metabolism— nutrient intake level estimated to the way the body uses digested food meet the requirement of half the (specifically carbohydrate) for growth and healthy individuals in a particular energy ==> 0.5719
    , carbohydrate, ==> 0.0
     protein, fats, carbohydrates, and alcohol ==> 0.0



```python
from textblob import TextBlob
from textblob.sentiments import NaiveBayesAnalyzer
opinion = TextBlob("During digestion all carbohydrates except fiber break down into sugars", analyzer=NaiveBayesAnalyzer())
opinion.sentiment
```




    Sentiment(classification='neg', p_pos=0.06619867710721464, p_neg=0.9338013228927862)




```python
for statement, polarity in getNutrientRelevantStatementsPolarityDictionaryUsingTextBlob(year = '2000', nutrientName = 'Carbohydrate').items():
    print('{} ==> {}'.format(statement, polarity))
```

    The carbohydrates, fats, and proteins in food supply energy, which is measured in calories ==> 0.0
     oats) They provide vitamins, minerals, carbohydrates (starch and dietary fiber), and other substances that are important for good health ==> 0.325
     are carbohydrates Dietary carbohydrates and a source also include of energy the complex carbohydrates starch and dietary fiber ==> -0.3
     During digestion all carbohydrates except fiber break down into sugars ==> -0.15555555555555559



```python
def getNutrientRelevantStatementsPolarityListUsingVader(year, nutrientName): 
    with open(year + '.txt', 'r') as myfile:
        text = myfile.read()
    text1 =text.replace('\n________________\n','\n')
    text2 = re.sub(r'\n([a-z]+)',r' \1', text1)
    list1 = [sentence for sentence in text2.split('\n')]
    list2 = []
    for i in list1:
        list2.append(i.split('.'))
    
    finalList = []
    
    for i in list2:
            for j in i:
                finalList.append(j)
    
    nutrientStatementList = []
    
    for i in finalList:
        if nutrientName.lower() in i:
            nutrientStatementList.append(i)
    
    
    statementsPolarityList = []
    
    for i in nutrientStatementList:
            statementsPolarityList.append((analyzer.polarity_scores(i))['compound'])
        
        
    return statementsPolarityList; 


```


```python
def getNutrientPolarityTrendLineUsingVader (nutrient):
    import numpy as np
    yearsList = np.arange(1980,2020,5)
    polarityMeansAcrossYearsList = []
    for i in yearsList:
        polarityMeansAcrossYearsList.append(normailizedMean(getNutrientRelevantStatementsPolarityListUsingVader(year=str(i),nutrientName = nutrient)))
    data = [go.Scatter(
          x=np.arange(1980,2020,5),
          y=polarityMeansAcrossYearsList)]
    layout = dict(
         title = "Trends in the sentiment of " + nutrient + '(s) ' + '(1980-2015)' ,
         yaxis = dict(title = 'Average Polarity(Normalized)'),
         xaxis = dict(title = 'Year')
    )

    fig = dict(data=data, layout=layout)
    return fig;
```


```python
import plotly.plotly as py
init_notebook_mode(connected=True)

nutrientName = 'Carbohydrate'

iplot(getNutrientPolarityTrendLineUsingVader(nutrientName)) 
```


<script>requirejs.config({paths: { 'plotly': ['https://cdn.plot.ly/plotly-latest.min']},});if(!window.Plotly) {{require(['plotly'],function(plotly) {window.Plotly=plotly;});}}</script>



<div id="bddad512-cb24-4fbd-8b76-52b731536442" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("bddad512-cb24-4fbd-8b76-52b731536442", [{"type": "scatter", "x": [1980, 1985, 1990, 1995, 2000, 2005, 2010, 2015], "y": [0.030590123456790123, 0.059268749999999995, 0.0109375, 0.015426562500000001, 0.06989375, 0.013781000000000002, 0.004223111111111111, 0.011007555555555555]}], {"title": "Trends in the sentiment of Carbohydrate(s) (1980-2015)", "yaxis": {"title": "Average Polarity(Normalized)"}, "xaxis": {"title": "Year"}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
import plotly.plotly as py
init_notebook_mode(connected=True)

nutrientName = 'Carbohydrate'

iplot(getNutrientPolarityTrendLineUsingTextBlob(nutrientName)) 
```


<script>requirejs.config({paths: { 'plotly': ['https://cdn.plot.ly/plotly-latest.min']},});if(!window.Plotly) {{require(['plotly'],function(plotly) {window.Plotly=plotly;});}}</script>



<div id="67c56195-ee72-4a39-a407-f57915827f5f" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("67c56195-ee72-4a39-a407-f57915827f5f", [{"type": "scatter", "x": [1980, 1985, 1990, 1995, 2000, 2005, 2010, 2015], "y": [0.005887223202038016, -0.0017968749999999999, -0.0024724702380952385, 0.004736483134920635, -0.008159722222222223, 0.01063904761904762, 0.0022434567901234567, 0.004726851851851853]}], {"title": "Trends in the sentiment of Carbohydrate(s) (1980-2015)", "yaxis": {"title": "Average Polarity(Normalized)"}, "xaxis": {"title": "Year"}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
requiredNutrient = 'Vitamin'
requiredYear = '2010'

iplot(plotPolarityScatterPlot(nutrient = requiredNutrient,nutrientStatementPolarityList = getNutrientRelevantStatementsPolarityListUsingTextBlob(year = requiredYear,nutrientName = requiredNutrient ), year = requiredYear), filename='sugar-polarity-scatter-2015')
```


<div id="37fd0e02-ad54-4cd3-acb4-2686f039e957" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("37fd0e02-ad54-4cd3-acb4-2686f039e957", [{"type": "scatter", "x": [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99, 101, 103, 105, 107, 109, 111, 113, 115, 117, 119, 121, 123, 125, 127, 129, 131, 133, 135, 137, 139, 141, 143, 145, 147, 149, 151, 153, 155, 157, 159, 161, 163, 165, 167, 169, 171, 173, 175, 177, 179, 181, 183, 185, 187, 189, 191, 193, 195, 197, 199, 201, 203, 205, 207, 209, 211, 213, 215, 217, 219, 221, 223, 225, 227, 229, 231, 233, 235, 237, 239, 241, 243, 245, 247, 249, 251, 253, 255, 257, 259, 261, 263, 265, 267, 269, 271, 273, 275, 277, 279, 281, 283, 285, 287, 289, 291, 293, 295, 297, 299, 301, 303, 305, 307, 309, 311, 313, 315, 317, 319, 321, 323, 325, 327, 329, 331, 333, 335, 337, 339, 341, 343, 345, 347, 349, 351, 353, 355, 357, 359, 361, 363, 365, 367, 369, 371, 373, 375, 377, 379, 381, 383, 385, 387, 389, 391, 393, 395, 397, 399, 401, 403, 405, 407, 409, 411, 413, 415, 417, 419, 421, 423, 425, 427, 429, 431, 433, 435, 437, 439, 441, 443, 445, 447, 449, 451, 453, 455, 457, 459, 461, 463, 465, 467, 469, 471, 473, 475, 477, 479, 481, 483, 485, 487, 489, 491, 493, 495, 497, 499, 501, 503, 505, 507, 509, 511, 513, 515, 517, 519, 521, 523, 525, 527, 529, 531, 533, 535, 537, 539, 541, 543, 545, 547, 549, 551, 553, 555, 557, 559, 561, 563, 565, 567, 569, 571, 573, 575, 577, 579, 581, 583, 585, 587, 589, 591, 593, 595, 597, 599, 601, 603, 605, 607, 609, 611, 613, 615, 617, 619, 621, 623, 625, 627, 629, 631, 633, 635, 637, 639, 641, 643, 645, 647, 649, 651, 653, 655, 657, 659, 661, 663, 665, 667, 669, 671, 673, 675, 677, 679, 681, 683, 685, 687, 689, 691, 693, 695, 697, 699, 701, 703, 705, 707, 709, 711, 713, 715, 717, 719, 721, 723, 725, 727, 729, 731, 733, 735, 737, 739, 741, 743, 745, 747, 749, 751, 753, 755, 757, 759, 761, 763, 765, 767, 769, 771, 773, 775, 777, 779, 781, 783, 785, 787, 789, 791, 793, 795, 797, 799, 801, 803, 805, 807, 809, 811, 813, 815, 817, 819, 821, 823, 825, 827, 829, 831, 833, 835, 837, 839, 841, 843, 845, 847, 849, 851, 853, 855, 857, 859, 861, 863, 865, 867, 869, 871, 873, 875, 877, 879, 881, 883, 885, 887, 889, 891, 893, 895, 897, 899, 901, 903, 905, 907, 909, 911, 913, 915, 917, 919, 921, 923, 925, 927, 929, 931, 933, 935, 937, 939, 941, 943, 945, 947, 949, 951, 953, 955, 957, 959, 961, 963, 965, 967, 969, 971, 973, 975, 977, 979, 981, 983, 985, 987, 989, 991, 993, 995, 997, 999], "y": [0.25, 0.26666666666666666, 0.03125, 0.03787878787878787, 0.2, 0.1, 0.11363636363636363, 0.25, 0.26666666666666666, 0.2708333333333333, 0.13333333333333333, 0.5, 0.09999999999999999, 0.05000000000000002, 0.5, 0.24166666666666664, 0.03333333333333333, 0.41666666666666663, 0.5583333333333333, 0.375, 0.012500000000000004, 0.2833333333333333, 0.41111111111111115, 0.21458333333333335, 0.25, 0.1, 0.15, 0.2833333333333333, 0.25, 0.3333333333333333, 0.28125, 0.5, 0.11704545454545455, 0.1, 0.3333333333333333, 0.04666666666666667, 0.15, 0.5, 0.1, 0.5], "name": "Positive", "mode": "markers", "marker": {"size": 10, "color": "rgba(0, 153, 51, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122, 124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150, 152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178, 180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206, 208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234, 236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260, 262, 264, 266, 268, 270, 272, 274, 276, 278, 280, 282, 284, 286, 288, 290, 292, 294, 296, 298, 300, 302, 304, 306, 308, 310, 312, 314, 316, 318, 320, 322, 324, 326, 328, 330, 332, 334, 336, 338, 340, 342, 344, 346, 348, 350, 352, 354, 356, 358, 360, 362, 364, 366, 368, 370, 372, 374, 376, 378, 380, 382, 384, 386, 388, 390, 392, 394, 396, 398, 400, 402, 404, 406, 408, 410, 412, 414, 416, 418, 420, 422, 424, 426, 428, 430, 432, 434, 436, 438, 440, 442, 444, 446, 448, 450, 452, 454, 456, 458, 460, 462, 464, 466, 468, 470, 472, 474, 476, 478, 480, 482, 484, 486, 488, 490, 492, 494, 496, 498, 500, 502, 504, 506, 508, 510, 512, 514, 516, 518, 520, 522, 524, 526, 528, 530, 532, 534, 536, 538, 540, 542, 544, 546, 548, 550, 552, 554, 556, 558, 560, 562, 564, 566, 568, 570, 572, 574, 576, 578, 580, 582, 584, 586, 588, 590, 592, 594, 596, 598, 600, 602, 604, 606, 608, 610, 612, 614, 616, 618, 620, 622, 624, 626, 628, 630, 632, 634, 636, 638, 640, 642, 644, 646, 648, 650, 652, 654, 656, 658, 660, 662, 664, 666, 668, 670, 672, 674, 676, 678, 680, 682, 684, 686, 688, 690, 692, 694, 696, 698, 700, 702, 704, 706, 708, 710, 712, 714, 716, 718, 720, 722, 724, 726, 728, 730, 732, 734, 736, 738, 740, 742, 744, 746, 748, 750, 752, 754, 756, 758, 760, 762, 764, 766, 768, 770, 772, 774, 776, 778, 780, 782, 784, 786, 788, 790, 792, 794, 796, 798, 800, 802, 804, 806, 808, 810, 812, 814, 816, 818, 820, 822, 824, 826, 828, 830, 832, 834, 836, 838, 840, 842, 844, 846, 848, 850, 852, 854, 856, 858, 860, 862, 864, 866, 868, 870, 872, 874, 876, 878, 880, 882, 884, 886, 888, 890, 892, 894, 896, 898, 900, 902, 904, 906, 908, 910, 912, 914, 916, 918, 920, 922, 924, 926, 928, 930, 932, 934, 936, 938, 940, 942, 944, 946, 948, 950, 952, 954, 956, 958, 960, 962, 964, 966, 968, 970, 972, 974, 976, 978, 980, 982, 984, 986, 988, 990, 992, 994, 996, 998, 1000], "y": [-0.032575757575757584, -0.1, -0.1875, -0.15, -0.016666666666666673, -0.032575757575757584], "name": "Negative", "mode": "markers", "marker": {"size": 10, "color": "rgb(230, 46, 0)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}], {"title": "Sentiment scatter plot for Vitamin (2010)", "yaxis": {"title": "Polarity", "zeroline": false}, "xaxis": {"title": "Statement #(not in original order)", "zeroline": false}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>



```python
requiredNutrient = 'Vitamin'
requiredYear = '2010'

iplot(plotPolarityScatterPlot(nutrient = requiredNutrient,nutrientStatementPolarityList = getNutrientRelevantStatementsPolarityListUsingVader(year = requiredYear,nutrientName = requiredNutrient ), year = requiredYear), filename='sugar-polarity-scatter-2015')
```


<div id="4c494d96-defd-49ee-b321-fb06520fdc94" style="height: 525px; width: 100%;" class="plotly-graph-div"></div><script type="text/javascript">require(["plotly"], function(Plotly) { window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("4c494d96-defd-49ee-b321-fb06520fdc94", [{"type": "scatter", "x": [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99, 101, 103, 105, 107, 109, 111, 113, 115, 117, 119, 121, 123, 125, 127, 129, 131, 133, 135, 137, 139, 141, 143, 145, 147, 149, 151, 153, 155, 157, 159, 161, 163, 165, 167, 169, 171, 173, 175, 177, 179, 181, 183, 185, 187, 189, 191, 193, 195, 197, 199, 201, 203, 205, 207, 209, 211, 213, 215, 217, 219, 221, 223, 225, 227, 229, 231, 233, 235, 237, 239, 241, 243, 245, 247, 249, 251, 253, 255, 257, 259, 261, 263, 265, 267, 269, 271, 273, 275, 277, 279, 281, 283, 285, 287, 289, 291, 293, 295, 297, 299, 301, 303, 305, 307, 309, 311, 313, 315, 317, 319, 321, 323, 325, 327, 329, 331, 333, 335, 337, 339, 341, 343, 345, 347, 349, 351, 353, 355, 357, 359, 361, 363, 365, 367, 369, 371, 373, 375, 377, 379, 381, 383, 385, 387, 389, 391, 393, 395, 397, 399, 401, 403, 405, 407, 409, 411, 413, 415, 417, 419, 421, 423, 425, 427, 429, 431, 433, 435, 437, 439, 441, 443, 445, 447, 449, 451, 453, 455, 457, 459, 461, 463, 465, 467, 469, 471, 473, 475, 477, 479, 481, 483, 485, 487, 489, 491, 493, 495, 497, 499, 501, 503, 505, 507, 509, 511, 513, 515, 517, 519, 521, 523, 525, 527, 529, 531, 533, 535, 537, 539, 541, 543, 545, 547, 549, 551, 553, 555, 557, 559, 561, 563, 565, 567, 569, 571, 573, 575, 577, 579, 581, 583, 585, 587, 589, 591, 593, 595, 597, 599, 601, 603, 605, 607, 609, 611, 613, 615, 617, 619, 621, 623, 625, 627, 629, 631, 633, 635, 637, 639, 641, 643, 645, 647, 649, 651, 653, 655, 657, 659, 661, 663, 665, 667, 669, 671, 673, 675, 677, 679, 681, 683, 685, 687, 689, 691, 693, 695, 697, 699, 701, 703, 705, 707, 709, 711, 713, 715, 717, 719, 721, 723, 725, 727, 729, 731, 733, 735, 737, 739, 741, 743, 745, 747, 749, 751, 753, 755, 757, 759, 761, 763, 765, 767, 769, 771, 773, 775, 777, 779, 781, 783, 785, 787, 789, 791, 793, 795, 797, 799, 801, 803, 805, 807, 809, 811, 813, 815, 817, 819, 821, 823, 825, 827, 829, 831, 833, 835, 837, 839, 841, 843, 845, 847, 849, 851, 853, 855, 857, 859, 861, 863, 865, 867, 869, 871, 873, 875, 877, 879, 881, 883, 885, 887, 889, 891, 893, 895, 897, 899, 901, 903, 905, 907, 909, 911, 913, 915, 917, 919, 921, 923, 925, 927, 929, 931, 933, 935, 937, 939, 941, 943, 945, 947, 949, 951, 953, 955, 957, 959, 961, 963, 965, 967, 969, 971, 973, 975, 977, 979, 981, 983, 985, 987, 989, 991, 993, 995, 997, 999], "y": [0.296, 0.296, 0.296, 0.296, 0.7717, 0.5106, 0.5106, 0.6369, 0.0258, 0.296, 0.296, 0.296, 0.5574, 0.5574, 0.5267, 0.4767, 0.2382, 0.296, 0.6908, 0.5267, 0.296, 0.4215, 0.296, 0.296, 0.7845, 0.4215, 0.4767, 0.296, 0.6415, 0.5719, 0.7506, 0.5106, 0.5994, 0.6968, 0.4588, 0.296, 0.4767, 0.296, 0.5106, 0.296, 0.6705, 0.296, 0.4588, 0.5423, 0.296, 0.5574, 0.5267, 0.296, 0.743, 0.296, 0.296, 0.6486, 0.6908, 0.4588, 0.5719, 0.296, 0.296, 0.296, 0.6289, 0.296, 0.296, 0.5574], "name": "Positive", "mode": "markers", "marker": {"size": 10, "color": "rgba(0, 153, 51, .8)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}, {"type": "scatter", "x": [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122, 124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150, 152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178, 180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206, 208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234, 236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260, 262, 264, 266, 268, 270, 272, 274, 276, 278, 280, 282, 284, 286, 288, 290, 292, 294, 296, 298, 300, 302, 304, 306, 308, 310, 312, 314, 316, 318, 320, 322, 324, 326, 328, 330, 332, 334, 336, 338, 340, 342, 344, 346, 348, 350, 352, 354, 356, 358, 360, 362, 364, 366, 368, 370, 372, 374, 376, 378, 380, 382, 384, 386, 388, 390, 392, 394, 396, 398, 400, 402, 404, 406, 408, 410, 412, 414, 416, 418, 420, 422, 424, 426, 428, 430, 432, 434, 436, 438, 440, 442, 444, 446, 448, 450, 452, 454, 456, 458, 460, 462, 464, 466, 468, 470, 472, 474, 476, 478, 480, 482, 484, 486, 488, 490, 492, 494, 496, 498, 500, 502, 504, 506, 508, 510, 512, 514, 516, 518, 520, 522, 524, 526, 528, 530, 532, 534, 536, 538, 540, 542, 544, 546, 548, 550, 552, 554, 556, 558, 560, 562, 564, 566, 568, 570, 572, 574, 576, 578, 580, 582, 584, 586, 588, 590, 592, 594, 596, 598, 600, 602, 604, 606, 608, 610, 612, 614, 616, 618, 620, 622, 624, 626, 628, 630, 632, 634, 636, 638, 640, 642, 644, 646, 648, 650, 652, 654, 656, 658, 660, 662, 664, 666, 668, 670, 672, 674, 676, 678, 680, 682, 684, 686, 688, 690, 692, 694, 696, 698, 700, 702, 704, 706, 708, 710, 712, 714, 716, 718, 720, 722, 724, 726, 728, 730, 732, 734, 736, 738, 740, 742, 744, 746, 748, 750, 752, 754, 756, 758, 760, 762, 764, 766, 768, 770, 772, 774, 776, 778, 780, 782, 784, 786, 788, 790, 792, 794, 796, 798, 800, 802, 804, 806, 808, 810, 812, 814, 816, 818, 820, 822, 824, 826, 828, 830, 832, 834, 836, 838, 840, 842, 844, 846, 848, 850, 852, 854, 856, 858, 860, 862, 864, 866, 868, 870, 872, 874, 876, 878, 880, 882, 884, 886, 888, 890, 892, 894, 896, 898, 900, 902, 904, 906, 908, 910, 912, 914, 916, 918, 920, 922, 924, 926, 928, 930, 932, 934, 936, 938, 940, 942, 944, 946, 948, 950, 952, 954, 956, 958, 960, 962, 964, 966, 968, 970, 972, 974, 976, 978, 980, 982, 984, 986, 988, 990, 992, 994, 996, 998, 1000], "y": [-0.5256, -0.3182, -0.5319, -0.3089], "name": "Negative", "mode": "markers", "marker": {"size": 10, "color": "rgb(230, 46, 0)", "line": {"width": 2, "color": "rgb(0, 0, 0)"}}}], {"title": "Sentiment scatter plot for Vitamin (2010)", "yaxis": {"title": "Polarity", "zeroline": false}, "xaxis": {"title": "Statement #(not in original order)", "zeroline": false}}, {"showLink": true, "linkText": "Export to plot.ly"})});</script>

