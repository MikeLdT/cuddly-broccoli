# cuddly-broccoli

## Team members

| Name  | Email | Clave única | Github handler
| :-------------: | :-------------: | :-------------: | :-------------:
| Fabián Orduña Ferreira  | fabian.orduna@itam.mx  | 159001  | FabianOrduna 
| Nelson Gil Vargas  | ngilvarg@itam.mx  | 203058  | nelsonalejandrov
| Jorge Garcia  | jgarc401@itam.mx  | 202945  | jgarciad
| Miguel Lerdo de Tejada  | miguel.lerdodetejada@itam.mx  | 168450  | MikeLdT


### Hi there 👋

Why are we awesome?

-	🔭 Because Nelson is a geophysicist (no, earthquakes can’t be predicted), leftie and gamer.
-	📫 Because Miguel is an economist/actuarial scientist and will judge you based on your p-values. 
-	⚡ Because Jorge enjoys writting code and thinks that the cloud rocks. 
- 🖥️ Because Fabian is a software engineer with experience in web development, distributed systems and can hack your phone if he wants.

Together we can learn about each other, and we can solve many kinds of problems merging our skills as one brain to conquer Data Product Architecture.

# Project Proposal 

### 1. Objectives

1. What is the problem that your Data Product will solve? 

According to [topendsports](https://www.topendsports.com/world/lists/popular-sport/fans.htm) football is the most popular sport globally approximately 3.5 billion fans followed by cricket with 2.5 billion fans. Many of these fans like to be aware of the odds for future games of their teams, specially with upcoming fooball classics like FC Barcelona vs Real Madrid, Manchester United vs Liverpool or America vs Chivas in the mexican league. Another proportion of these followers are looking for betting tips. This data product intends to predict football match results (win, loss or tie), this prediction could be used for informative means or as betting tips. 

2. If a company was to use this application, what would be their ML objectives and business objectives? 

The ML objectives is to reduce the false positive rate over the output predictions. 

The company's business objectives would be to provide an additional set of tools to help gamblers in decision making process. 

### 2. Users

1. Who will be the users of your application?

Football fans looking for predictions about football game results. 

2. How are users going to interact with your application? 

Match results will be displayed in tables containing the opponents in the game and the probability of a win, loss or tie. We will display some comboboxes with basic parameters like league, team, date, etc and then it will provide the user with win, draw or lose probabilities for the next match. Also, it will also display recent statistics of both the home and away teams (since football is usually about streaks). The idea is to provide to the client with the best tools to bet. 


### 3. Data Product Architecture Diagram

### 4. Data

1. Where would you get your data from? How much data would you need? Is there anything publicily available or do you need to build your own dataset? 

The data for our project will be extracted from the [API-FOOTBALL](https://www.api-football.com/documentation-v3), a free API containing Timezones, Countries, Leagues, Teams, Venues, Standings, Fixtures, Injuries, Predictions, Coachs, Players, Transfers, Trophies, Sidelined and Odds. 

### 5. Modeling

**User interface**: Our interface will be user-friendly. we will display some comboboxes with basic parameters like league, team, date, etc and then it will provide the user with win, draw or lose probabilities for the next match. Also, it will also display recent statistics of both the home and away teams (since football is usually about streaks). The idea is to provide to the client with the best tools to bet. 

**Model**:. The initial idea of the model is to adjust a neural network, logistic regression and any other algorithms to get the best prediction based on several variables available (recent matches, venue, expected goals, etc). We would re-train the model each transfer window and replace the old model. 

[JORGE LA VERDAD A ESTO NO LE ENTENDI] We will display main statistics of the teams. This statistics will be saved, the idea is conserving the statistics of the last month into a data table in order to show repeat information for a different client user, that means, same match prediction result will display same statistics. To obtain new statistics that we do not consult previously we will request from the API the necessary information about it. 

**Software**: Python to train the models and PHP to display the front-end application. Postgres to data base management. The idea is use Postgres to conserve results of the prediction model to compare and implement improvements over the last production model. On the other hand, with Postgres we storage the data to train a model and the statistic of the requested matches. 

**Scope**: Premier League matches. 


### 6. Evaluation

1. How would you evaluate your model performance, both during training and
inference?

We would evaluate if the percentage of false positives is strictly smaller than a threshold defined by the client. In this case, we understand a false positive as a situation where the model predicts a team will win a match when in reality the opposite happens. We believe false positives are what the client is ultimately interested in minimizing, whereas alternative measures like accuracy might be misleading.


2. How would you evaluate whether your application satisfies its objectives?

We would compare our performance against that of profesional betting houses. From the Football API we can retrieve betting odds from several webpages. If we can manage to get data of the results of professional gamblers, we might compare against them as well.

### 7. Inference

1. Will you be doing online prediction or batch prediction or a combination of both?

We intend to do batch prediction, however we might do online prediction if we can manage to.

2. Will the inference run on-device or through a server?

On-device 

3. Can you run inference on CPUs or an edge device or do you need GPUs?

We will only need CPUs.

### 8. Compute

1. How much compute do you need to develop this application as a market-ready
product?

In order to develop this application we require to use different tools. On this case we are using a Compute Engine for AI so we could have a space with pre installed libraries and ready to use for this purpose. We also need Cloud Storage service for the data retrieved from the API so we could be able to store the information. The use of databases is required so we could retrieve information and query information from there in the future. For the machine learning model we could use the Auto ML Google Service but also a script to perform this. We need to use an orchestrator and a hosting space to place a dashboard to be used by the customer.

    1. To train your model (if you train your own model): do you need GPUs/TPUs or just CPUs? How many machines? For how long?

Since the amount of data for this project is not that much we could perform all the operations with only CPUs in a single machine and for training the models we estimate the time needed is gonna be at most 24 hours but that depends, at the end, in the amount of algorithms we compare and the different configurations. 

    2. To serve your model: can your models make predictions on CPUs?

At the end, when models are ready and based on the amount of data the predictions can be done with CPUs.

2. How much compute do you need to develop this application for this project?

As mentioned above we need different tools from GCP and apart from that clarify that use of single CPU with an Intel processor is enough.

### 9. MVP

As an MVP we want to have all the pipeline since the API data retrieval, the model and a dashboard to the end user to make predictions in an easy and quick way

### 10. Pre-mortems
Todos lluvia de ideas
