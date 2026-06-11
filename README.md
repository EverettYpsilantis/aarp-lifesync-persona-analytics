# aarp-lifesync-persona-analytics
K-Means persona segmentation, topic intelligence pipeline, and Medicare plan analysis built for AARP consulting engagement

# AARP LifeSync: Persona Analytics & Content Intelligence

A consulting engagement delivering data-driven persona segmentation, content gap 
analysis, and Medicare plan intelligence to support AARP's LifeSync personalization platform.

## Project Overview

LifeSync transforms AARP from a content provider into an active decision-support 
companion for members 50+. This repository contains the full analytical pipeline, 
from member segmentation through content gap identification to Medicare plan recommendation logic.

## Notebooks

### 1. `Persona_RAND.ipynb`: Member Persona Segmentation
K-Means clustering on RAND Health and Retirement Study (HRS) survey data (Wave 15, 2020).
Engineered three composite features, health burden, lifestyle engagement, and life stage — 
across 10+ clinical and behavioral variables. Validated cluster count using elbow method 
and silhouette scoring. Output: three distinct member personas with radar chart fingerprints 
and full demographic/clinical profiles.

### 2. `AARP_Topic_Intelligence_Pipeline.ipynb`: Content Gap Analysis
Multi-source topic intelligence pipeline combining Google Trends keyword tracking, 
RSS feed scraping across competitor outlets (Next Avenue, AARP.org, etc.), and 
semantic similarity analysis using sentence transformers. Identifies where AARP's 
content coverage falls short relative to trending member search behavior and news cycles.

### 3. `aarp_marketing_plan.ipynb`: Persona-Driven Marketing Strategy
Merges Pew Research Internet & Technology Survey data with synthetic CDC BRFSS-calibrated 
health data to build a channel-frequency-format matrix per persona. Produces a 
Phase 4-ready campaign brief with platform, content type, and messaging recommendations 
tailored to each segment.

### 4. `Health_plan_analysis.ipynb`: Medicare Plan Landscape Analysis
Analyzes CMS 2026 Medicare Advantage plan landscape and enrollment performance data. 
Cleans and standardizes premium, deductible, star rating, and MOOP variables across 
thousands of plans. Feeds directly into LifeSync's plan recommendation logic for 
persona-matched Medicare guidance.

## Pipeline

RAND HRS Survey Data
↓
Persona_RAND.ipynb
(K-Means clustering → 3 personas)
↓
AARP_Topic_Intelligence_Pipeline.ipynb
(Trends + RSS scraping → content gaps)
↓
Cross-reference gaps to persona needs
↓
aarp_marketing_plan.ipynb          Health_plan_analysis.ipynb
(Channel & messaging strategy)     (Medicare plan matching)
↓                                   ↓
LifeSync Personalization Layer

## Tech Stack
Python, scikit-learn, pandas, numpy, sentence-transformers, 
pytrends, BeautifulSoup, matplotlib, seaborn, ipywidgets

## Data Sources
- RAND Health and Retirement Study (HRS), Wave 15 (2020)
- Pew Research Internet & Technology Survey
- CDC BRFSS prevalence rates (synthetic simulation)
- CMS Medicare Advantage Landscape & Enrollment Performance (2026)
- Google Trends (pytrends API)
- RSS feeds: Next Avenue, AARP.org

## Notes
Raw data files are excluded from this repository. Survey datasets 
require institutional access via RAND and Pew Research portals.

