# HekimaBot

HekimaBot is a Java AI chatbot that uses your documents as context to answer questions using RAG (retrieval augmented generation).  
The chatbot uses [LangChain4j](https://github.com/langchain4j/langchain4j) and the OpenAI API (or a local LLM) to generate responses, and [Vaadin](http://vaadin.com/) to create the user interface.

---

## Configuration

### Documentation Location

Update the `docs.location` property in `application.properties` to point to a folder with your documents.  
LangChain4j uses Apache Tika internally, so most file types are supported.

### AI Model Options

#### Using OpenAI

OpenAI provides high-quality responses but requires sending data to a third party.  
- Obtain an [API key](https://platform.openai.com/api-keys) and configure it in `application.properties`.  
- You can also configure the model in the properties.

#### Using a Local LLM

Local models keep your data on your computer but may provide lower-quality responses.  
- Install [Ollama](https://ollama.com/) and the `llama3` model.  
- Comment out the OpenAI section in `application.properties` and uncomment the Ollama section.

### Optional: Embedding Store (Vector DB)

By default, HekimaBot uses an in-memory embedding store, suitable for demos and small datasets.  
For larger datasets, you can use any [embedding store supported by LangChain4j](https://docs.langchain4j.dev/integrations/embedding-stores/).

---

## Running the Application

HekimaBot is a standard Maven project.  

### From the Command Line

**Windows:**
```bash
mvnw spring-boot:run
