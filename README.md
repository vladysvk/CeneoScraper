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
|opinion|opinion|div.js_product-review:not(.user-post--highlight)|
|opinion ID|opinion_id|["data-entry-id"]| 
|opinion’s author|author|span.user-post__author-name| 
|author’s recommendation|recommend|span.user-post__author-recomendation > em| 
|score expressed in number of stars|stars|span.user-post__score-count| 
|opinion’s content|content|div.user-post__text| 
|list of product advantages|pros|div.review-feature__item.review-feature__item--positive| 
|list of product disadvantages|cons|div.review-feature__item.review-feature__item--negative| 
|how many users think that opinion was helpful|up_votes|button.vote-yes["data-total-vote"]| 
|how many users think that opinion was unhelpful|down_votes|button.vote-no["data-total-vote"]| 
|publishing date|published|span.user-post__published > time:nth-child(1)["datetime"]| 
|purchase date|purchased|span.user-post__published > span > time:nth-child(2)["datetime"]| 