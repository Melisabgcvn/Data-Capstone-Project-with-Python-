import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df=pd.read_csv("911.csv")
#dosya df isimli bir dataframe nesnesine dönüşür.
#911.csv dosyasını internetten çekiyoruz.Python dosyamızla aynı klasörün içinde olmalı.
print(df.head())
#head ile ilk 5 satırı görücez.


print(df["zip"].value_counts().head())
#zip sütunundaki eşsiz 5 veriyi ve ne kadar tekrar edildiğini gösterir.

#print(df["zip"])
#zip sütununu yazdırarak daha net görebiliriz.

print(df["twp"].value_counts().head(5))
#twp deki eşsiz olan verilerden 5 tanesini gösterir.
#print(df["twp"]) denerek gözlemlenebilir.

print(len(df["title"].unique()))
#kaç tane eşsiz title var onun sayısını verir.
print(df["title"].nunique()) #denirsede aynı şekilde eşsiz title sayısını gösterir.
   
    
df["Reason"]=df["title"].apply(lambda x : x[:x.find(":")])
#lambda x : (yapılacak işlem)
print(df.head())


print(df["Reason"].value_counts().head())
#Reason'daki eşsiz kelimlerin kaç kere kullanıldığını yazar.

sns.countplot(x="Reason",data=df)

sns.countplot(x="Reason",data=df,palette="viridis")
#renk değişir.

print(df["timeStamp"].iloc[0])
#iloc ile istediğimiz index'teki veriye ulaşabiliriz.
print(type(df["timeStamp"].iloc[0]))
#denirse timeStamp adlı sütunun 0.indeksindeki değerin tipini öğreniriz.

df["timeStamp"]=pd.to_datetime(df["timeStamp"])
print(type(df["timeStamp"].iloc[0]))

#artık str olan veri tipmiz bir pandas tarih nesnesine dönüştü.
time=df["timeStamp"].iloc[0]
#timeStamp sütununun ilk elemanını time denilen bir değişkene atadık.
print(time.hour)
print(time.year)
print(time.minute)
#time değişkenin saati yılı ve dakikası gibi bilgileri aldık.

df["hour"]=df["timeStamp"].apply(lambda time: time.hour)
#df'e hour adında timeSpan sütununu kullanarak yeni bir sütun daha ekledik.
print(df["hour"])

df["Day of Week"]=df["timeStamp"].apply(lambda x: x.dayofweek)
dmap={0:'Mon',1:'Tue',2:'Wed',3:'Thu',4:'Fri',5:'Sat',6:'Sun'}
df["Day of Week"]=df["Day of Week"].map(dmap)


sns.countplot(x="Day of Week",data=df)
#tek bir değişkene göre grafiği gösterir.
sns.countplot(x="Day of Week",data=df,hue="Reason")
#günlere göre "reason" oranlarını verir.İki değişken var.

sns.countplot(x="Day of Week",data=df,hue="Reason",palette="viridis")
plt.legend(bbox_to_anchor=(1.05, 1), loc=2, borderaxespad=0.)
#reason kutucuğumuzun yerini ve boyutunu ayarladık.


sns.countplot(x='hour',data=df,hue='Reason')
plt.legend(bbox_to_anchor=(1.05, 1), loc=2, borderaxespad=0.)
byhour = df.groupby('hour').count()
#hour kolonuna göre sıralayıp toplamlarını alır.Yani hour'a göre hazırlanmış yeni bir dataframe oluştu.
print(byhour.head())
#yeni dataframe in ilk 5 satırını gösteriri.

byhour["lat"].plot()
#byjour dataframe indeki lat sütununun plot'u çizilir.

byhour=byhour.reset_index()
#reset_index() anlamsız değerleri veya düzgün olmayan şeyleri düzelterek tekrar oluşturur.
print(byhour.head())
sns.lmplot(x="hour", y="twp", data=byhour)


df['Date'] = df['timeStamp'].dt.date
#timeStamp kolonunu kullanar
byDate = df.groupby('Date').count()
#Date kolonuna göre sıralayıp toplamlarını alır.
byDate['lat'].plot()
#yeni dataframe'in lat sütunun grafiği

df[df['Reason']== 'Traffic'].groupby('Date').count()['lat'].plot()
#df deki Reason kolonunun Traffic olan verilerini kullanır (koşul sunar) ve bunları date'e göre gruplar ve lat sütununu hesaplayıp grafiğini çizer.
plt.tight_layout()
#subplot'lar otomatik olarak sığsın diye kullanılır.

df.groupby(by=["Day of Week","hour"]).count()["Reason"]
#2 değişkene göre Reason kolonun toplam değerlerini gösterir.

df.groupby(by=["Day of Week","hour"]).count()["Reason"].unstack()
#matris halinde gösterir.

dayhour=df.groupby(by=["Day of Week","hour"]).count()["Reason"].unstack()
#yukarıdaki tabloyu bir dataframe e atadık.

sns.heatmap(dayhour)
#ısı haritası çizilicek.

sns.heatmap(dayhour,cmap="viridis")
#renk değşir
plt.figure(figsize=(12,6)) #grafikteki kutucuk boyutunu değiştirdik.
sns.heatmap(dayhour,cmap="viridis")

sns.clustermap(dayhour,cmap="viridis")
#Hiyerarşik olarak kümelenmiş bir ısı haritası olarak bir matris veri kümesi çizer.
