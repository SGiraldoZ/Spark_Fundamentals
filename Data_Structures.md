# Main Data Structures in Spark

> The main data structures in spark are called RDDs and Dataframes

## RDDs
It's the main data structure since spark has been around. The data is distributed around the cluster running spark.

- They have no specific shape. So they're adaptable to the most adequate.

- They are also immutable

- Lazy evaluation. Bits of code are not used until absolutely needed.

### Important distinction. Transformations vs Actions


    | Transformations | Actions  |
    |-----------------|----------|
    |OrderBy()        |Show()    |
    |groupBy()        | take()   |
    |filter()         | count()  |
    |select()         | collect()|
    |join()           | save()   |


### Code Example On RDDs

```
    pedroParamo = sc.textFile("pedroParamo.txt")

    comala = pedroParamo.filter(lambda l: "Comala" in l)

    paramo = pedroParamo.filter(lamdba l: "Páramo" in l)

    comalaInterParamo = comala.intersection(paramo)

    cuenta = comalaInterParamo.count()
```

Here, we can have errors in all of the lines up to the last one, since the .count() is the one where an output is forced, the other lines are lazy. And only run when count needs them

## DataFrames

They are built on top of the RDD's. 

- They main difference is they have structure. Columns with data types

- They are easier to create from an external data source or from an RDD


## When To Use

If DataFrames are more comfortable, and also more efficient generally than RDD's

#### Should RDD's ever be used?

Yes, they should for one of the following reasons:

- To have more low level control of spark flow

- If you are using Python, it allows for greater data control converting to a native Python data structure

- They are backwards compatible into legacy spark

#### And When to use DataFrames

- When there are complicated data semantics

- When we are running High-level tasks. Such as filters, maps, agregates, avgs, etc

- SQL like syntax can be used on this data structures