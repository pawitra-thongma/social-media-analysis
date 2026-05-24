# Social Media Engagement Analysis
> Analyzing 1,000 posts across 5 platforms to uncover what drives engagement — using SQL queries and Python visualization.

---

## Overview

This project investigates social media engagement patterns using a synthetic dataset built from published industry benchmarks (Buffer, Rival IQ 2024–2025). The goal is to identify actionable strategies for maximizing content performance across platforms.

---

## Data Source

| Detail | Info |
|---|---|
| Dataset type | Synthetic — generated from published benchmarks |
| Based on | Buffer State of Social Media 2024–2025 (52M+ posts analyzed) |
| Also referenced | Rival IQ 2024 Benchmark Report, Hootsuite 2025 |
| Size | 1,000 posts × 11 features |
| Platforms covered | Instagram, TikTok, LinkedIn, Facebook, Twitter |

**Platform baselines used:**

| Platform | Benchmark Engagement Rate |
|---|---|
| LinkedIn | 6.50% (Buffer, 2024–2025) |
| TikTok | 2.01% (Rival IQ, 2024) |
| Instagram | 1.16% (Buffer, Jan 2025) |
| Facebook | 0.50% (industry average) |
| Twitter/X | 0.12% (Buffer, 2025) |

---

## Project Structure

```
social-media-analysis/
├── data/
│   ├── social_media_data.csv
│   └── social_media.db
├── notebooks/
│   └── analysis.ipynb
├── images/
│   ├── chart1_platform.png
│   ├── chart2_content_type.png
│   ├── chart3_heatmap.png
│   └── chart4_hashtag.png
├── docs/
│   └── analysis_bpmn.png
├── README.md
└── requirements.txt
```

---

## SQL Analysis

All initial analysis was performed using **SQLite** queries before visualization:

```sql
-- Engagement rate by platform
SELECT platform,
       COUNT(*) as total_posts,
       ROUND(AVG(engagement_rate) * 100, 2) as avg_engagement_pct
FROM posts
GROUP BY platform
ORDER BY avg_engagement_pct DESC
```

---

## Key Results

### Platform Engagement
![Platform Chart](https://raw.githubusercontent.com/pawitra-thongma/social-media-analysis/main/chart1_platform.png)

| Platform | Avg Engagement Rate |
|---|---|
| LinkedIn | 8.11% |
| TikTok | 2.57% |
| Instagram | 1.50% |
| Facebook | 0.68% |
| Twitter | 0.16% |

### Content Type Performance
![Content Type Chart](https://raw.githubusercontent.com/pawitra-thongma/social-media-analysis/main/chart2_content_type.png)

| Content Type | Avg Engagement Rate |
|---|---|
| Video | 3.41% |
| Carousel | 2.82% |
| Image | 2.46% |
| Text | 1.85% |

### Best Time to Post (Heatmap)
![Heatmap](https://raw.githubusercontent.com/pawitra-thongma/social-media-analysis/main/chart3_heatmap.png)

### Hashtag Optimization
![Hashtag Chart](https://raw.githubusercontent.com/pawitra-thongma/social-media-analysis/main/chart4_hashtag.png)

---

## Key Insights

**📱 Platform**
- LinkedIn leads with 8.11% engagement — over 50x higher than Twitter
- TikTok is best for B2C brands needing wide reach
- Instagram has high volume but lower engagement per post

**🎬 Content Type**
- Video outperforms Text by 1.84x across all platforms
- Carousel performs especially well on LinkedIn and Instagram
- Text-only posts consistently underperform

**📅 Timing**
- **Best day:** Tuesday (3.53% avg engagement)
- **Best hours:** 18:00–21:00 based on heatmap analysis
- Sunday shows lowest engagement — avoid for important posts

**#️⃣ Hashtags**
- Sweet spot: **6–15 hashtags** for optimal engagement
- 26+ hashtags reduces performance — perceived as spammy
- No hashtags = lowest engagement across all platforms

---

## Analysis Workflow

The analysis followed a structured BA-style workflow:

**Define Questions → Collect Data → SQL Analysis → Python Visualization → Insight Generation → Business Recommendation**

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square)

---

## References

- Buffer. (2025). *State of Social Media Engagement 2024–2025*. https://buffer.com/resources/average-engagement-rate/
- Rival IQ. (2024). *Social Media Industry Benchmark Report 2024*.
- Hootsuite. (2025). *Average Engagement Rates by Industry, January 2025*.
