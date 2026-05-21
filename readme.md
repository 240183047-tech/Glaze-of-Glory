# 🍳 Recipe Website Analysis & ML Models (eda.rambler.ru)

This project focuses on the end-to-end data pipeline, including web scraping, Exploratory Data Analysis (EDA), hypothesis testing, and Machine Learning. The goal was to analyze user engagement, recipe characteristics, and build predictive models based on data extracted from the popular recipe platform *eda.rambler.ru*.

---

## 👥 Team: Glaze of Glory
* **Dana Beisbayeva**
* **Akmeiir Amirseit**
* **Fazilat Kholmirzayeva**
* **Feruza Shamshimetova**

---

## 🛠 Tech Stack & Tools
* **Programming Language:** Python
* **Data Collection (Scraping):** Requests, BeautifulSoup (extracting hidden JSON from HTML webpage source)
* **Data Processing & Analysis:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn (`df.explode()` for granular ingredient analysis)
* **Machine Learning:** Regression models for calorie estimation & Semantic Search using `SentenceTransformer`.

---

## 📊 Repository Structure
* `Glaze_of_glory_code.ipynb` — Interactive Jupyter Notebook containing the full data workflow: scraping, cleaning, feature engineering, visualizations, and ML models.
* `Glaze_of_glory_report.docx` — Comprehensive analytical report detailing our methodology, statistical tests, and business insights.
* `Glaze_of_glory_presentation.pdf` *(White Gray Modern...)* — Stakeholder-ready business presentation summarizing the project.

---

## 📈 Key Findings & Workflow Stages

### 1. Data Collection & Preprocessing
* Successfully scraped over **10,000 rows and 15 features** (nutritional values, cuisine, user likes/dislikes). 
* **Data Quality:** Achieved 0% null values after robust cleaning.
* **Feature Engineering:** Developed advanced metrics including `Likes Ratio` (user satisfaction index), `Calories per Portion`, `Dietary Focus`, `Time Effort`, and extracted `Dish Type` from recipe URLs.

### 2. Exploratory Data Analysis (EDA) Insights
* **The "Quick & Healthy" Paradox:** The data disproves the myth that healthy eating is time-consuming. Low-calorie or high-protein meals are statistically faster to prepare than high-carb/high-fat options.
* **The Complexity Ceiling (The 8-Ingredient Rule):** Recipe popularity peaks at roughly 8 ingredients. Beyond this point, user engagement drops sharply due to the perceived "cognitive load" of complex recipes.
* **Punchy Titles Perform Better:** Recipes with short, concise names (e.g., "Brownies") achieve higher virality and saves compared to long, overly descriptive titles (e.g., "Homemade syrniki made from farm-style cottage cheese").
* **Controversial Categories:** Breakfasts and drinks emerged as the most polarizing dish types, yielding the highest 'Dislikes per Like' ratios. Simple categories trigger higher expectations regarding quality.

### 3. Statistical Hypothesis Testing
* **Hypothesis 1 (Cuisine Popularity):** Italian cuisine is statistically more popular than Russian cuisine within this dataset. Italian recipes receive roughly 36% more user engagement ($p\text{-value} = 0.014$).
* **Hypothesis 2 (The Guilty Pleasure Effect):** High-calorie/indulgent meals receive significantly more love (27% more likes on average) than healthy, low-calorie alternatives ($p\text{-value} = 0.003$). People search for health but like comfort food.
* **Hypothesis 3 (Diet vs. Complexity):** We confirmed a positive correlation between carbohydrate density and the number of ingredients. Lower-carb recipes generally feature minimalist structures, making them simpler to prepare ($p\text{-value} < 0.05$).

### 4. Machine Learning Models
* **Calorie Prediction:** Built a highly reliable regression model to estimate total calories using macronutrients (Fat, Protein, Carbs). The model achieved an outstanding **$R^2 = 0.96$** with an RMSE of just 55.60 kcal. Fat content was identified as the primary predictor (69.17% importance).
* **Semantic Search (Advanced ML):** Implemented a context-based search engine using vector embeddings. This phase highlighted a dataset bias—uncovering that technical precision cannot override data composition, as healthy food queries occasionally returned beverage results due to a high density of drink-related texts.

---

## 💡 Strategic Recommendations

### For Content Creators & Chefs
1. **Optimize Recipe Length:** Stick to the "8-ingredient rule" to maximize user saving rates. If a dish requires more, visually separate it into sub-steps.
2. **Rebrand Healthy Options:** Use sensory and indulgent language for nutritious dishes (e.g., rebrand "Low-Calorie Chicken" to "Tuscan-Style Lean Chicken") to boost click-through rates.

### For Platform Developers (eda.rambler.ru or similar)
1. **Automated Tagging:** Integrate the Calorie Prediction model ($R^2=0.96$) to automatically calculate and display missing nutritional data for user-submitted recipes.
2. **Search Guardrails:** Implement category-specific constraints for the Semantic Search model to prevent cross-category mismatching (e.g., blocking alcohol results for breakfast queries).
3. **Smart Personalization:** Push time-efficient "Quick & Healthy" recipes during busy weekdays, while reserving indulgent Italian/High-Calorie recommendations for "weekend treats."
