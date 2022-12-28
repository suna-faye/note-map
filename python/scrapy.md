## env install
### debian
1. install python3
   `sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev`
2. install python venv
   `sudo apt-get install python3-venv`
3. create virtual python env
   `python3 -m venv scrapy-env`
4. use virtual env
   `source ./scrapy-env/bin/activate`
5. deactivate virtual env
   `deactivate`
6. install python scarpy
   `python -m pip install scrapy`
7. create project
   `scrapy startproject tutorial`
8. create "quotes_spider.py"
```python
import scrapy

class QuotesSpider(scrapy.Spider):
    name = "quotes"

    def start_requests(self):
        urls = [
            'https://quotes.toscrape.com/page/1/',
            'https://quotes.toscrape.com/page/2/',
        ]
        for url in urls:
            yield scrapy.Request(url=url, callback=self.parse)

    def parse(self, response):
        page = response.url.split("/")[-2]
        filename = f'quotes-{page}.html'
        with open(filename, 'wb') as f:
            f.write(response.body)
        self.log(f'Saved file {filename}')   
```
8. run spider
```sh
   # at tutorial
   pwd
   # like this => .../tutorial
   scrapy crawl quotes
```
9. use shell to extracting data
   `scrapy shell 'https://quotes.toscrape.com/page/1/'`
10. filter response by css
    `response.css('title')`
11. extract text from filter result
    `response.css('title::text').getall()`
12. use xpath
    `response.xpath('//title/text()').get()`
