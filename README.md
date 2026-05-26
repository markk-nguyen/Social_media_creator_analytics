# Data-Driven Strategy for Launching a Music Creator Channel
  Social Media Creator Analytics Pipeline

I built this project to answer one question: if I were launching a DJ and music creation channel on TikTok or YouTube Shorts, what does the data actually tell me about how to grow from day one? How can I use existing data to drive decisions that will grow my personal brand and business short term and long term?

## Live Dashboard
[View on Tableau Public](https://public.tableau.com/app/profile/mark.nguyen4226/viz/Social_Media_Project_17796914960500/Story1)

## Tech Stack
| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data cleaning and statistical validation |
| PostgreSQL (Supabase) | Cloud database for storing and querying cleaned data |
| SQL | Queries across platforms, genres, creator tiers, traffic sources, and video duration |
| Tableau | Interactive dashboards |
| Google Colab | Development environment |

## Dataset
48,079 real TikTok and YouTube Shorts videos from Kaggle covering 14 content genres across multiple regions in 2025.

**Source:** [YouTube Shorts and TikTok Trends 2025](https://www.kaggle.com/datasets/tarekmasryo/youtube-shorts-and-tiktok-trends-2025)

## What I Built
1. Cleaned and transformed the raw dataset using Python and Pandas. Removed low quality columns, fixed inconsistencies, and reclassified creator tiers into four segments based on average view counts.
2. Loaded the cleaned data into a PostgreSQL database hosted on Supabase so it could be queried from anywhere.
3. Wrote SQL queries to dig into engagement patterns across platforms, genres, creator tiers, traffic sources, and video duration.
4. Ran statistical tests to make sure the findings were reliable before drawing conclusions.
5. Built two Tableau dashboards to tell the story visually and make the findings easy to understand for anyone.

## What is Engagement Rate?
Before jumping into the findings, engagement rate is the main metric used throughout this project.

**Engagement Rate = (Likes + Comments + Shares + Saves) / Views**

It measures how actively viewers interact with content. A higher rate means the audience is doing something like liking, commenting, or sharing, not just passively watching. It is a better measure than raw view count because it accounts for video size. A small video with a high engagement rate is often more valuable than a large video where most people just scroll past.

## Statistical Validation
I did not just compare averages. I ran additional tests to make sure the findings were reliable before drawing conclusions.

**Two-sample t-test** checks whether the difference between two group averages is real or just random chance in the data. Think of it like asking: if I ran this analysis on a different sample of videos, would I get the same result?

**Confidence interval** gives a range where the true average likely falls. Instead of saying TikTok averages exactly 9.18%, it says TikTok's true average is somewhere between 9.15% and 9.21% with 95% certainty.

**Standard deviation and median check** confirms the averages are not being distorted by a few extreme outliers. If the median and mean are close together the average is trustworthy.

Results:
- The probability the TikTok vs YouTube difference is random chance is essentially zero
- TikTok's true engagement rate falls between 9.15% and 9.21% with 95% confidence
- YouTube's true engagement rate falls between 5.07% and 5.11% with 95% confidence
- These ranges do not overlap, so the gap is confirmed
- Median and mean were within 3 to 4 percent of each other for both platforms

**Conclusion: TikTok's engagement advantage over YouTube Shorts is statistically confirmed. It is not a quirk of this dataset. It is a real and consistent difference.**

## What the Data Says

**Platform**
TikTok averages 9.18% engagement vs YouTube Shorts at 5.09%. That is nearly double. The gap is consistent across every single genre and there is no content type where YouTube closes the difference.

**Traffic Source**
How viewers find your content does not significantly affect engagement within each platform. TikTok sources all cluster around 9.1% and YouTube sources all cluster around 5.1% regardless of whether someone found the video through search, the For You page, or their following feed. Platform choice matters far more than discovery method.

**Best Time to Post**
Engagement peaks at 3 AM and 7 AM across both platforms. The 3 AM peak has a smaller sample size so 7 AM is the more reliable recommendation for a consistent posting schedule.

**Video Duration**
Shorter videos drive more engagement and more watch-through. Videos under 15 seconds averaged 8.63% engagement and a 65.84% completion rate. Videos over 45 seconds dropped to 6.64% engagement and 61.37% completion. Every time video length increases both metrics drop consistently.

**Genre**
Music ranks 11th out of 14 genres by engagement rate. Dance ranks 4th. Comedy and Education rank 1st and 2nd. For a DJ channel this suggests incorporating visual movement and educational elements like teaching music production or explaining a DJ technique could significantly boost engagement beyond pure performance content.

**Creator Tier**
Emerging creators with under 75,000 average views slightly outperform established creators on engagement rate. While follower count matters for reach, the algorithm rewards content quality regardless of account size.

## What This Means
Start on TikTok. Keep videos under 15 seconds. Post at 7 AM for consistency or 3 AM if you want to experiment. Add visual dance or educational elements to music content. Focus on making content worth engaging with because follower count does not determine early success, content quality does.

## Why This Project Transfers to Other Industries
The metrics and methods used here are not unique to social media. They show up in almost every analytics role.

Engagement rate is the same concept as conversion rate or campaign performance. How many people who saw something actually did something with it? Every marketing team measures this.

Completion rate is retention in disguise. Whether someone finishes a video or cancels a subscription is the same underlying question. Did we keep their attention long enough?

Creator tier segmentation is customer segmentation. Small, mid, enterprise. Emerging, growing, established. Different labels, same analytical framework.

Traffic source analysis is marketing attribution. Which channel brought the most engaged audience? Companies spend millions trying to answer that question across every industry.

## Limitations
- This is a sample dataset and may not represent every creator on each platform
- Traffic source labels differ between TikTok and YouTube so direct cross-platform comparison is not possible
- TikTok's engagement advantage may be structural. It is a single format platform with a more intentionally engaged audience compared to YouTube which serves long form video, live streaming, music, and Shorts all at once
- The 2 AM and 3 AM posting time findings are based on smaller sample sizes and should be interpreted with caution

## What's Next
- A/B test peak vs off-peak posting for music content specifically to confirm the timing finding with statistical significance
- Test whether combining Music and Dance genre elements drives higher engagement than either genre alone
- Add Claude API integration to automatically generate plain-English strategy briefs from SQL query outputs

## Status
Tableau dashboards live publicly. SQL analysis complete. Phase 2 in planning.
