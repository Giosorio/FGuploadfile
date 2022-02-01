# FGUploadFile
Class UploadFile creates an object UploadFile that allows to to split the description and content from a Fieldglass upload file. Once the content has been modified it allows you to concatenate the description again.


# HOW TO IMPORT
**import** pandas **as** pd

**from** FGUploadFile **import** uploadfile **as** upf
```
import pandas as pd
from FGUploadFile import uploadfile as upf

df = pd.read_excel('xl_files/FG_BU_download.xlsx')
print(df)

upf_1 = upf.UploadFile(df)
```

## Description
```
print(upf_1.description)

                         Type=Business Unit Upload  ...                              
0                                 Transaction=True  ...                   NaN
1                 Language=English (United States)  ...                   NaN
2   Number Format=#,##9.99 (Example: 1,234,567.99)  ...                   NaN
3                           Date Format=MM/DD/YYYY  ...                   NaN
4                                        Comments=  ...                   NaN
5                                              NaN  
```

## Content
```
print(upf_1.content)

                                 Modification Type  ...          Legal Entity
7                                                A  ...        Legal_Entity_1
8                                                A  ...        Legal_Entity_2
9                                                A  ...        Legal_Entity_3
10                                               A  ...        Legal_Entity_4
```


## Complete, concatenate Description and Content
```
print(upf_1.complete)

                         Type=Business Unit Upload  ...                              
0                                 Transaction=True  ...                   NaN
1                 Language=English (United States)  ...                   NaN
2   Number Format=#,##9.99 (Example: 1,234,567.99)  ...                   NaN
3                           Date Format=MM/DD/YYYY  ...                   NaN
4                                        Comments=  ...                   NaN
5                                              NaN  ...                   NaN
6                                Modification Type  ...          Legal Entity
7                                                A  ...        Legal_Entity_1
8                                                A  ...        Legal_Entity_2
9                                                A  ...        Legal_Entity_3
10                                               A  ...        Legal_Entity_4
```

## Download CSV format, it marks the date and time the download is generated and allows you to put a comment (optional)
```
upf_1.download_csv('BU_UPLOAD.csv', comms='[COMMENT]')

>>>
                         Type=Business Unit Upload  ...                              
0                                 Transaction=True  ...                   NaN
1                 Language=English (United States)  ...                   NaN
2   Number Format=#,##9.99 (Example: 1,234,567.99)  ...                   NaN
3                           Date Format=MM/DD/YYYY  ...                   NaN
4          Comments=[COMMENT] 01/02/2022, 19:46:17  ...                   NaN
5                                              NaN  ...                   NaN
6                                Modification Type  ...          Legal Entity
7                                                A  ...        Legal_Entity_1
8                                                A  ...        Legal_Entity_2
9                                                A  ...        Legal_Entity_3
10                                               A  ...        Legal_Entity_4
```


# HOW TO INSTALL IN YOUR ENVIRONMENT

```
pip install git+https://github.com/Giosorio/FGUploadFile@[VERSION -- Check in Tags of the repository]
```
