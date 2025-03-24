# CeneoScraper

"https://www.ceneo.pl/167976636;02514"

## Algorithm for extracting opinions about single product from Ceneo.pl
1. Send the request for accessing first webpage with opinions about product
2. If response is OK, parse HTML page content into DOM structure
3. Extract opinions and their components from DOM structure
4. Save opinions with their components to complex data structure
5. If there are more pages with opinions, repeat steps 1-5
6. Save data structures with opinions into database

## Structure of single opinion in Ceneo.pl
|Component|Variable|Selector|
|---------|--------|--------|
|opinion|opinion|div.js_product-review|
|opinion ID|opinion_id|[data-entry-id]| 
|opinion’s author|author|span.user-post__author-name| 
|author’s recommendation|recommend|span.user-post__author-recomendation| 
|score expressed in number of stars|stars|| 
|opinion’s content|content|div.user-post__text| 
|list of product advantages|pros|| 
|list of product disadvantages|cons|| 
|how many users think that opinion was helpful|up_votes|| 
|how many users think that opinion was unhelpful|down_votes|| 
|publishing date|published|| 
|purchase date|purchased|| 