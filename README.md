#ÖRNEK BOYUNCA OLUŞAN VARİABLES
# Data-Capstone-Project-with-Python-<img width="915" alt="Ekran Resmi 2022-04-09 14 51 08" src="https://user-images.githubusercontent.com/96236352/162572926-df0b9655-9a33-441d-9920-e9d59a92186a.png">

#ÖRNEK BOYUNCA KULLANILAN BAZI GRAFİKLER

#sns.countplot(x='Reason',data=df)
<img width="414" alt="Ekran Resmi 2022-04-09 14 54 26" src="https://user-images.githubusercontent.com/96236352/162573024-727ca412-b5f3-4065-aae5-083349392e07.png">




#sns.countplot(x='Day of Week',data=df,hue='Reason')
#plt.legend(bbox_to_anchor=(1.05, 1), loc=2, borderaxespad=0.)
<img width="503" alt="Ekran Resmi 2022-04-09 14 55 15" src="https://user-images.githubusercontent.com/96236352/162573059-9e98d53d-34bd-45f2-9613-2a4a9513824e.png">




#byMonth['lat'].plot()
<img width="434" alt="Ekran Resmi 2022-04-09 14 56 06" src="https://user-images.githubusercontent.com/96236352/162573099-8569996d-e8b6-4e8f-aab9-33f611e034d3.png">




#byMonth = byMonth.reset_index()
#byMonth.head()
#sns.lmplot(x='Month',y='twp',data=byMonth) 
<img width="364" alt="Ekran Resmi 2022-04-09 14 56 28" src="https://user-images.githubusercontent.com/96236352/162573114-4056bdea-27eb-4c2e-a1d5-1dac88cdf3df.png">




#byDate['lat'].plot()
<img width="406" alt="Ekran Resmi 2022-04-09 14 56 43" src="https://user-images.githubusercontent.com/96236352/162573128-f031b32f-c03b-4445-8ce9-a69d19988574.png">




df[df['Reason']== 'Traffic'].groupby('Date').count()['lat'].plot()
<img width="388" alt="Ekran Resmi 2022-04-09 14 57 03" src="https://user-images.githubusercontent.com/96236352/162573144-9d309c4d-fcbd-4df0-a290-a3e8d6bf574e.png">




#fig,ax = plt.subplots(figsize=(15,10))
#sns.heatmap(dayHour,cmap='viridis',ax=ax)
<img width="608" alt="Ekran Resmi 2022-04-09 14 57 32" src="https://user-images.githubusercontent.com/96236352/162573164-846bd218-9bf6-4504-bb36-0c6d63344707.png">




#sns.clustermap(data=dayHour,cmap='viridis')
<img width="609" alt="Ekran Resmi 2022-04-09 14 57 54" src="https://user-images.githubusercontent.com/96236352/162573183-c894f32e-d399-472f-8ad1-1fd4033a6ebd.png">




#figsize,ax = plt.subplots(figsize=(10,8)) 
#sns.heatmap(data=dayMonth,cmap='viridis',ax=ax)
<img width="584" alt="Ekran Resmi 2022-04-09 14 59 45" src="https://user-images.githubusercontent.com/96236352/162573259-d287f683-ff06-4765-8b4e-61b795e2e848.png">




