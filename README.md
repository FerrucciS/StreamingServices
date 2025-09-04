# Cross-Platform Streaming Content Analysis  
*Netflix | Hulu | Disney+ | Amazon Prime Video*  

---

## Executive Summary  

This analysis compares the content libraries of four major streaming platforms - **Netflix, Hulu, Disney+, and Amazon Prime Video** - using publicly available datasets. The goal was to identify patterns in **content acquisition, release strategies, and catalog composition** that highlight each platform’s strategic positioning.  

### Key Insights  

- **Catalog Size & Composition**  
  - **Amazon Prime Video** hosts the largest library (~9,600 titles), dominated by movies (81%).  
  - **Netflix** follows with ~8,800 titles, also movie-heavy (70%).  
  - **Hulu** maintains a mid-sized catalog (~3,000 titles) with a unique **50/50 balance** between movies and TV shows.  
  - **Disney+** is the smallest (~1,450 titles), emphasizing a **curated, family-oriented catalog** (73% movies).  

- **Geographic Distribution**  
  - The **U.S. dominates** across all platforms.  
  - **Netflix** demonstrates notable international diversification, with strong representation from **India (~11%)** and the **UK (~7%)**, alongside a substantial share of content from a wide range of other countries (~21% outside the top 9). This breadth highlights Netflix’s deliberate global acquisition strategy and its positioning as the most internationally oriented platform among the four.  
  - **Hulu** features content from **Japan (17%)** and the **UK (10%)**, with the Japanese titles being almost entirely TV shows (~90%), predominantly **Anime**. This highlights Hulu’s selective international acquisitions and its specialization in anime content, positioning the platform as a niche provider in this segment.
  - **Disney+** remains overwhelmingly U.S.- and UK-centric, reflecting its in-house production model.  
  - **Amazon’s country data is incomplete**, but among the available records, there is a strong **India presence (~35%)** alongside the U.S. Notably, ~93% of the Indian content consists of **movies**, reflecting a significant **Bollywood catalog**, which underscores Amazon’s strategy to cater to regional film markets.
 

- **Ratings & Audience Targeting**  
  - **Disney+** is almost entirely **PG/TV-14 or below**, aligning with its **family-friendly positioning**.  
  - **Netflix and Hulu** cover the full ratings spectrum, appealing to both general and mature audiences.  
  - **Amazon** has the most **diverse ratings mix**, consistent with its aggregator model.  

- **Content Growth & Seasonality**  
  - **Disney+** bulk-uploaded its catalog in **2019**, with limited additions afterward.  
  - **Hulu** shows steady growth from 2006, with an **accelerated focus on TV shows from 2019–2021**, overtaking movies.  
  - **Netflix** experienced a surge of new content between **2016–2019**, followed by a decline — potentially due to **COVID-19 or strategic curation**.  
  - Seasonal spikes exist: **Disney+ in November** (launch timing), **Hulu in July/October**, and **Netflix in January/July/December**.  

- **Release Year of Titles**  
  - **Disney+** leverages its deep back catalog (films dating to the 1930s).  
  - **Amazon** stands out for breadth of **older films**, while **Hulu and Netflix** skew toward recent releases, with peaks around 2019–2020.  

### Strategic Takeaways  

- **Disney+**: Positions itself as a **family-first service** with a tightly curated catalog, relying on owned IP.  
- **Netflix**: Global leader with diverse international representation but slowing content growth, suggesting a **shift from scale to quality/originals**.  
- **Hulu**: Differentiates with **TV show focus** in recent years and selective non-U.S. markets (notably Japan).  
- **Amazon Prime Video**: Broad, high-volume aggregator with both the **largest library** and **widest rating spread**, making it the most generalist platform.  

Overall, the data reveals clear differences in how platforms **build, expand, and position** their libraries. While all lean heavily on the U.S. market, their **approaches to international content, ratings, and catalog growth** reflect distinct competitive strategies.  

---

## Data & Methodology  

- **Data Source**: [Kaggle – Shows Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)  
- **Columns**:  
  `['show_id', 'type', 'title', 'director', 'cast', 'country', 'date_added', 'release_year', 'rating', 'duration', 'listed_in', 'description']`  
- **Note**: `rating` refers to **content rating (PG, R, etc.)**, not user reviews.  

### Handling Missing Values  

- **Netflix**: Moderate missingness (e.g., director 30%, cast 9%). Missing `country` imputed with mode; minimal missing in `date_added` and `rating` filled with mode.  
- **Disney+**: Similar approach as Netflix.  
- **Hulu**: ~100% missing for `director`/`cast`; dropped. High missingness in `country` (47%) → filled with `"No Data"` to avoid skew.  
- **Amazon**: Severe missingness (`country` 93%, `date_added` 98%). Filled with `"No Data"`, except `rating` imputed with mode.  

---

## Results  

### Geographic Distribution of Content  
![Plot1](images/GeoDistribution.png)

- **U.S. dominates** across all platforms.  
- **Netflix** shows stronger diversification (India 11%, UK 7%).  
- **Hulu** is notable for Japan (17%) and UK (10%).  
- **Disney+** overwhelmingly U.S.-UK due to in-house Disney catalog.  
- **Amazon** indicates strong India presence (35%), though limited by missingness.  

---

### Movies vs. TV Shows Split  
![Plot2](images/MovieTVSplit.png)

- **Netflix**: 70% movies, 30% TV shows.  
- **Hulu**: Almost 50/50 split.  
- **Disney+**: 73% movies, 27% shows.  
- **Amazon**: 81% movies, 19% shows.  

Breakdowns by country show Netflix and Amazon emphasize **movies globally**, while Hulu has a **more balanced strategy**.  

---

### Content Volume & Ratings Distribution  
![Plot3](images/ContentVol.png)

- **Catalog size**:  
  - Amazon: ~9,668 titles  
  - Netflix: ~8,807 titles  
  - Hulu: ~3,073 titles  
  - Disney+: ~1,450 titles
 
 ![Plot4](images/Ratings.png)

- **Ratings**:  
  - Disney+ strictly **family-oriented** (PG/TV-14 max).  
  - Netflix & Hulu span full range.  
  - Amazon widest diversity in ratings.  

---

### Content Added Over Time  
![Plot5](images/AddedYear.png)
![Plot6](images/CumAddedYear.png)

- **Disney+**: Bulk upload in 2019 → sharp drop afterward.  
- **Hulu**: Steady growth, TV shows overtook movies post-2019.  
- **Netflix**: Surged in 2016–2019, decline after 2019.  

---

### Seasonality in Content Releases  
![Plot7](images/AddedMonth.png)
![Plot8](images/CumAddedMonth.png)

- Disney+: **November spike** (launch timing).  
- Hulu: **July & October spikes** (seasonal themes).  
- Netflix: Steady with peaks in **Jan, July, Dec**; lows in Feb/May.  

---

### Correlations in Genres  
![Plot9](images/NCorr.png)
![Plot01](images/NCorr1.png)
![Plot02](images/Hcorr.png)
![Plot03](images/Hcorr1.png)
![Plot04](images/DCorr.png)
![Plot05](images/DCorr1.png)
![Plot06](images/ACorr.png)
![Plot07](images/ACorr1.png)

- Sitcoms ↔ Comedy.  
- Docuseries ↔ negative with Kids/Comedy.  
- Action ↔ Thriller; Animation ↔ Kids.  

---

### Release Year of Titles  
![Plot17](images/Release.png)

- Disney+: Deep catalog back to **1930s**.  
- Amazon: Largest share of **older films**.  
- Netflix & Hulu: Skewed toward **recent content**, peaking ~2019–2020.  
- Hulu: TV shows emphasized in recent years.  

---

## Recommendations for Further Analysis  

To strengthen insights, future work could include:  

- **Subscriber and engagement data**: Linking content trends to user growth/retention.  
- **Originals vs. licensed content**: Identifying how much of each catalog is exclusive.  
- **Genre-level performance**: Mapping library mix to audience preferences per region.  
- **Cross-platform overlap**: Measuring how much content is shared vs. exclusive.  

---

## Conclusion  

This analysis highlights that while all four platforms draw heavily from U.S. content, they pursue **distinct strategies**:  

- Disney+ → tightly curated, family-first.  
- Netflix → global diversification, now shifting to quality.  
- Hulu → recent pivot to TV shows, selective international focus.  
- Amazon → largest, most generalist library with wide rating and age spread.  

These differences shape how platforms compete for subscribers, balance global reach with local content, and respond to industry shifts.  
