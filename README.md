# SuggestPrediction

Current repository consist of 2 main files:<br>
1. <b>StatisticAlgorithm</b> <br>
2. <b>CategoryPrediction</b> <br>
Moreover, there are two main <b>.csv</b> files, which are the examples of data:
1. <b>category_data.csv</b> (for category prediction) <br>
2. <b>suggest_data.csv</b> (for statistic prediction) <br>

## StatisticAlgorithm

This algorithm use statistic data for prediction. The principle is next:
1. We send get request to old version of suggest for recieving the suggest based on text score of <b>Elasticsearch</b> <br>
2. We use every suggest, which we recieved earlier, for finding the most relevant goods, using the statistic <br>
3. We recieve the TOP-n goods and return the TOP-n SKU of goods <br>

## CategoryPrediction

This algorithm has two part: prediction of category and prediction of TOP-n goods in predicted category. 
