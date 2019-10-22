---
layout: post
title: 'Get Content Hidden Element Using Selenium'
subtitle: ''
date: 2019-09-27
categories: Scrape
tags: Scrape Selenium
---
### Motivation
Sometimes when we do web scraping, we find some contents are hidden which will be shown by click a button or title etc..

In these cases, we have to use `selenium` to click the button to show the hidden texts. In some cases, however, we can use elements' `textContent`, `innerText`, or `innerHTML` to get those contexts easily.

- `innerHTML` will return the inner HTML of this element, which contains **all HTML tags** inside.

- `textContent` and `innerText` will only retrieve all text content of its descendants without any HTML tags.
    - `textContent` is a W3C-compliant textContent property, but not supported by IE.
    - `innerText` is not part of the W3C DOM specification and not supported by Firefox.

### Sample Codes
This little sample is part of my scraping project.
I come across Data Science interview questions post online. But all its questions are hidden, you have to click the question's title to show the contents one by one.

I use `xpath` and `textContent` of `selenium` to get all hidden contents very easily and dump to json file.

``` python
def parse_ds101(urls):
    res = {}
    for i in range(len(urls)):
        options = webdriver.ChromeOptions()
        options.add_argument('--ignore-certificate-errors')
        options.add_argument('--ignore-ssl-errors')
        options.add_argument('--headless')
        driver = webdriver.Chrome(options=options)
        driver.get(urls[i])
        titles = driver.find_elements_by_xpath('//h3')
        for i in range(len(titles)):
            title = titles[i].text
            pk = int(title.split(".")[0])
            id = "h5p-panel-content-0-" + str(i)
            txt = driver.find_element_by_id(id)
            txt = txt.get_attribute("textContent")
            res[pk] = {title:txt}
    return res
```