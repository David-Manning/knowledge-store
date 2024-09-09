## Python

For files on S3, pandas works out of the box using S3 URI, which is in the format "s3://bucket_name/folder_name/file.csv" - this should be given as though it were a file name.

### CSV
```python
import pandas as pd
df = pd.read_csv("/home/david/Documents/Temp/test.csv")
df.to_csv("/home/david/Documents/Temp/test.csv", index = False)
```

### JSON
```python
import pandas as pd
df = pd.read_json("/home/david/Documents/Temp/test.json")
df.to_json("/home/david/Documents/Temp/test.json")
```

### Parquet
```python
import pandas as pd
df = pd.read_parquet("/home/david/Documents/Temp/test.parquet")
df.to_parquet("/home/david/Documents/Temp/test.parquet")
```

### Excel
```python
import pandas as pd
df = pd.read_excel("/home/david/Documents/Temp/test.xlsx")
df.to_excel("/home/david/Documents/Temp/test.xlsx", index = False)
```
