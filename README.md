# data-export
ais ma yh hotah haa  ky hum data ko dataframe ma sy muktaleef  export formate ma convert krty haa jis tarah to_htlm, to_json, to_csv,  to_json  ma




# ============================== fetch the data form csv file that convert data frame that fetch any coluum then that coonvert into
#        csv file through thee to_csv

# import pandas as pd
# pd=pd.read_csv('deliveries.csv')
# print(pd)
# print(pd.info())
# pf=pd.groupby('batsman')['batsman_runs'].sum().reset_index()



# ======================   abb hum ne csv file ko hum excel ky formate ma cnvert krna haa



# import pandas as pd
# pd=pd.read_csv('deliveries.csv')
# print(pd)
# print(pd.info())
# pf=pd.groupby('batsman')['batsman_runs'].sum()
# pff=pf.to_excel('ipl_batsman_total_runs.xlsx',index=False)
# print(pff)



# import pandas as pd
#
# df = pd.read_csv('deliveries.csv')
#
# pf = df.groupby('batsman')['batsman_runs'].sum()
#
# pff=pf.to_excel('ipl_batsman_total_runs.xlsx', index=False)
# print(pff)



# ===========================  abb hum nee  aus ko to_HTML ma convert krna haa  =======================

# import pandas as pd
#
# # Step 1: Read the dataset
# df = pd.read_csv('deliveries.csv')
# print(df.info())
#
# # Step 2: Use pivot_table correctly (not pd.pivot)
# pff = df.query('batsman_runs == 6').pivot_table(index='over', columns='ball', values='batsman_runs', aggfunc='count').to_html('sixes_heatmap.HTML')
#
#
# # Step 3: Print result
# print(pff)





#    ===================   abb joo humary ppass data haa  aus ko huum ne json ki format ma tabdeel  krna haa==========


import pandas as pd

# Step 1: Read the dataset
df = pd.read_csv('deliveries.csv')
print(df.info())

pff=df.groupby(['batting_team','batsman'])['batsman_runs'].sum().unstack().to_json('IPL_json')
print(pff)



