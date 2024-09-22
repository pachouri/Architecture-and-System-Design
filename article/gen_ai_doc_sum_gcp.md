# Generative AI Document Summarization - GCP
![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/GEN_AI_DOC_SUMMARIZATION.gif?raw=true)

Generative AI document summarization solution, which leverages Vertex AI Generative AI Large Language Models (LLM) to process and summarize documents on demand.

This solution deploys a pipeline that is triggered when you add a new PDF document to your Cloud Storage bucket. The pipeline extracts text from your document, creates a summary from the extracted text, and stores the summary in a database for you to view and search.

| **Component** | **Product description** | **Purpose in this solution** |
| --- | --- | --- |
| [Cloud Storage](https://cloud.google.com/storage) | An enterprise-ready service that provides low-cost, no-limit object storage for diverse data types. | Stores the PDF documents and extracted text. |
| [Eventarc](https://cloud.google.com/eventarc/docs/overview) | A service that manages the flow of state changes (events) between decoupled microservices, routing events to various destinations while managing delivery, security, authorization, observability, and error handling. | Watches for new documents in the Cloud Storage bucket and triggers an event in Cloud Run functions. |
| [Cloud Run functions](https://cloud.google.com/functions) | A lightweight serverless compute service that lets you create single-purpose, standalone functions that respond to Google Cloud events without the need to manage a server or runtime environment. | Orchestrates the document processing steps. |
| [Document AI](https://cloud.google.com/document-ai) | A document understanding platform that takes unstructured data from documents and transforms it into structured data. You can automate tedious tasks, improve data extraction, and gain deeper insights from data. | Extracts the text from the documents. |
| [Vertex AI Generative AI](https://cloud.google.com/generative-ai-studio) | Generative AI support on Vertex AI gives you access to Google's large generative AI models so you can test, tune, and deploy them for use in your AI-powered applications. | Creates a summary from the extracted text stored in Cloud Storage. |
| [BigQuery](https://cloud.google.com/bigquery) | A fully managed, highly scalable data warehouse with built-in machine learning capabilities. | Handles the storage of the generated summary. |

**Request Flow**

The following steps detail the request processing flow of the application. The steps in the flow are numbered as shown in the preceding architecture diagram.

1. When the document is uploaded, it triggers a Cloud Run functions. This function runs the Extractive Question-Answering process.
2.  1. The Cloud Run function uses Document AI Optical Character Recognition (OCR) to extract all text from the document.
3. The Cloud Run function uses Vertex AI Gemini to extract all text from the PDF file.
4. The Cloud Run function stores the textual summaries of PDFs inside a BigQuery table.
5. The Cloud Run function stores the extracted text inside a Cloud Storage bucket.
