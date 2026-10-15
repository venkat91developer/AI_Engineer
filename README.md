# AI Engineer Learning Path

A project-first roadmap from Python to Agentic AI, based on the video roadmap slides plus additions.

**Legend:** 🆕 from the video slides · ➕ added by Claude · ⚠️ changed from an earlier draft

**Core idea:** keep theory minimal and build a project at every stage. Week numbers for Python, FastAPI, and Deep Learning come from the slides. The rest are estimates, so adjust them to your pace.

## Overview

| Phase | Topic | Weeks | Projects |
| --- | --- | --- | --- |
| 0 ➕ | Setup: Python, VS Code, Git, venv | Days 1-3 | None |
| 1 | Python foundations | 1-2 | Report Card Generator, Expense Tracker (console) |
| 2 | APIs and FastAPI | 3-5 | Expense Tracker (API) |
| 3 | Databases and SQL | 6-7 | Expense Tracker (API + DB) |
| 4 | Machine Learning | 8-13 | Score Predictor, Spam Classifier, Customer Segmentation |
| 5 | Deep Learning (TensorFlow) | 14-17 | MNIST, Cats vs. Dogs, Tweet Sentiment |
| 6 | Generative AI, non-agentic | 18-21 | Resume Screener, RAG Chatbot, Summarizers |
| 7 | Generative AI, agentic | 22-25 | Informational Agent, Travel Planner |
| 8 ➕ | Production skills | Ongoing | Deploy a capstone |

## Phase 0: Setup (Days 1-3) ➕

- Install Python, VS Code, and Git
- Learn basic Git/GitHub (commit, push, branch) so you can publish every project
- Learn basic terminal commands and virtual environments (`venv`)

## Phase 1: Python Foundations (Weeks 1-2)

**Topics**

- Variables and data types
- Conditional statements
- Looping constructs
- Functions
- Data structures: lists, tuples, dictionaries (➕ also sets)
- ➕ File handling, exceptions, and basic OOP (classes)

**Projects**

1. **Student Report Card Generator:** input ID, name, and marks; store marks in a dictionary; calculate average and grade; print a formatted report card.
2. **Personal Expense Tracker (console):** add expenses (category + amount) in a list of dictionaries, with functions for total spent and highest expense, and a view by category.

## Phase 2: APIs and FastAPI (Weeks 3-5)

**Concepts**

- What an API is, and request vs. response
- JSON structure
- Consuming an API from the command line (curl) and from Python (`requests`)
- Practice with restful-api.dev

**Building APIs with FastAPI (Weeks 4-5)**

- Build, test, and expose your own API
- ➕ Pydantic models for validation, HTTP methods and status codes, and the auto-generated `/docs` page

**Project: Expense Tracker, API Version**

1. Set up a FastAPI app in VS Code
2. Add an "Add Expense" endpoint and test it with Postman
3. Add a "Get All Expenses" endpoint
4. Add a "Highest Expense" endpoint

## Phase 3: Databases (Weeks 6-7)

- SQL fundamentals: SELECT, WHERE, JOIN, GROUP BY, aggregates
- Setting up database configuration in your app
- ➕ SQLite first, then PostgreSQL, and an ORM (SQLAlchemy or SQLModel)

**Project: Expense Tracker, API + DB Version (your first end-to-end app)**

1. Configure the database in the app
2. Modify Add Expense to store data in the DB
3. Modify Get All Expenses to read from the DB
4. Modify Highest Expense to query the DB

## Phase 4: Machine Learning (Weeks 8-13)

➕ **Prerequisites:** NumPy, Pandas, and basic statistics, linear algebra, and probability. You don't need heavy math, just enough to understand what the models do.

### 🆕 ML categories

- **Supervised learning**
  - Regression (predicting a number)
  - Classification (predicting a label)
- **Unsupervised learning**
  - Clustering (finding groups without labels)
- ➕ Reinforcement learning (awareness only, not a focus)

### 🆕 Project 1: Student Score Predictor (Regression)

**Goal:** predict exam scores from study hours, plus optional factors like test preparation and parental education.

- Take input such as hours studied and optional attributes
- Train a regression model to predict the exam score
- Compare predicted vs. actual scores
- Produce a simple evaluation report (accuracy or error rate)

**Concepts:** data cleansing, train/test split, model training, cost function, mean squared error (MSE)

**➕ Extras:** RMSE and R², and wrap the model in a FastAPI endpoint using Phase 2.

### 🆕 Project 2: Spam Email Classifier (Classification)

**Goal:** classify SMS or email text as spam or ham (not spam).

- Use a dataset of real SMS messages labeled spam or ham
- Clean and preprocess the text
- Train a classification model to detect spam
- Test on new, unseen messages
- Show performance metrics (accuracy or confusion matrix)

**Concepts:** text preprocessing, text vectorization, model training, accuracy, precision, recall

**➕ Extras:** TF-IDF, Naive Bayes vs. Logistic Regression, F1 score, and why accuracy misleads on imbalanced data.

### 🆕 Project 3: Customer Segmentation (Clustering)

**Goal:** group customers by spending habits and demographics.

- Use features like age, income, and spending score
- Apply clustering to form segments (high-value, budget, casual spenders)
- Visualize the clusters on a chart
- Summarize each cluster's key characteristics

**Concepts:** K-Means clustering, elbow method, data visualization, Matplotlib, Seaborn

**➕ Extras:** feature scaling, and the silhouette score as a second way to pick *k*.

### ➕ Cross-cutting ML skills

- Cross-validation, overfitting vs. underfitting, and hyperparameter tuning
- scikit-learn Pipelines, and saving models with `joblib`

## Phase 5: Deep Learning (Weeks 14-17, TensorFlow)

### 🆕 Neural network fundamentals

- Neurons, layers, weights, and activation functions
- ➕ Backpropagation, gradient descent, and optimizers (Adam, SGD)
- ⚠️ The video uses **TensorFlow**, so start there. Treat PyTorch as an optional follow-up after Week 17.

### 🆕 Project 1: Handwritten Digit Recognizer (MNIST)

**Goal:** recognize handwritten digits 0 to 9, a classic beginner project.

- Train a simple neural network on MNIST (70,000 handwritten digit images)
- Predict the digit for a new handwritten image
- Check accuracy on unseen test data
- Aim for **90%+ accuracy**

**Concepts:** layers, activation functions, training and test data, loss function / cross-entropy, model evaluation

### 🆕 Project 2: Cats vs. Dogs Classifier (CNN)

**Goal:** classify images as cat or dog with a Convolutional Neural Network.

- Train on thousands of cat and dog images
- The model learns features like edges, shapes, and textures
- Test on new images
- Prevent overfitting with data augmentation and validation checks

**Concepts:** convolutional neural networks, overfitting, data augmentation, model evaluation

**➕ Extras:** transfer learning (MobileNet or ResNet) reaches high accuracy with far less data and training time.

### 🆕 Project 3: Sentiment Analysis on Tweets (Text Classification)

**Goal:** classify tweets as positive or negative, and see how neural networks handle language.

- Train on a dataset of tweets labeled with sentiment
- Clean the text (remove stopwords and unnecessary characters)
- Convert words into embeddings (numerical vectors)
- Use an RNN/LSTM, or even a simple dense network, to capture word order and context
- Test on new tweets

**Concepts:** text preprocessing, word embeddings, recurrent neural networks (RNN/LSTM)

**➕ Extras:** compare against your Phase 4 Spam Classifier, and note how this prepares you for Transformers and LLMs.

## Phase 6: Generative AI, Non-Agentic (Weeks 18-21)

### 🆕 LLM foundations

- Large language model basics
- Pre-training
- Fine-tuning
- ➕ Tokens, context windows, temperature, and hallucinations
- ➕ Transformers and attention at a conceptual level, as the successor to RNN/LSTM
- ➕ Calling LLM APIs (Claude, Gemini, OpenAI) from Python, with API key handling via `.env`

### 🆕 Prompt engineering

- Prompt engineering basics
- Zero-shot prompting
- Few-shot prompting
- Chain of thought
- ➕ System vs. user prompts, structured outputs (JSON/Pydantic), and prompt versioning

### 🆕 Project: Resume Screening Application

**Flow:** the resume goes to the AI, which extracts resume details. The job description goes to the AI, which extracts job details. A third AI step compares the two and outputs **select / reject**.

- Two extraction steps feed one decision step
- ➕ Return structured JSON with a match score and reasons, not just a yes/no
- ➕ Test with a few resumes, and watch for bias in the decisions
- ➕ Wrap it in a FastAPI endpoint using Phase 2

### 🆕 Project: RAG Chatbot

**Concepts:** embeddings, vectorization, vector DB, data chunking, semantic search, top-k chunks

- Chunk documents, embed them, and store them in a vector DB
- Retrieve the top-k relevant chunks for each question
- Pass those chunks to the LLM to generate a grounded answer
- ➕ Vector DB options: Chroma or FAISS to start, pgvector later
- ➕ Chunk size and overlap, citing sources, and handling "I don't know"
- ➕ Evaluate retrieval quality, not just the final answer
- The creator has a 5-part RAG playlist, including a no-code n8n version and Python versions

### Other projects from the video description

- Text Summarizer
- PDF Q&A Bot (essentially the RAG project above, so you can combine them)
- YouTube Video Summarizer

## Phase 7: Generative AI, Agentic (Weeks 22-25)

### 🆕 Learning approach (framework order)

The slide lists LangChain, LangGraph, LlamaIndex, AutoGen, and CrewAI with a red X, read as "don't start with frameworks."

1. **Build with plain Python first**, with no agentic frameworks
2. **Rebuild the same application with LangGraph**, so you can see what the framework adds

⚠️ Google ADK and MCP are optional follow-ups, since the creator covers them in a separate playlist.

### ➕ Core agent concepts

- Tool/function calling: the LLM decides which tool to use
- The agent loop: reason, act, observe, repeat
- Planning and task decomposition
- Memory, short-term and long-term
- Guardrails, retries, and timeouts

### 🆕 Project 1: Informational Agent (Weather API / News API)

**Goal:** an agent that decides which external API to call based on the user's request.

- User asks something natural, like "What's today's weather in Chennai?"
- The agent recognizes it needs the Weather API
- It makes the request, retrieves the response, and formats a friendly answer
- Extend to multiple tools (News API, Dictionary API)
- Handle errors gracefully, with a fallback message if an API fails
- ➕ Test with ambiguous questions (weather with no city) and questions that need no tool

### 🆕 Project 2: Travel Planner Agent

**Goal:** plan a trip from destination, budget, and duration. Example: "Plan me a 3-day trip to Bangalore under ₹10,000."

- The agent breaks the task into steps: transport, accommodation, food, sightseeing
- It connects to APIs (flights, hotels, maps) to gather real options
- It combines the results into a structured daily itinerary within budget
- It presents the plan clearly, day by day
- ➕ Add a budget checker tool that verifies the total stays under the limit
- ➕ Return structured output, and have the agent revise the plan if it goes over budget

### ➕ Optional follow-ups

- Google ADK and MCP (Model Context Protocol)
- Bonus: a RAG-powered agent that uses your Phase 6 chatbot as one of its tools
- Human-in-the-loop approval and tracing/observability

## Phase 8: Production Skills (Ongoing) ➕

- Docker and containerizing your FastAPI apps
- Cloud deployment (Render, Railway, GCP, AWS, or Azure)
- Evaluating LLM apps (test sets, LLM-as-judge)
- Basic CI/CD, logging, and cost and latency monitoring
- Security basics: API key handling and prompt injection

## Project Checklist

| # | Project | Phase | Type |
| --- | --- | --- | --- |
| 1 | Student Report Card Generator | 1 | Python |
| 2 | Expense Tracker (console) | 1 | Python |
| 3 | Expense Tracker (API) | 2 | FastAPI |
| 4 | Expense Tracker (API + DB) | 3 | End to end |
| 5 | Student Score Predictor | 4 | Regression |
| 6 | Spam Classifier | 4 | Classification |
| 7 | Customer Segmentation | 4 | Clustering |
| 8 | MNIST Digit Recognizer | 5 | Neural network |
| 9 | Cats vs. Dogs | 5 | CNN |
| 10 | Tweet Sentiment Analysis | 5 | RNN/LSTM |
| 11 | Resume Screening App | 6 | GenAI |
| 12 | RAG Chatbot (+ PDF Q&A) | 6 | GenAI |
| 13 | Text Summarizer, YouTube Summarizer | 6 | GenAI |
| 14 | Informational Agent (Weather/News) | 7 | Agentic |
| 15 | Travel Planner Agent | 7 | Agentic |

## Suggested Habits ➕

- **Build in public:** put every project on GitHub with a clear README
- **One portfolio capstone:** deploy one polished app with a live link (Resume Screener, RAG Chatbot, or Travel Planner)
- **Ratio:** about 30% learning and 70% building
- **Weekly review:** write what you learned, what broke, and how you fixed it

## Datasets from the Video

- **ML:** Students Performance in Exams, SMS Spam Collection, Customer Segmentation (Kaggle)
- **DL:** MNIST, Dogs vs. Cats, Twitter Entity Sentiment Analysis (Kaggle)

## PATH STRUCTURE: 
ai-engineer/
├── 01-python-foundations/
│   ├── report-card-generator/
│   └── expense-tracker-console/
├── 02-fastapi/
│   └── expense-tracker-api/
├── 03-databases/
│   └── expense-tracker-db/
├── 04-machine-learning/
│   ├── student-score-predictor/
│   ├── spam-classifier/
│   └── customer-segmentation/
├── 05-deep-learning/
│   ├── mnist-digit-recognizer/
│   ├── cats-vs-dogs-cnn/
│   └── tweet-sentiment/
├── 06-genai/
│   ├── resume-screener/
│   └── rag-chatbot/
├── 07-agents/
│   ├── informational-agent/
│   └── travel-planner-agent/
└── notes/            # weekly reviews, cheat sheets