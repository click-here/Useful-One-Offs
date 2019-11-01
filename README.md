# Useful-One-Offs

## Pandas
```python
df['Column'].value_counts()
```
[value_counts](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.value_counts.html) is syntactically more convenient than using goupby to get simple counts

Get unique count of values in all columns
```python
df.nunique()
```
See rows are duplicated 
```python
df.loc[df.duplicated(keep=False)].sort_values(by=0)
```

Bin as new column
```python
df = pd.DataFrame(np.random.randint(0,100,size=(100, 1)),columns=['score'])
bins = [0,50,100]
df['binned'] = pd.cut(df['score'],bins=bins, labels=['Low','High'])
```

Compare 2 columns with fuzzywuzzy library

```python
from fuzzywuzzy import fuzz
df =  pd.DataFrame(data={'Name1': ['Jane Doe', 'Bill Smith','Carrie Riddlesman'], 'Name2': ['Jan Doe', 'Bill Smith','Kerry Riddlesman']}
)
def compare_names(x,y):
    return fuzz.ratio(x,y)
df['name_compare'] = df[['Name1','Name2']].apply(lambda x: compare_names(*x), axis=1)
```

Between
```python
df = pd.DataFrame(np.random.randint(0,100,size=(100, 1)),columns=['score'])
df.loc[df['score'].between(25, 50, inclusive=False)]
```
## Grep
Find lines in file with both strings in them.
```console
grep 'some_string' file.txt | grep 'other_string' 
```
[FFMPEG Simple Reference](https://github.com/click-here/Useful-One-Offs/blob/master/ffmpeg.md)

#### pdf2text.exe

pdftotext [options] [PDF-file [text-file]]
