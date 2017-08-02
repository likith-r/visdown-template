 # Visdown

  **Make visualisations using only markdown**

  Write visualisation using a simple declarative markup like you would write code. Just wrap it in fenced block (three backticks) and mark the language as `vis`.

  *Make simple static visualisations*

  ```vis
  data:
    url: data/cars.csv
  mark: point
  encoding:
    x:
      type: quantitative
      field: kmpl
    y:
      type: quantitative
      field: price

  ```




  Visdown is based on the grammar of interactive graphic (vega-lite) which allows you to specify the visualisation including interactions in a declarative fashion.

  *Make interactive visualisations*

  Select the circles with the mouse

  ```vis
  data:
    url: "data/cars.csv"
  mark: circle
  selection:
    brush:
      type: interval
  encoding:
    x:
      type: quantitative
      field: kmpl
      scale:
       domain: [12,25]
    y:
      type: quantitative
      field: price
      scale:
       domain: [100,900]
    color:
      condition:
        selection: brush
        field: type
        type: nominal
      value: grey
    size:
      type: quantitative
      field: bhp
  width: 450
  height: 300
  ```    
    

*Tested code*
```vis
width: 700
height: 500

data:
  url: data/notes.csv

    
mark: area
encoding:
  x:
    timeUnit: year
    type: temporal
    field: year
  y:
    field: money
    type: quantitative
    aggregate: sum
  color:
    type: nominal
    field: denom
```


# ranking

<h1> Hello </h1>






```vis
width: 700
height: 500

data:
  url: data/notes.csv

    
mark: bar

encoding:
  x:
    
    type: nominal
    field: denom
  y:
    field: number
    type: quantitative
  color:
    type: nominal
    field: denom

```

<h1> distribution </h1>


```vis
width: 700
height: 500

data:
  url: data/notes.csv

    
mark: bar

encoding:
  x:
    
    type: quantitative
    field: money
  y:
    field: denom
    type: nominal
  color:
    type: nominal
    field: denom

```

<h1> concat </h1>


```vis
width: 700
height: 500

data:
  url: data/notes.csv
layer:
  -mark:bar


encoding:
  y:
    
    type: nominal
    field: denom
  x:
    field: number
    type: quantitative
  color:
    type: nominal
    field: denom



    
layer:
  -mark:point

encoding:
  y:
    
    type: nominal
    field: denom
  x:
    field: number
    type: quantitative
  color:
    type: nominal
    field: denom

```