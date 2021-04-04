## Core components of pandas: Series and DataFrames

- The primary two components of pandas are the `Series` and 
  `DataFrame`.
  - A `Series` is essentially a `column`
  - a `DataFrame` is a `multi-dimensional` table made up of a 
    collection of `Series`.

![](img/2021-03-26-22-30-08.png)

![](img/2021-03-26-22-45-44.png)

![](img/2021-03-26-22-48-35.png)

![](img/2021-03-27-00-05-47.png)

-----

![](img/2021-03-27-00-32-33.png)


---

![](img/2021-03-27-02-01-28.png)

```py
df.loc[1].at[2] = 55 # row 2, column 2
df[2][1] = 55 # column 2, row 1
print(df)

#    0  1   2
# 0  1  2   3
# 1  4  5  55
# 2  7  8   9
```

---

![](img/2021-03-27-02-27-18.png)