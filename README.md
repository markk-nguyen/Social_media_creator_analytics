# Social Media Creator Analytics Pipeline

Built an end-to-end data analytics pipeline to analyze 48,000+ real TikTok 
and YouTube Shorts videos, applying Python and SQL to surface creator 
engagement patterns and generate AI-powered strategy insights.

## Tech Stack
| Tool | Purpose |
|------|---------|
| Python (Pandas) | Data cleaning and transformation |
| PostgreSQL (Supabase) | Cloud database for storing and querying cleaned data |
| SQL | Analytics queries across creator tiers, genres, and platforms |
| Anthropic Claude API | Auto-generates plain-English strategy briefs from query results |
| Google Colab | Development environment |
| PowerBI | Dashboard-ready CSV exports |

## Dataset
Real-world dataset of 48,079 TikTok and YouTube Shorts videos sourced 
from Kaggle, covering 14 content genres across multiple regions in 2025.

## Dataset
Real-world dataset of 48,079 TikTok and YouTube Shorts videos sourced 
from Kaggle, covering 14 content genres across multiple regions in 2025.

**Source:** [YouTube Shorts and TikTok Trends 2025](https://www.kaggle.com/datasets/tarekmasryo/youtube-shorts-and-tiktok-trends-2025)

## What it does
1. Loads and inspects raw dataset using Pandas
2. Cleans data by removing low-value columns and reclassifying creator tiers
3. Loads cleaned data into a live PostgreSQL database on Supabase
4. Runs SQL queries to surface engagement patterns by genre, platform, and creator tier
5. Sends query results to Claude AI to auto-generate plain-English strategy briefs
6. Exports PowerBI-ready CSVs for stakeholder reporting

## Key finding
Mid-tier creators generate disproportionately high engagement relative to 
their view counts compared to larger tiers, suggesting brand partnership 
budgets are more effective when targeting growing creators over high follower counts.

## Status
Work in progress. SQL analysis queries and Claude API integration in development.
