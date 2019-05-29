# SuggestPrediction

Current repository consist of 2 main files:<br>
1. <b> [StatisticAlgorithm](https://github.com/maikReal/SuggestPrediction/blob/master/StatisticAlgorithm.ipynb) </b> <br>
2. <b> [Category-Suggestion Algorithm](https://github.com/maikReal/SuggestPrediction/blob/master/Category-SuggestionAlgorithm.ipynb) </b> <br>
3. <b> [SuggestPredictionVersion2](https://github.com/maikReal/SuggestPrediction/blob/master/SuggestPredictionVersion2.ipynb) </b> <br>
Moreover, there are two main <b>.csv</b> files, which are the examples of data:
1. <b>[category_data.csv](https://github.com/maikReal/SuggestPrediction/blob/master/caregory_data.csv)</b> (for category prediction) <br>
2. <b>[suggest_data.csv](https://github.com/maikReal/SuggestPrediction/blob/master/suggest_data.csv)</b> (for statistic prediction) <br>

## Statistic Algorithm

This algorithm use statistic data for prediction. The principle of work is next:
1. We send get request to old version of suggest for recieving the suggest based on text score of <b>Elasticsearch</b> <br>
2. We use every suggest, which we recieved earlier, for finding the most relevant goods, using the statistic <br>
3. We recieve the TOP-n goods and return the TOP-n SKU of goods <br>

## Category-Suggestion Algorithm

This algorithm has two part: prediction of category and prediction of TOP-n SKU of goods in predicted category. The main plot of algorithm is next: <br>
1. We use `category_data.csv` for predicting the category of new good (one of 49 unique category) <br>
2. Ranking goods in predicted category <br>
3. Recieve TOP-n SKU of goods in predicted category

## SuggestPredictionVersion2 Algorithm

This algorithm has many advantages over algorithms described above. His main feature is context searching. It means, that he can look for different queries by his prefix. So, the algorithm principle of work is next: <br>
1. We get every, for example, 3 letter of user query (it's our query) <br>
2. We find different queries with using context searching. For example: <br>
```
Prefix - шок
Variants:
шоколадный заяц
кубик шоколадный
торт в шоколадной глазури
```
3. Try to find all correct variants for user prefix <br>
4. Return all variants for user query <br>
