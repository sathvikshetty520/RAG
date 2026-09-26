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