# Movies System Recommender - Fajar Zulkautsari Muhammad

## Project Overview

The film business has expanded significantly in recent years[[1]](https://journal.untar.ac.id/index.php/koneksi/article/view/21509). Technological developments and modifications in how individuals receive entertainment are the main drivers of this. Users now have access to hundreds of movies and TV series that can be streamed whenever and wherever they choose thanks to the growth of streaming services like Netflix, Amazon Prime Video, Hulu, Disney+, and many others. The development of internet technology has enabled smooth and high-quality streaming. Additionally, consumers have a variety of entertainment alternatives because to the diversity of movie content provided by these platforms, which ranges from the newest Hollywood blockbusters to independent and documentary projects.

The landscape of entertainment content consumption has been drastically altered by the film industry's explosive rise. Each year, thousands or even hundreds of movies are released. Users are faced with an ever-increasing number of choices. In this situation, a movie genre recommendation system becomes essential. The growing film industry also brings about greater genre diversification, including more niche and experimental genres. Therefore, the recommendation system must be able to accommodate a variety of user preferences and identify movies that fit into genres that may be less popular. Personalization is also key in meeting the increasingly diverse needs of users[[2]](https://www.inderscienceonline.com/doi/abs/10.1504/IJHPCN.2017.083199). In the fierce competition between streaming platforms and other online entertainment services, an effective recommendation system can be a differentiating factor, helping users find the content they love. Furthermore, the recommendation system can be used to improve the accuracy and relevance of movie genre recommendations, providing a better experience for users in navigating the wealth of movies that are available today.

In this context, movie recommendation systems based on genre play an increasingly important role. The ability of streaming platforms to recommend movies that match user preferences has become one of the key factors in retaining customers and attracting new customers[[3]](https://www.mdpi.com/2227-7390/11/4/895). Personalization of the user experience based on viewing history and viewing patterns has been a major focus for increasing customer retention. With movie genre data and intelligent comparison algorithms, these systems can help users navigate through the various movie choices available and increase their satisfaction in finding entertainment content that suits their tastes. With the rapid growth of digital content and the influence of social media in sharing recommendations, movie genre-based recommendation systems are becoming one of the important aspects of the rapidly growing film industry. In other words, the recommendation system can be beneficial to both parties, to the user and the provider platform. Users will get satisfaction in watching movies that will lead to profit for the provider platform[[4]](https://ddd.uab.cat/record/232276).

## Business Understanding
### Problem Statements
In the context of building a movie recommendation system, the project aims to address the following challenges:
- How to improve user satisfaction in streaming platforms?
- How to provide movie recommendations that are in line with user preferences with a high level of precision?

The main focus of this project is to generate precise and relevant movie recommendations based on the user's genre preferences.

### Goals
The main objectives of this project are:
- To improve the user experience in finding new movies that match their preferences.
- To develop a movie recommendation system that can provide movie recommendations that match user preferences with a high level of precision.

In the context of building a movie recommendation system, the main objective is to provide precise and relevant recommendations to users based on their preferences. Precision measures the extent to which the recommended movies are actually relevant and in line with the user's preferences.

### Solution Statements:
This project will employ a Machine Learning strategy along with the Content-Based Filtering technique to address the issues and accomplish the stated goals. Content-Based Filtering will make use of previously loved content as a benchmark. The recommendation algorithm will provide consumers highly accurate material (in this case, movies) based on the user's viewing history or content they have previously liked. In this assignment, the movie's genre will be used to determine how comparable the two are. This means that the system will suggest further films that fall into a similar or even identical genre to the one that the user has chosen to enjoy. With this strategy, it is anticipated that users will get recommendations for movies with genres that match their preferences, even movies that they may not have known about before.

Proper movie genre recommendations will help users in the following ways:
- Users are more likely to enjoy movies that are to their liking, thus increasing their satisfaction.
- Users will be more involved in streaming platforms because they get relevant and interesting recommendations.
- Users will find new movies that match their favorite genres, develop their viewing preferences, and make the viewing experience more diverse.

With this approach, it can be understood that a proper movie genre recommendation system will have a positive impact on user satisfaction and engagement in streaming platforms.

## Data Understanding
The dataset used is the Movie System Recommender Datasat dataset obtained from the Kaggle website. The dataset is divided into two files, namely:
- [movies.csv](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset?select=movies.csv)  contains information about movies, including movieId, title, and genres.
- [ratings.csv](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset?select=ratings.csv) contains information about ratings given by users to movies, including userId, movieId, rating, and timestamp.

## Data Preparation
A content-based recommendation system project's data preparation procedure entails cleaning up and processing the data so that the recommendation system may use it. These procedures include gathering, scrubbing, analyzing, and structuring the data in order to make precise suggestions. The primary steps in the data preparation process are as follows:

- **Gathering data:**

The information needed for the movie genre recommendation system was obtained early in the project. On the Kaggle website, you may find a variety of datasets that can be used to assess this data. The initial step in this process is to upload the Kaggle API token, which will be used as an authentication key to access Kaggle's data. After successfully uploading the API key, the relevant data is downloaded from Kaggle directly to the project environment utilizing the Kaggle datasets download mechanism. This approach assures the quality and accuracy of the data used in the building of a movie recommendation system based on movie genres since the data used in this project is continually updated in line with its source.

- **Data cleaning:**

After exploration, there are several data that need to be cleaned, namely:
- Duplicate data in the title column. The five data have the same title as other data, but their movieId and genres are different. Cleaning was done by deleting the duplicate data so that it remained 9737 data.
- Data that does not have a genre. There are 34 films that do not have genre information that can be used for recommendation analysis. The 34 films were excluded from the project, so the total number of films that could be used was 9703 films. The decision was made to make the analysis and recommendation of film genres more accurate and relevant, as genre is one of the important aspects in determining user preferences. Although these 34 films are not included in the analysis, the 9703 films available still reflect the diversity and complexity of the rapidly growing film industry today, and the film genre recommendation system will focus on providing recommendations that are appropriate based on well-defined genres.

- **Feature Extraction:**

In the feature extraction stage, the genre fields in the dataset are converted into numerical representations that can be used in further analysis. One of the approaches used in this project is the one-hot encoding technique. In this context, each genre present in the genre column is translated into separate binary columns. Each of these columns describes one specific genre, and if the movie has that genre, the value in that column will be 1, while otherwise it will be 0. For example, one-hot encoding will transform the table as follows:

| ...  | genres  |                  
|---|---|
|   |  Comedy, Romance   |
|   |  Comedy, Drama, Romance  |
|   |   |

Into a table as below :

| ...  | Comedy  | Romance  | Drama  |
|---|---|---|---|
|   | 1  | 1  | 0  |
|   | 1  | 1  | 1  |

The result of this feature extraction is the transformation of the dataset into a binary representation that allows the algorithm to understand and process genres as features that can be used in similarity calculation and movie recommendation. This is an important step in preparing the data before applying various content-based recommendation methods.

- **Data Transformation:**

In the context of understanding the level of correlation or similarity between movies based on genre, a pivot table has been created using the previously calculated Cosine Similarity metric. This pivot table acts as a very useful visual tool to illustrate the extent to which each movie in the dataset is related to each other in terms of genres. Each row and column in this table represents one movie, and the value located in each cell illustrates the extent to which the two movies are similar based on the genres they share. A high Cosine Similarity value indicates that the two movies have a strong similarity in certain genres, while a lower value indicates a lower level of similarity.

This pivot table makes it easier to explore the relationship between the movies in the dataset and identify movies that are highly similar by genre. This lays the foundation for more accurate movie recommendations, as it visually displays movies that are similar in genre. This pivot table is a very important tool in understanding and visualizing the degree of similarity between movies in the context of genre, which is the core of the content-based recommendation method applied in this project. The following is an illustration of the pivot table that was successfully created.

| 'title'  | Toy Story (1995)  | Jumanji (1995)  | Grumpier Old Men (1995)  |  ...  |
|---|---|---|---|---|
| Toy Story (1995)  | 1.000  | 0.774597  | 0.316228  |
|  Jumanji (1995) | 0.774597  | 1.000  | 0.000000  |
|  Grumpier Old Men (1995) | 0.316228  | 1.000  | 0.000000  |
|  ... | ...  | ...  | ...  |

As an example of how to read the table above, the movies Toy Story (1995) and Jumanji (1995) have a degree of similarity of 0.774597. With a maximum value of 1,000, the two movies can be said to be 77.46% similar based on their genre.

## Modeling and Result
The development model used in this project is Content-Based Filtering, a recommendation method that relies on the intrinsic features of the items to be recommended, in this case, movies. This model was chosen because it is highly relevant to the available dataset, which includes movie data along with the various genres associated with each movie.

![1 Lr6qL0YjY_WqVK5u-AYHAQ](https://github.com/Loically/Movies_System_Recommender/assets/114181235/3aea8555-7ccb-4be7-b0a6-d83116c792bf)

In this research, the Content-Based Filtering model begins by extracting features from the movie dataset. The genres connected with each film are the key features utilised. Using a one-hot encoding strategy, each genre is first turned into a binary representation. That is, each film is represented as a binary vector, with each element indicating the existence or absence of a genre in the film. This generates a numerical representation that may be used to calculate similarity.

The Content-Based Filtering model then analyzes the movies previously enjoyed by the user with other movies in the dataset based on genre similarity to propose movies to the user. This is accomplished by computing the similarity score between the genre vector of the user's chosen movie and the genre vector of all movies in the dataset. The Cosine Similarity metric is used to produce this similarity score, which evaluates the angle between genre vectors in a high-dimensional space. The lower the angle between two vectors, the more genre-related the two films are.

$$
Cosine Similarity = \frac{{A \cdot B}}{{\|A\| \cdot \|B\|}}
$$

Cosine Similarity is a helpful measure for quantifying vector similarity in this situation since it ignores vector scale and only considers vector direction. The direction of the genre vector in this example represents the degree to which two movies have comparable genres. The outcome of this Cosine Similarity computation is used to sort and recommend movies to the user based on their similarity score.

Thus, in this project, the Content-Based Filtering model integrates feature extraction, genre similarity calculation using Cosine Similarity, and suggestions based on the most related genres. Based on the analysis of the movie genres offered, the system is able to generate recommendations that are more tailored and in accordance with the user's interests. In addition, after suggesting a movie, the genre information of the suggested movies is presented in one column in the notebook's movie_recommendations() function to offer the user a better idea of why the recommendation was made.

The model was tested to find movies that are similar to the movie 'Toy Story (1995)'. The model test results are attached as the table below which displays **TOP 10 Movie Recommendations**.

| title  | similarity_score  | genres  |
|---|---|---|
|  Tale of Despereaux, The (2008) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Moana (2016) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Shrek the Third (2007) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Antz (1998)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Wild, The (2006)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Monsters, Inc. (2001) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Toy Story 2 (1999)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Turbo (2013)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Phantom Tollbooth, The (1970) |  0.894427 |  Adventure, Animation, Children, Fantasy |
|  We're Back! A Dinosaur's Story (1993) |  0.894427 |  Adventure, Animation, Children, Fantasy |

## Evaluation
The usage of accuracy measures in this recommendation system is highly useful and vital in evaluating the quality of the recommendations offered. Precision is a statistic that gauges how relevant and relevant the movies recommended by the system are to the user's tastes.

The formula for determining accuracy is straightforward:

$$
Precision = \frac{\text{Number of Relevant Movies}}{\text{Total N Recommendations}}
$$

The accuracy measure ensures that the recommendations supplied are not only many, but also of high significance. To prevent making suggestions that are mostly conflicting with user preferences.

According to the test findings, eight of the ten recommended movies share the same genre (similarity_score = 1.0000). Using a basic precision formula, this model's accuracy value is 80.0%.
