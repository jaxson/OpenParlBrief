# OpenParlBrief - Project Scope

<!-- 
Credits: This project was inspired by Murad Hemmadi's reporting in The Logic on the federal government's ParlBrief AI tool (https://thelogic.co/news/parliament-ai-cohere/), developed by the Innovation, Science and Economic Development Canada (ISED) team. OpenParlBrief aims to create an open-source, publicly accessible version of similar capabilities.
-->

## What is OpenParlBrief?

An autonomous AI agent that monitors Canadian parliamentary committees, automatically transcribing meetings and publishing factual summaries through Twitter and RSS feeds that citizens can follow.

## Core Features

1. **Autonomous Monitoring**: Automatically detect new committee meetings from OurCommons and ParlVu
2. **Real-time Processing**: Transcribe and analyze meetings as they happen or shortly after
3. **Smart Summaries**: Generate factual, non-partisan summaries of key discussions and decisions
4. **Social Distribution**: Publish bite-sized updates to Twitter with links to full summaries
5. **RSS Feeds**: Organized feeds by committee, topic, or party for targeted following
6. **Archive Access**: Searchable database of all processed meetings and summaries

## Data Sources

- **OurCommons**: Official House of Commons committee audio and video
- **OpenParliament**: Parliamentary proceedings and voting records
- **ParlVu**: Video archives and streaming content from Parliament Hill

## MVP Scope

**Automated Pipeline**:
1. **Monitor**: Check OurCommons and ParlVu for new committee meetings (hourly)
2. **Ingest**: Download audio/video files automatically (MP3/WAV/MP4)
3. **Process**: Transcribe with Whisper, summarize with open-source LLM
4. **Publish**: Generate Twitter threads and RSS feed entries
5. **Distribute**: Post to @OpenParlBrief Twitter account and update RSS feeds

**Output Formats**:
- **Twitter Threads**: 3-5 tweets per meeting with key highlights and decisions
- **RSS Feeds**: Full summaries organized by committee (e.g., /feeds/finance, /feeds/justice)
- **Web Archive**: Searchable database of all transcripts and summaries
- **API Endpoints**: JSON feeds for developers and third-party integrations

## Technical Stack

- **Backend**: Python with FastAPI
- **AI Models**: Whisper (transcription) + Llama/Mistral (summarization)
- **Database**: PostgreSQL with full-text search
- **Scheduler**: Celery with Redis for automated monitoring and processing
- **Social APIs**: Twitter API v2 for posting, RSS generation libraries
- **Frontend**: Simple React web app for archive browsing
- **Deployment**: Docker containers with cron jobs

## Success Criteria

- **Automation**: Detect and process 90% of committee meetings without manual intervention
- **Speed**: Post Twitter summary within 4 hours of meeting completion
- **Accuracy**: >90% transcription accuracy and factual, non-partisan summaries
- **Reach**: Build audience of 1000+ Twitter followers and 500+ RSS subscribers
- **Coverage**: Monitor all major House committees (Finance, Justice, Health, etc.)

## Out of Scope (for now)

- Live tweeting during active meetings
- Political commentary or opinion (strictly factual reporting)
- Senate committee coverage (House of Commons only initially)
- Historical meeting analysis (focus on new meetings)
- Interactive features or user-generated content