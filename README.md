#Note: I didn't get the cvs, after I activated the virtual environment I wrote all this code in the command prompt 
to do this just write. You can also use Notepad++ but writing in CMD extracted something from the website.

python

after activating virtual environment.

# scraping
# 1) go to your cmd, and type in:
easy_install pip  
pip install BeautifulSoup4

# Be sure to activate virtual environment.

2.) In notepad++ (python) write the code below:

# import libraries
import urllib2  # (start here)

from bs4 import BeautifulSoup

quote_page = 'https://www.amazon.com/Jimmy-Paddox-Leather-Black-Biker/dp/B0771TB2Y1/ref=sr_1_9?s=apparel&ie=UTF8&qid=1511230028&sr=1-9&nodeID=7141123011&psd=1'

page = urllib2.urlopen(quote_page)

soup = BeautifulSoup(page, 'html.parser')

title_box = soup.find('h1', attrs={'id': 'title'}) 

title = title_box.text.strip()

print title

priceblock_ourprice_box = soup.find('span', attrs={'id':'priceblock_ourprice'})

priceblock_ourprice = priceblock_ourprice_box.text

print priceblock_ourprice


