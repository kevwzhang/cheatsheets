**get subset of main dataframe isolating specific columns**
```
df['column_name1', 'column_name2']
```

**get all values in dataframe**
```
df.values
```

**get value at specified row/column pair**
```
df.at[4, 'B'] #int row index and string name of column
```

**print out entire dataframe**
```
with pd.option_context('display.max_rows', None, 'display.max_columns', None):  #more options can be specified also
    print(df)
```

**convert dataframe to dict where a column is a unique key**
```
df.set_index('id').to_dict()
```

**get data type of pandas column(s)**
```
df.column.dtype #specific single column data type
df.dtypes #all column data types
```
