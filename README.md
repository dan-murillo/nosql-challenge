# Analysing British restaurants data (Non-SQL databases *Challenge 12*)

This repository contains a mini-project in which I acted as a data scientist who was contracted by the fictional magazine *Eat, Safe, Love*. I analysed restaurants data of the [UK Food Standards Agency (FSA)](https://ratings.food.gov.uk/open-data/en-GB).

## Author

Daniel Ramón Murillo Antuna [@daniel-r-murillo-antuna](https://www.github.com/daniel-r-murillo-antuna)

## Repository description

The FSA are an independent UK government department that are responsible for food safety and food hygiene in England, Wales, and Northern Ireland. According to their website, they protect public health and consumers' wider interests when it comes to food. They were established in the year 2000 and their mission is *food you can trust*.

The fictional magazine *Eat, Safe, Love* needed a data scientist who could evaluate some of the FSA data to help journalists and food critics decide what to focus on in future articles. In order to reach this objective, the mini-project was divided into three parts.

### Part 1: Database and Jupyter Notebook set up
This first part included basic actions to prepare the data for the analysis, such as importing the data of the *establishments.json* file in the *Resources* folder of this repository, creating the database in MongoDB and calling it `uk_food`, creating a collection called `establishments`, importing the dependencies needed —*PyMongo, Pretty Print, and Pandas*—, creating an instance of the Mongo Client, and displaying one of the documents in the `establishments` collections to double-check whether the database was correctly imported and to browse the type of information contained in a document.

### Part 2: Updating the database
The database had to be updated, since the magazine editors requested some database modifications; they asked me to include a new halal restaurant that just opened in Greenwich in the analysis. The new restaurant was added. All the restaurants in Dover were dropped because the magazine was not interested in them, and the latitude and longitude of all the documents was changed from string to decimal numbers.

### Part 3: Exploratory analysis
The magazine was interested in four main questions that would help them find the locations that they wanted to visit and the ones they wanted to avoid. The questions are outlined below:

#### 1. Which establishments have a hygiene score equal to 20? 
41 establishments were found to have a score equal to 20. Some of them were *The Chase Rest Home*, *Brenalwood*, *Melrose Hotel*, *Seaford Pizza*, and *Golden Palace*. You can find all of them in the `hygiene_score_20_df` Pandas DataFrame in the *NoSQL_analysis.ipynb* file.

#### 2. Which establishments in London have a `RatingValue` greater than or equal to 4?
34 establishments were found to have a `RatingValue` greater than or equal to 4. Some of them were *Charlie’s*, *My City Cruises Erasmus*, *Benfleet Motor Yacht Club*, *Tilbury Seafarers Centre*, and *Coombs Catering t/a The Lock and Key*. You can find all of them in the `london_rating_gte_4_df` Pandas DataFrame in the *NoSQL_analysis.ipynb* file.

#### 3. What are the top 5 establishments with a `RatingValue` rating value of '5', sorted by lowest hygiene score, nearest to the new restaurant added, *Penang Flavours*?
The top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, and closest to ‘Penang Flavours’ were: *Howe and Co Fish and Chips - Van 17*, *Atlantic Fish Bar*, *Plumstead Manor Nursery*, *Iceland*, and *Volunteer*.

#### 4. How many establishments in each Local Authority area have a hygiene score of 0?
The database contained 55 local authorities, and the number of establishments whose hygiene score was 0 varied from 1130 to 1. The local authorities with the most establishments were Thanet, Greenwich, Maidstone, Newham, and Swale with 1130, 882, 713, 711, and 686 establishments respectively. On the contrary, Dorset, Broxbourne, Sunderland, North Norfolk, Reading, and Kensington and Chelsea have the least establishments with a hygiene score of 0, as each of those local authorities has only 1 of that type of establishment. You can find all the numbers per local authority in the Pandas DataFrame `hygiene_0_per_local_authority_df` in the *NoSQL_analysis.ipynb* file.

To sum up, there were 41 establishments with a hygiene score equal to 20, 34 establishments were found to have a `RatingValue` greater than or equal to 4, *Howe and Co Fish and Chips - Van 17* is the closest establishment to *Penang* that has a `RatingValue` of 5 and the lowest hygiene score, and Thanet is the local authority with the most establishments whose hygiene score is 0. Should the magazine want to write about poor hygiene restaurants, they should look more into the top local authorities listed in question 4. Otherwise, they can look into the restaurants listed in questions 1 and 2.

This repository contains the Python code and the JSON file used to analyse the FSA data.

### The *Resources* folder:

It has the *establishments.json* file, which contains the data that was analysed in this mini-project.

### The *NoSQL_analysis.ipynb* file:

It contains the Python code of Part 3, which was used to analyse the non-SQL (MongoDB) database and answer the four questions posed by the magazine.

### The *NoSQL_setup.ipynb* file:

It has the Python code of Part 1 and 2, which was used to set up the database, update the database, and clean the data.


## Data Reference

UK Food Standards Agency (2022). UK food hygiene rating data API. [https://ratings.food.gov.uk/open-data/en-GB](https://ratings.food.gov.uk/open-data/en-GB). Contains public sector information licensed under the Open Government Licence v3.0. Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).

```#Thank you for reading me!```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)