# nsql-challenge
The UK Food Standards Agency provides ratings to various establishments across the United Kingdom based on hygiene and other criteria. This project involves setting up a MongoDB database and performing exploratory data analysis using Jupyter notebooks to help editors at "Eat Safe, Love" magazine decide where to focus future articles.

Part 1: Database and Jupyter Notebook Set Up
- Database Setup Using NoSQL_setup_starter.ipynb
- Within your notebook, import necessary libraries: PyMongo and pprint.
- Create an instance of the Mongo Client.
- Confirm database and collection creation:
  - List databases (list_database_names()), confirm uk_food.
  - List collections in uk_food (list_collection_names()), confirm establishments.
  - Use find_one() with pprint to display a document from establishments.
    
Part 2: Update the Database
- Database Modifications

- Add a new halal restaurant:

python
Copy code
{
    "BusinessName": "Penang Flavours",
    "BusinessType": "Restaurant/Cafe/Canteen",
    "AddressLine1": "Penang Flavours",
    "AddressLine2": "146A Plumstead Rd",
    "AddressLine3": "London",
    "PostCode": "SE18 7DY",
    "LocalAuthorityCode": "511",
    "LocalAuthorityName": "Greenwich",
    "LocalAuthorityWebSite": "http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress": "health@royalgreenwich.gov.uk",
    "scores": {
        "Hygiene": "",
        "Structural": "",
        "ConfidenceInManagement": ""
    },
    "SchemeType": "FHRS",
    "geocode": {
        "longitude": "0.08384000",
        "latitude": "51.49014200"
    },
    "RightToReply": "",
    "Distance": 4623.9723280747176,
    "NewRatingPending": True
}

- Find BusinessTypeID for "Restaurant/Cafe/Canteen".
- Update the new restaurant with BusinessTypeID.

Remove establishments in Dover:
- Count documents in Dover.
- Remove documents in Dover and verify deletion count.
Convert string numbers to integers:
- Use update_many() to convert latitude, longitude, and RatingValue.
Part 3: Exploratory Analysis

Data Analysis Using NoSQL_analysis_starter.ipynb
  - Answer specific questions for Eat Safe, Love magazine:
    - Use count_documents, pprint, and convert results to Pandas DataFrame.
    - Explore hygiene scores, ratings, and local authority statistics.

Example questions:
- Establishments with hygiene score equal to 20.
- Establishments in London with RatingValue >= 4.
- Top 5 establishments with RatingValue of 5, sorted by lowest hygiene score near "Penang Flavours".
- Local authority areas with establishments having hygiene score of 0.

Hints and Techniques
- Utilize MongoDB queries, aggregation pipelines, and geospatial comparisons for analysis.
- Ensure data integrity by coercing non-numeric values and converting data types as needed.
