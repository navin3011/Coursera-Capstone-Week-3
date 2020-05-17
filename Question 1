#This file contains first question of Capstone Week-3
! pip install beautifulsoup4
! pip install --upgrade lxml
from lxml.html import fromstring
import pandas as pd 
import requests 
#import Numpy as np
from bs4 import BeautifulSoup
req = requests.get("https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M") 
soup = BeautifulSoup(req.content,'lxml') 
table = soup.find_all('table')[0] 
df = pd.read_html(str(table))
nh=pd.DataFrame(df[0])
df2 = nh[nh['Borough'] == "Not assigned"].index
nh.drop(df2, axis=0, inplace=True)
nh.reset_index(drop=True, inplace=True)
nh.columns = ['Postcode','Borough', 'Neighbourhood']
cols = nh.columns.tolist()
cols
nh= nh[cols]
nh.shape
nh
