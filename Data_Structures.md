# Main Data Structures in Spark

> The main data structures in spark are called RDDs and Dataframes

### RDDs
It's the main data structure since spark has been around. The data is distributed around the cluster running spark.

They have no specific shape. So they're adaptable to the most adequate.

They are also immutable

Lazy evaluation. Bits of code are not used until absolutely needed.

## Important distinction. Transformations vs Actions


    | Transformations | Actions  |
    |-----------------|----------|
    |OrderBy()        |Show()    |
    |groupBy()        | take()   |
    |filter()         | count()  |
    |select()         | collect()|
    |join()           | save()   |