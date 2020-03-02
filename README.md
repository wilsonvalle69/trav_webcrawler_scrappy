https://scrapy.org/    <br>
https://blog.scrapinghub.com/   <br>

python3 -m venv venv    # create environment  <br>
source  venv/bin/activate     # activate environment    <br>
    # deactivate environment  <br>

pip install scrapy  <ber>
scrapy startproject postscrape         # name of the project   <br>
cd postscrape  <br>
inside the postscrape/postscrape/spider folder create a file where we are going to work on post_spider.py <br>

To execute the code <br>
scrapy crawl posts    # post is from the name variable inside the class     <br>



On shell    <br>
scrapy shell htts://blog.scrapinghub.com    <br>
response.css('title')   <br>
response.css('title').get() <br>
response.css('title::text').get()   <br>
response.css('h3::text').get()  <br>
response.css('h3::text')[2].get()   # get all   <br>
response.css('h3::text').getall()   <br>
response.css('.post-header').get()    # get by class name the first one <br>
response.css('.post-header a::text').get()    # get by class name the first link    <br>
response.css('.post-header a::text')[1].get()    # get by class name the second link    <br>
response.css('p::text').re(r'scraping')    # regular expressions    <br>
response.css('p::text').re(r's\w+')     # regular expression everything that starts with s  <br>
response.css('p::text').re(r'(\w+) you (\w+)') # regular expression phrases with 'you in the middle     <br>
response.xpath('//h3')      # using xpath sentences <br>
response.xpath('//h3/text()').extract() # equal to getall() <br>
response.xpath('//h3/text()').getall()  <br>
post = response.css('div.post-item')[0]     # putting data into a variable  <br>
title = post.css('.post-header h2 a::text')[0].get()    # reuse previous variable to get each individual value - get title  <br>
date = post.css('.post-header a::text')[1].get()        # get date  <br>
author = post.css('.post-header a::text')[2].get()      # get author    <br>
for post in response.css('div.post-item'):      <br>
    title = post.css('.post-header h2 a::text')[0].get()        <br>
    date = post.css('.post-header a::text')[1].get()        <br>
    author = post.css('.post-header a::text')[2].get()      <br>
    print(dict(title=title, date=date, author=author))      <br>

quit()      # exit shell        <br><br>

Command to execute applycation and send it to a file    <br>
scrapy crawl posts -o posts.json     <br>



