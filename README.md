# AI-Powered Agent Builder for VCT Manager
## Description
An Agentic RAG (Retrieval-Augmented Generation) system for a VCT (Valorant Champions Tour) AI Coach is a highly valuable project that combines multi-agent workflows, real-time gaming data, and tactical analysis.

## Business Objective
Develop an AI-powered VCT analytics assistant capable of answering factual, statistical, comparative, and strategic questions about professional Valorant matches using structured match data and unstructured knowledge sources.

## Data Ingestion Pipeline Architecture
                  ┌────────────────────────┐
                  │      Data Sources      │
                  └────────────┬────────────┘
         ┌─────────────────────┼────────────────────┐
         ▼                     ▼                    ▼
┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│   Patch Notes /  │  │  VLR.gg / Kaggle │  │   GRID API /     │
│ VOD Transcripts  │  │   Match History  │  │    Telemetry     │          
└────────┬─────────┘  └────────┬─────────┘  └────────┬─────────┘
         ▼                     ▼                    ▼
┌───────────────────┐ ┌──────────────────┐ ┌──────────────────┐
│ Unstructured Track│ │ Structured Track │ │ Live Stream Track│
│ (Semantic Chunk)  │ │   (ETL/Parser)   │ │  (GraphQL/JSONL) │
└────────┬──────────┘ └────────┬─────────┘ └────────┬─────────┘
         │                     │                    │
         ▼                     ▼                    ▼
┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│ Vector Database  │  │ Relational DB    │  │ Global Agent     │
│ (Qdrant Cloud)   │  │ (Postgres / SQL) │  │ Execution State  │
└──────────────────┘  └──────────────────┘  └──────────────────┘
