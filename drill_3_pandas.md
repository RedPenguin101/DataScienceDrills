# Chapter 3: Pandas

## Series
### Basics
1. create a Series of 4 floats
2. print the values of the Series
3. print the index of the Series
4. return the 2nd element of the Series
5. return the 2nd and 3rd elements of the Series using slicing
6. create a Series of 4 floats with an index of the letters a-d
7. Now use index notation to return the 'b' indexed value
8. use index slicing to return a subset of the Series
9. create a series with index [100,200,300], with all values being 5

## Dataframe basis
```
area_dict = {'California': 423967, 'Texas': 695662, 'New York': 141297,
             'Florida': 170312, 'Illinois': 149995}
population_dict = {'California': 38332521,
                           'Texas': 26448193,
                           'New York': 19651127,
                           'Florida': 19552860,
                           'Illinois': 12882135}
```

1. Create series from these dictionaries
2. Create a dataframe from these series using dictionary notation
3. return the index of the dataframe
4. return the names of the columns
5. return the area series
6. Why should you think about dataframes as specialised dictionaries, not specialised arrays?
 
## Datafram contruction
1. create a df from a series, specifying the column name

```
data = [{'a':i, 'b':2*i} for i in range(3)]
```

2. create a dataframe from this data
3. create a dataframe from two series, using dictionary notation
4. creata a dataframe from a 3x2 numpy array, with cols foo and bar and index a,b,c`

