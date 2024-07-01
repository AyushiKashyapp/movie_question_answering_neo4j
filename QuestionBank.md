# Question Bank

1. **Why did I choose Neo4j for this project?**
Neo4j is a powerful graph database that is particularly well-suited for handling interconnected data like movies and their relationships with actors, directors, and other entities. Its Cypher query language allows for efficient querying of complex relationships, making it ideal for this type of application.

2. **How does the system connect to the Neo4j database?**
The system connects to the Neo4j database using the `neo4j-driver` library. A driver object is created with the necessary credentials to establish a connection using the Bolt protocol. This driver is then used to open sessions and execute Cypher queries.

3. **What role does the Spacy library play in the system?**
The Spacy library is used for natural language processing (NLP) to extract entities from user questions. It helps identify specific entities such as movie titles and director names, which are then used to construct and execute relevant Cypher queries on the Neo4j database.

4. **How do I handle entity extraction from user queries?**
The system processes the user input using Spacy's NLP model. It scans the text for entities labeled as "WORK_OF_ART" or "MOVIE" to extract movie titles, and "PERSON" for director names. These extracted entities are then used to query the Neo4j database for the relevant information.

5. **What are some challenges you faced with this project?**
Some challenges included ensuring accurate entity extraction from user queries, handling variations in user input, and optimizing Cypher queries for efficient data retrieval. Additionally, integrating the Gradio interface for a smooth user experience was a significant aspect of the project.

6. **How does the chatbot maintain conversation history?**
The chatbot maintains conversation history by appending each user input and the corresponding response to a history list. This history is passed back and forth during each interaction, allowing the chatbot to keep track of the dialogue context.

7. **Explain the functionality of the `get_answer` function?**
The `get_answer` function processes the user question to determine the type of information requested, such as movie release dates. It uses extracted entities to formulate Cypher queries that retrieve the desired information from the Neo4j database. The function then returns the result to the user.

8. **What is the role of Gradio in the project?**
Gradio provides an easy-to-use interface for the question-answering system. It allows users to input their questions and receive responses in a chat-like environment. Gradio handles the frontend interaction, while the backend processes the queries and retrieves the answers from Neo4j.

9. **How do we ensure the accuracy of the system's responses?**
To ensure accuracy, the system relies on precise entity extraction using Spacy, well-constructed Cypher queries, and thorough testing with various user queries. Additionally, error handling is implemented to provide informative messages when the system cannot find the requested information.

10. **What are Cypher queries and how are they used in this project?**
Cypher is the query language for Neo4j, designed specifically for querying graph databases. In this project, Cypher queries are used to retrieve information about movies, actors, and directors from the Neo4j database based on the entities extracted from user questions.

11. **What are the main components of the codebase?**
The main components include:
- **Database Connection**: Establishing connection with the Neo4j database using `neo4j-driver`.
- **NLP Processing**: Using Spacy to extract entities from user queries.
- **Cypher Query Execution**: Formulating and executing Cypher queries to retrieve data.
- **Chatbot Logic**: Handling user interactions, maintaining conversation history, and generating responses.
- **Gradio Interface**: Providing a web-based interface for users to interact with the chatbot.

These components work together to process user questions, extract relevant entities, query the database, and return accurate responses.

12. **How to handle variations in user input?**
The system uses Spacy's NLP capabilities to extract entities regardless of variations in phrasing. This allows it to identify the key elements of a question, such as movie titles, even if the wording changes. Additionally, the `get_answer` function is designed to understand common variations in questions related to movie release dates and other attributes.
