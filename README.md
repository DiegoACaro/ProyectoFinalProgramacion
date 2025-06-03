En orden, se creó el dataset original desde: https://archive.ics.uci.edu/dataset/891/cdc%2Bdiabetes%2Bhealth%2Bindicators 

```
from ucimlrepo import fetch_ucirepo 
import pandas as pd


# fetch dataset 
cdc_diabetes_health_indicators = fetch_ucirepo(id=891) 
  
# data (as pandas dataframes) 
X = cdc_diabetes_health_indicators.data.features 
y = cdc_diabetes_health_indicators.data.targets 
  
# metadata 
print(cdc_diabetes_health_indicators.metadata) 
  
# variable information 
print(cdc_diabetes_health_indicators.variables) 

# ---------------------------------------------------------

# Combina las features y el target en un solo DataFrame
df = pd.concat([X, y], axis=1)

# Guarda el DataFrame en un archivo CSV
df.to_csv("06 - dataset_original.csv", index=False)
```

