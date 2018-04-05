# WebScrapingeBayUsingBeautifulSoup
Python code to Web scrape eBay page(Using page link) and analyze the data by drawing a Bar Graph and wordcloud based on the frequency of the words in product name.
Retrives Product Name, Product State (Brand New , Used, etc) and product price of the products in the provided page link. (Change the link according to the requirement) and writes into a csv file.
I have followed https://www.youtube.com/watch?v=XQgXKtPSzUI&t=2s video to get scrape data.
Used panda library to create a Bar graph and word cloud to craete a wordCloud of frequenty used words.

How to execute code?
Open the jupyter notebook using Anaconda and run each cell of the file.

#create dictionary 
productCount = Counter(new_product)

#remove objects from dictionary count less than 2
for k in list(productCount):
    if productCount[k] < 3:
        del productCount[k]

#use pandas library to create bar graph
df = pandas.DataFrame.from_dict(productCount, orient='index')
df.plot(kind = 'bar', color = 'byrgkc')
plt.title("Product Name Word frequency")
plt.xlabel("Product Words")
plt.ylabel("Number of times product name repeats")
plt.show()

#Create Word cloud
wc = WordCloud(scale = 4)
wc.generate(str(new_product))
plt.imshow(wc)
plt.axis('off')
plt.show()


