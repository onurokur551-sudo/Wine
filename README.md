import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("WineQT.csv")




while True:
    df = pd.read_csv("WineQT.csv")
    print("YAPMAK ISTEDIGINIZ ISLEMI SECINIZ!")

    print("1-Temel Istatistik Cikarma")
    print("2-Kalite Dagilimi")
    print("3-pH Degeri")
    print("4-Korelasyon Matrisi")

    secim = input("Lutfen bir islem seciniz:")
    if secim == '1':
        print(df.describe())

    if secim == '2':
        plt.scatter(df['quality'], df['alcohol'])
        plt.grid(True, linestyle='--', alpha=0.6)
        plt.title('Quality Graphics')
        plt.xlabel('Quality')
        plt.ylabel('Alcohol')
        plt.show()


    if secim == '3':
        plt.hist(df['pH'], bins=20, color='skyblue', edgecolor='black')
        plt.grid(True, linestyle='--', alpha=0.6)
        plt.title('Ph Graphics')
        plt.xlabel('Ph')
        plt.ylabel('Wine Count')
        plt.show()

    if secim == '4':
        korelasyon_matrisi = df.corr()
        plt.figure(figsize=(10, 8))
        sns.heatmap(korelasyon_matrisi, annot=True, cmap="coolwarm", fmt=".2f", linewidths=.5)
        plt.title('Korelasyon Matrisi')
        plt.show()

    if secim == '99':
        print(df.columns)
