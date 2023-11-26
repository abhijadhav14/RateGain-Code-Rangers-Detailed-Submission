# Rate Gain Challenge ( Web-Scrapping )

In this repository I have solved a challenge given by rate gain company on unstop platform .

The challenge was to web-scrap few details from all the 45 pages of https://rategain.com/blog/ website .

I had to extract the following :

1. Blog Title
2. Blog Date
3. Blog Image URL
4. Blog Likes Count

## Solution :

I used python and selenium tool to solve the given problem , here are the steps I followed :

1. I observed that each blog was contained in a div named "wrap" and in this wrap div contained all the details of each of all blogs

<img width="1440" alt="image" src="https://github.com/anandsagar00/Covid-19-Vaccination-Analysis/assets/80447047/8f1c1061-c24b-4dd1-8034-fc61734f927c">

2. The wrap div contained div named "img" from which I extracted the background image url which was contained in the anchor tag as one of it's property .
   some of the blogs didn't contain image , so in that case we had to explicitly check if image URL was there or not in the code .

3. The blog title was in the h6 heading which I extracted easily using the selenium tool.
4. Next , I had to extract the Blog date and Blog Like Count , so I observed carefully and saw that these data were contained in the span tag
   and on the 1st span there was data about Blog Date and on the 4th span there was data about Blog like count .

## Problem with CSV :

- The challenge was to store these value in a file , first I chose CSV file format but it caused error as there were blogs in which the title contained comma and all of the dates on the blogs contained comma values which created extra columns in CSV file format , so finally I stored the extracted data in excel file format , for which I used **openpyxl** library
