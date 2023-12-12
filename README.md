# Module-12-Challenge_nosql-challenge

Created a NoSQL Database with data from the UK Food Standards Agency and performed an exploratory analysis as follows:

NoSQL_setup
----------------------------
* Part 1: Database and Jupyter Notebook Set Up
  * Imported the data provided in the establishments.json file. Named the database uk_food and the collection establishments.
  * Imported the libraries needed: PyMongo and Pretty Print (pprint).
  * Created an instance of the Mongo Client.
    * Confirmed that the database was created and loaded the data properly:
    * Listed the databases in MongoDB. Confirmed that uk_food is listed.
    * Listed the collection(s) in the database to ensure that establishments is there.
    * Found and displayed one document in the establishments collection using find_one and display with pprint.
  * Assigned the establishments collection to a variable to prepare the collection for use.

* Part 2: Update the Database
  * An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked to include it in the analysis. Added the provided information to the database.
  * Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
  * Updated the new restaurant with the BusinessTypeID found.
  * The magazine is not interested in any establishments in Dover, so checked how many documents contained the Dover Local Authority. Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
  * Some of the number values are stored as strings, when they should be stored as numbers.
    * Used update_many to convert latitude and longitude to decimal numbers.
    * Used update_many to convert RatingValue to integer numbers.

NoSQL_analysis
----------------------------
* Part 3: Exploratory Analysis
  * Used the following questions to explore the database, and find the answers, to provide them to the magazine editors.
    * Unless otherwise stated, for each question:
      * Used count_documents to display the number of documents contained in the result.
      * Displayed the first document in the results using pprint.
      * Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.
  * Which establishments have a hygiene score equal to 20?
  * Which establishments in London have a RatingValue greater than or equal to 4?
  * What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
  * How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
