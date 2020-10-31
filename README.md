# hacktob3
nabs
import csv
import heapq
import math
import operator
import random
import pandas as pd
from scipy.spatial import distance
import numpy as np
import matplotlib.pyplot as plt
from csv import reader
from unicodedata import name
print("Enter the value of k")
k=int(input())
data = pd.read_excel('C:\\Users\\92303\\Desktop\\Semester 7\\Data.xlsx')
data = data.drop(columns =['Observation'])
datanp= data.to_numpy()
length = len(datanp)
dictionary={}
list1=[]
list2=[]
sList=[]
ssList=[]
disList=[]
sDic={}
train_len= math.ceil(0.7*length)
test_len=length-(math.floor(0.3*length))
for i in range((length-1),test_len,-1):
    for j in range(0,train_len,+1):
        d = int(distance.euclidean(datanp[i],datanp[j]))
        
        #dictionary.setdefault(d,[]).append(datanp[j])
        #dictionary.setdefault(datanp[i],[]).append(d)

        #sDic.append(datanp[j])
        #disList.append(d)
        #disList.append(datanp[i])
        #disList.append(datanp[j])
       # np.append(disList,(d,datanp[i],datanp[j]))
        #np.append(datanp,d)
        #np.append(datanp,(datanp[i],datanp[j]))
        list1.append(d)
        
        sList=np.sort(list1)
        dictionary.setdefault(i,[]).append(d)
        dictionary.setdefault(i,[]).append(datanp[j])  
    #sorted(disList,key = lambda x: x[0])
    #dictionary.setdefault(i,[]).append(datanp[i]) 
    #ssList=np.argsort(sList)[:k]
    #dictionary.setdefault(i,[]).append(sList[ssList])
    list1=[]
    sList=[]
    ssList=[]
    sDic=sorted(dictionary.items(), key=lambda x: x[0])
#print(dictionary)
print(sDic)
#print(datanp)

    

