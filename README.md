RAG:

Retrieval-Augmented Generation (RAG) is the process of optimizing the output of a large language model, so it references an authoritative knowledge base outside of its training data sources before generating a response.
Large Language Models (LLMs) are trained on vast volumes of data and use billions of parameters to generate original output for tasks like answering questions, translating languages, and completing sentences.
RAG extends the already powerful capabilities of LLMs to specific domains or an organization's internal knowledge base, all without the need to retrain the model.
It is a cost-effective approach to improving LLM output so it remains relevant, accurate, and useful in various contexts.

Example:
User gives a input query to LLM and it produces Output.
If Today is 31 August.If LLM is trained only till 1 Aug and if we ask a question on 31st Aug about recent events, It hallucinates
One option is we can fine tune it recent data .But problem with it is fine-tuning is expensive.Thats why we use RAG.
So along with LLM , we use LLM with vector DB. It basically converts text into vectors and store it.
User gives queries to vector db first and then it searches for neccesary data and send propmt to llm to give specified answers


RAG :
Two important pipeline

1. Ingestion pipeline

Chunking  ---> Breaking down Bigger files into small parts
Embedding models --> It is a model , which converts any kind of data like text , pictures into numerical vectors
Ex: Word Cat and Kitten will have similar/close numbers.

Vector DB - It's basically database where embedded data is stored 

2. Retrieval pipeline 

Query - User gives a request for retrieving of data
Also keep note that we must use same embedding model for both user queries and document conversion 

Example

1. I have a long pdf file.(let's say 10 Million Tokens)

2. I have to first divide them into chunks of a specific amount of tokens. (5000 tokens creating one chunk, so 10M will create 2K chunks)

3. I have to pass the chunks into an embedding model.

4. Embedding Model Outputs 2000 vector embeddings.

5. I store them in a Vector DB.

6. Diya asked a question.

7. I have to pass the query to the exact same embedding model with same dimensions used before to embed and get an embedding representation for the question.

8. A retriever component is going to go through all the 2000 embeddings.

9. It will find the top most similar embeddings along with their textual chunks.

10. I have to ask LLM now "This is the user question, these are the possible answers, find which one is correct and answer the question"

Data Ingestion:Taking pdf,html,excel files
Data Parsing: Checking documemt structure
Chunking: Dividing those data into pieces
Embedding:Coverting into vectors of fixed context
Vector DB: Storing vecors in DB