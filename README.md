# AI-Disaster-Agent
A multi-agent AI system using Gemini LLMs, Google Search grounding, and Pydantic to identify, analyze, and generate structured insights on natural disaster events.

## Overview

AI Disaster Agent is an interactive Python project that uses Google Gemini 2.5 Flash, Google Search grounding, Pydantic, and the Wikimedia Commons API to identify a disaster event and assemble a structured situation report. It combines conversational intent clarification, event research, rule-based severity scoring, image collection, AI summarization, and timeline generation.


## Key Features:

- Intent clarification: Asks follow-up questions to collect disaster type, location, and approximate time period.
- Grounded event research: Uses Gemini 2.5 Flash with Google Search grounding to identify an event, collect impact details, and gather article links.
- Structured validation: Uses Pydantic models to validate intent, event details, images, situation briefs, and timeline entries.
- Severity scoring: Calculates a custom 1–5 score using reported deaths, injuries, displacement, and infrastructure damage.
- Image enrichment: Searches Wikimedia Commons for relevant images and associated licensing/author metadata; downloads image files locally.
- Situation brief: Produces a headline, overview, impact summary, affected-population notes, response summary, key facts, and source URLs.
- Timeline generation: Creates a chronological list of major developments, including times when available.
- Console report: Displays the resulting disaster situation report in a readable format.


## System Workflow

The project follows a multi-stage AI processing workflow:

1. Event Identification: AI agents identify natural disaster events using LLM capabilities and available information.
2. Information Retrieval: Google Search grounding provides relevant external information.
3. Event Analysis: Gemini models process the retrieved information to generate insights.
4. Output Validation: Pydantic schemas validate the structure of generated responses.
5. Structured Results: The system produces organized information for further analysis.

## Getting started (Google Colab)
1. Open Full Pipeline AI Agent.ipynb in Google Colab.
2. Under Secrets (key icon), add a secret named GOOGLE_API_KEY containing your Gemini API key. Enable notebook access to that secret.
3. Run the notebook cells from top to bottom. The notebook installs its dependencies with:
 
   !pip install -q google-genai langchain langchain-google-genai requests pytest
4. The final cell runs run_disaster_agent(). Respond to the clarification agent's prompts about the disaster you want to research. Type quit to exit the clarification stage.
5. Review the console report. The pipeline also returns the assembled event data as final_event_data.
   
Requirements: Internet access, a valid Gemini API key, and access to Google Search grounding and Wikimedia Commons. API usage may incur costs or be subject to quotas.


## Concepts

This project demonstrates practical experience with:

- LLM-based application development
- Multi-agent AI architectures
- API integration
- Structured data validation
- Prompt-driven information processing
- Search-grounded AI workflows
- Python software development


## Project Motivation

Natural disaster information can be distributed across multiple sources and presented in different formats, making it challenging to identify and organize relevant details efficiently.

This project explores the use of AI agents to assist with information retrieval and analysis while producing structured outputs that can be used in downstream applications.


## Future Improvements

Potential extensions include:

- AI-generated casualty estimates, summaries, sources, and timelines require fact-checking against authoritative reporting.
- Search-grounded results and Wikimedia API responses may vary or fail; error handling and retries could be improved.
- The severity scoring rubric is heuristic and does not account for data uncertainty.
- Additional automated tests, source verification, clearer separation of pipeline modules, and an interactive UI would improve maintainability and usability.


