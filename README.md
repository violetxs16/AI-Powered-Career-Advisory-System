# **AI-Powered Career Advisory System**

An AI-powered system designed to provide students/young adults with grounded career insights by leveraging professional podcast interviews. This project implements a Retrieval Augmented Generation (RAG) pipeline to process unstructured interview transcript data, retrieve semantically relevant excerpts, and generate personalized, context-rich career advice.

---

## **Getting Started**

These instructions will guide you through setting up and running a copy of this project in a Google Colab environment. The project requires access to Google Drive for transcript data storage and API keys for Pinecone (vector database) and Google Gemini (Large Language Model).

---

## **Prerequisites**

Requirements for the software and tools to build, test, and run the career advisory system:

* **Google Account** – Required for Google Colab and Google Drive access  
* **Google Colab Environment** – Recommended to use a GPU runtime (e.g., T4 GPU) for efficient embedding generation and LLM interactions  
* **Pinecone API Key** – For initializing and interacting with the vector database  
* **Google Gemini API Key** – For leveraging the Large Language Model for query formatting and response generation  
* **Python 3.x** – The core programming language for the notebook  
* **Required Python Libraries** – Installed via pip commands within the notebook  
  * `openai`  
  * `pinecone-client`  
  * `langchain`  
  * `sentence-transformers`  
  * `google-generativeai`  

---

## **Installing**

### **Step 1: Set up your Google Colab Environment**

1. Open the provided Jupyter notebook in Google Colab  
2. Navigate to `Runtime > Change runtime type` and select **T4 GPU** as the hardware accelerator, then click **Save**  
3. Securely store your API keys:  
   - In Google Colab, go to the left sidebar and click the **Secrets** icon 
   - Add two new secrets:  
     - `PINECONE_API_KEY` (paste your Pinecone API key here)  
     - `GEMINI_API_KEY` (paste your Google Gemini API key here)  
   - Ensure **Notebook access** is toggled **ON** for both secrets  

### **Step 2: Access Transcript Data**

1. Access the sample interview data folder on Google Drive: **Sample Transcripts**  
2. Create a shortcut to this folder in your own Google Drive:  
   - Navigate to the Google Drive folder linked above  
   - Click the down arrow next to the folder name (e.g., "Sample Transcripts")  
   - Select **Organize** from the menu  
   - Choose **Add Shortcut**  
   - From **All locations**, select **My Drive** and confirm  

### **Step 3: Run the Notebook Cells**

1. Run the first code cell in the notebook to install all necessary Python libraries. This may take a few minutes  
2. Run the subsequent code cells sequentially. These cells will:  
   - Mount your Google Drive to allow the notebook to access the transcript data  
   - Load and chunk the interview transcripts, extracting relevant metadata  
   - Generate vector embeddings for each transcript chunk  
   - Initialize the Pinecone vector database and upload the embeddings, making the data searchable  
   - Define helper functions for API calls, embedding, and query object parsing  

---

## **Running the Tests**

Once all the setup cells have been executed successfully, you can test the full RAG pipeline:

### **Step 1: Execute the RAG Pipeline Function**

- Scroll to the final code cell in the notebook (labeled `#Test your pipeline here for your user queries`)  
- Modify the `query` variable with your desired career-related question  
- Run only this cell to execute the complete RAG pipeline  

### **Step 2: Observe the Output**

- The notebook will print the **FINAL USER RESPONSE**, which is the AI-generated career advice, grounded in the podcast transcripts  

---

## **Built With**

* **Python** – Programming language  
* **Google Colab** – Cloud-based Jupyter notebook environment  
* **Pinecone** – Vector database for efficient similarity search  
* **Google Gemini API** – Large Language Model for natural language understanding and generation  
* **Sentence Transformers** – For generating high-quality vector embeddings  
* **LangChain** – Framework for developing applications powered by language models  
* **Google Drive** – Used as the data source for interview transcripts  
