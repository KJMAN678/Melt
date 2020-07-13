# melt
python の melt() でグラフ化しやすいデータに加工してみた

import pandas as pd

### データの作成
df = pd.DataFrame(data=[('a',1,2,3,4,5,6,7),('b',8,9,10,11,12,13,14),
                        ('c',15,16,17,18,19,20,21),('d',22,23,24,25,26,27,28),
                        ('e',29,30,31,32,33,34,35),('f',36,37,38,39,40,41,42),
                        ('g',43,44,45,46,47,48,49)])

df.columns = ['category', 'Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']

df_m = pd.melt(df, id_vars=['category'], 
              value_vars=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'],
              var_name = "Day of the week", value_name = "Num")
