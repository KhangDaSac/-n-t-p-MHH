# Quiz

## Data Modeling in MongoDB

Which of the following statements are true about data modeling using MongoDB?

- **MongoDB will help you iterate on the schema designs of your models throughout your application's lifecycle.**
- MongoDB should only be used for unstructured datasets.
- MongoDB is schema-less so you should not worry about designing a schema for your models.

## The Document Model in MongoDB

Which of the following statements are true about MongoDB documents?

- **MongoDB documents have a flexible schema.**
- MongoDB documents within a collection must have the same fields.
- **MongoDB documents are stored as BSON documents.**

## Constraints in Data Modeling

Which of the following is not a usual constraint that would impact your data model for MongoDB?

- Security
- Disk Drives
- **Operating System**
- RAM
- Network

## The Data Modeling Methodology

Which of the following phases are included in our data modeling methodology for MongoDB?

- **Applying schema design patterns.**
- **Identify the relationships between models.**
- **Identifying the workload of the system.**

## Model for Simplicity or Performance

Which of the following are use cases in which you should model your data for performance rather than simplicity?

- **It is expected that the solution will be designed with only 10 shards.**
- There is not an applicable design pattern to the solution.
- **The application is being developed by 100 engineers.**

## Identifying the Workload

Which of the following is not part of the first phase of the data modeling methodology?

- Listing the read operations.
- Quantifying each of the operations in terms of latency and frequency.
- **Identifying the relationships between the units of data.**
- Identifying the durability of each write operation.
- Listing the write operations.


# Quiz

## Relationship Types and Cardinality

Why did we introduce the one-to-zillions relationship in our modeling notation?

- **To highlight the fact that huge cardinalities may impact design choices.**
- To address the fact that a crow's foot has 5 fingers, not 3.
- **To address the fact that the concept of relationship linked to a huge number of entitites is missing in normal crow's foot notation.**

## One-to-Many Relationship

Consider a one-to-many relationship observed between a county and the cities in that county.

Which of the following are valid ways to represent this one-to-many relationship with the document model in MongoDB?

- **Embed the entities for the cities as an array of sub-documents in the corresponding county document.**
- Embed all the fields for a city as a subdocument in the corresponding county document.
- **Have a collection for the counties and a collection for the cities with each city document having a field to reference the document of its county.**

## Many-to-Many Relationship

Consider a many-to-many relationship observed between movies and the actors starring in these movies, for a system that could provide detailed information about either a movie or an actor.

![](https://university-courses.s3.amazonaws.com/M320/rst-images-prob_movies_actors.png)

Which of the following are true about modeling this many-to-many relationship with the document model in MongoDB?

- **Embedding actors in movies creates duplication of actor information.**
- When using one collection for movies and one collection for actors, all movie documents must have an array of references to the actors in that movie, and all actor documents must have an array of references to the movies they appear in.
- **Embedding actors in movies still requires a separate collection to store all actors.**

## One-to-One Relationship

Which of the following are valid ways to represent a one-to-one relationship with the document model in MongoDB?

- **Embed the fields in the document.**
- **Link to a single document in another collection.**
- **Embed the fields as a sub-document in the document.**

## One-to-Zillions Relationship

Which of the following statements are true about one-to-zillions relationships?

- **The relationship representations that embed documents are not recommended.**
- **It is a special case of the one-to-many relationship.**
- **We must take extra care when writing queries that retrieve data on the zillions side.**

# Quiz

## Guide to Homework Validation

Please follow the steps outlined in this lecture and included in the lecture notes.

**To run the validator for the example lab on Windows, run the following command:**

```validate_m320 example --file answer_schema.json```

**To run the validator for the example lab on MacOS and Linux, run the following command:**

```./validate_m320 example --file answer_schema.json```

Then, paste the validation code from the example lab into the text box below and hit the submit button.

**5d124f9bd971a774b97b5fc7**

## Handling Referential Integrity

Which of the following are valid concerns regarding duplication, staleness and referential integrity management in a MongoDB database and appropriate resolution techniques?



- **Data integrity issues can be minimized by using multi-document transactions.**
- Data duplication should not exist and can be avoided with multi-document transactions.
- **Data staleness issues can be minimized with frequent batch updates.**

## Attribute Pattern

Which one of the following scenarios is best suited for the application of the Attribute Pattern?



- The working set does not fit in memory.
- The documents need strict validation.
- **Some fields share a number of characteristics, and we want to search across those fields.**
- The system is accessing the disk too frequently.
- The documents are large.

## Extended Reference Pattern

Which one of the following scenarios is the best candidate to use the Extended Reference Pattern to avoid doing additional reads through joins/lookups?



- An app needs to retrieve a product and its ten most recent reviews.
- A product model needs to store references to images of the product that are kept in an external location outside the database.
- **An app needs to retrieve a product and information about its supplier.**
- An order model needs to store the product ID, the price sold, and the quantity ordered for each product in an order.
- A product model needs to store a counter representing the number of times it was purchased.

## Subset Pattern

Which one of the following scenarios is the best candidate for use of the Subset Pattern?



- The system is running out of RAM.
- The developers of the system have left and no one understands the application.
- **The working set does not fit in memory and it is difficult to scale the hardware.**
- The system is accessing the disk too frequently
- The documents are too big.

# Quiz

## Computed Pattern

Which one of the following scenarios is best suited for the application of the Computed Pattern?

- We need to group documents and sum on a field.
- We need to calculate a value that is displayed once per minute and is based on a field which updates 100 times per minute.
- **We need to calculate a value that is displayed 100 times a minute and is based on a field which updates once a minute.**
- We need to calculate a value that is displayed 100 times a minute and is based on a field which updates 100 times per minute.
- We have too much information to store in a single document.

## Bucket Pattern

Which one of the following requirements in our system is the best candidate to use the Bucket Pattern?

- Our system handles 1 million IOT devices.
- Our system must embed a one-to-many relationship in one of our models, however, some of the result documents would be too big.
- **Our system ingests thousands of log lines each day for each host it monitors.**
- Our system performs sums and averages over all elements of certain arrays.
- Our system ingests 10 million pieces of data per day from 1 million devices, with 20% coming from 10 devices.

## Schema Versioning Pattern

Which one of the following scenarios is the best candidate for the use of the Schema Versioning Pattern?

- **I want to avoid downtime when upgrading my schema.**
- I can schedule a window of downtime long enough to migrate the documents to the new version.
- I want to keep track of the changes to my documents.
- I have billions of documents.
- I have many obsolete documents.

## Tree Patterns

Which of the following scenarios would be ideal to use the Tree Pattern?

- **Company organization charts**
- **Product categories**
- Contact lists of users

## Polymorphic Pattern

Which one of the following scenarios is best suited for the use of the Polymorphic Pattern?

- **The organization acquired different companies over the years, serving the same markets with the same customers and there is a requirement to merge all systems into one.**
- There is a requirement to keep many versions of a document, and these versions may have different fields for each version.
- The application has a base class with some derived classes.
- There are billions of documents.
- There is a requirement to store addresses for my customers.

## Other Patterns

A pharmaceutical company needs to implement a design to model the relationships between the company and its partners, customers, and suppliers. A team came up with a design that works perfectly, meeting all performance requirements. However, when loading the real data in the system, they realized that one customer, the U.S. government had too many contacts to be stored into the designated array for this information.

Instead of redesigning the whole system to make this customer fit well into the new data model, which pattern can you use?

- The Schema Versioning Pattern.
- The Pharmaceutical Pattern.
- **The Outlier Pattern.**
- The Attribute Pattern.
- The Subset Pattern.
