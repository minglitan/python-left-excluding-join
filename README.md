# Left Excluding Join (Python)
This is a simple Python script to compare data in two Excel files and return rows which are unique to the first Excel workbook.

Replace/rename these portions of the code for your purpose:
1. **Book1** : the Excel file to reference
2. **Book2** : the Excel file to compare against
3. **name** : usually your username
4. **Desktop** : refers to the location of the Excel file (you can change this path/location as needed)
5. **Temp_ID** : a column name that is used in both Excel files (change this to whichever column you want to compare in both Excel files)
6. **Output.xlsx** : a generated Excel file that contains rows of data from Book1 that are not in Book2

## Code:
```python
#import pandas
import pandas as pd

#import the notebooks
df1 = pd.read_excel(r"C:\Users\name\Desktop\Book1.xlsx")
df2 = pd.read_excel(r"C:\Users\name\Desktop\Book2.xlsx")

#do a left-excluding join
merged_df = pd.merge(df1, df2, on="Temp_ID", how="left", indicator=True)
left_excluding_df = merged_df.query('_merge == "left_only" ').drop(columns=['_merge'])

#export to Excel
left_excluding_df.to_excel(r"C:\Users\name\Desktop\Output.xlsx", index=False)

```

Feel free to explore and customize this project to suit your requirements. Happy coding!
