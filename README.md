# AI-Powered-Q-A-System-on-PDF-LangChain-HuggingFace-FAISS-
To build an intelligent system where you can upload a PDF (like a solar energy report), ask questions about it in natural language, and get accurate answers using Language Models.


Step 1: Importing Required Libraries

➤ Explanation:
os: Interacts with the operating system (like checking directories, paths).

urllib.request.urlretrieve: Downloads files from the web.

numpy: A library for numerical computing and array manipulation.

!pip install langchain: Installs the LangChain library, which helps in building applications using LLMs (Large Language Models).

.

.

.

.

.


Step 2: Installing Sentence Transformers

➤ Explanation:
This command installs or updates the sentence_transformers package.

Sentence Transformers are used to convert text into embeddings—a numerical format that models can understand.
.
.
.
.
.
.
Step 3: Install and Import LangChain Modules

Purpose: This installs the langchain-community package, which includes various connectors for document loading, vector stores, LLMs, and more—specifically for open-source or community-supported tools.
.
.
.
.
.
.
.
.
.
Step 4: Main Module Imports

 Explanation:

HuggingFaceBgeEmbeddings: Converts text into vector representations using HuggingFace models.

HuggingFacePipeline: Loads and runs pre-trained HuggingFace LLMs.

PyPDFLoader / PyPDFDirectoryLoader: Loads text content from a single PDF or a directory of PDFs.

RecursiveCharacterTextSplitter: Splits documents into chunks for better processing by LLMs.

FAISS: Facebook AI Similarity Search – a fast vector search engine.

RetrievalQA: A LangChain chain that allows you to ask questions over documents.

PromptTemplate: Customizes the prompt format used for LLM inference.
.
.
.
.
.
.
.
Step 5: Install PDF Reader

 Explanation:

Installs pypdf, a lightweight library to read PDF files, often used internally by loaders like PyPDFLoader.
.
.
.
.
.
.
.
.
.
.
.
.
Step 6: Load the PDF Document

 Explanation:

This code initializes a PDF loader using a file path to a document named: solar_energy_v1.1-21-24.pdf.

The loader will extract text from the PDF for further processing (like chunking and embedding).






Load the PDF Document

Reads and extracts raw text from the PDF using LangChain’s community loader.
.
.
.
.
.
.
.
.
.
Step 7: Split the Text into Chunks


LLMs (like GPT or HuggingFace models) struggle with long text.

So, the PDF is divided into small, overlapping sections for better understanding.
.
.
.
.
.
.
.
.
.
.
.
Step 8: Convert Text to Embeddings

embedding = HuggingFaceBgeEmbeddings(model_name="BAAI/bge-small-en-v1.5")
 Text embeddings are like numerical fingerprints of text.They allow us to search semantically (based on meaning, not exact words).
.
.
.
.
.
.
.
.
.
.
.
Step 9: Store in FAISS Vector Database

vectordb = FAISS.from_documents(docs, embedding)
FAISS is a fast similarity search engine by Facebook. It stores all chunk embeddings so we can later retrieve relevant chunks during Q&A.
.
.
.
.
.
.
.
.
.
.
Step 10 : Define a Prompt Template

You can customize how the system asks the LLM questions. The system injects context (from the PDF) + your actual question.
.
.
.
.
.
.
.
.
.
.
.
.
.
Step 11 : Set Up Retrieval + QA Chain

Retriever → finds relevant document chunks

LLM → answers your question using those chunks
.
.
.
.
.
.
.
.
.
Step 12 : Ask Questions & Get Answers

You get a smart, context-aware answer from the AI, grounded in the document content.





Technologies Used

## Tech	Purpose


LangChain ---------------> Orchestration of LLM pipelines
.
.
HuggingFace ----------------> Embeddings & LLMs
.
.
FAISS	------------------------> Vector database for retrieval
.
.
PyPDFLoader	--------------------> Text extraction from PDFs
.
.
PromptTemplate ------------------> Custom LLM prompting
.
.
Retrieval ------------------------> QA	Final Q&A logic











