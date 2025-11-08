# 📊 Zomato Menu Item Data Analysis

## 📝 Introduction

This project performs a comprehensive analysis of a Zomato dataset, focusing on menu items, restaurant performance, and market trends across 6 major Indian cities. The dataset provides granular data at the individual menu item level, allowing for deep insights into pricing, popularity, and customer ratings.

The primary goal of this analysis is to identify strategic opportunities for restaurants by answering three core questions:

1.  **Winning Cuisine Analysis:** Which cuisines have high ratings and high demand, but low competition?
2.  **Market/Location Analysis:** Which city or neighborhood offers the best potential for growth (high engagement, high ratings, and low competition)?
3.  **Service Model Analysis:** Should a restaurant focus on a delivery-first or dine-in-first model, and how does this vary by cuisine?

## 🛠️ Tech Stack & Libraries Used

* **Python**
* **Pandas:** For data manipulation and aggregation.
* **NumPy:** For numerical operations.
* **Matplotlib & Seaborn:** For data visualization.
* **SciPy:** For statistical analysis (t-tests).

## 🗂️ Dataset

The dataset used is `Zomato Dataset.csv`, which contains **57,421** records (menu items) and **26** features.

### Data Dictionary

| Column Name | Description |
| :--- | :--- |
| `Restaurant_Name` | Name of the restaurant listed on Zomato. |
| `Dining_Rating` | User rating for the dine-in experience (0.0 to 5.0). |
| `Delivery_Rating` | User rating for the delivery experience (0.0 to 5.0). |
| `Dining_Votes` | Number of votes received for dine-in service. |
| `Delivery_Votes` | Number of votes received for delivery service. |
| `Cuisine` | Type of cuisine served (e.g., Fast Food, Chinese). |
| `Place_Name` | Local area or neighborhood of the restaurant. |
| `City` | City in which the restaurant is located. |
| `Item_Name` | Name of the menu item listed. |
| `Best_Seller` | Bestseller status (e.g., BESTSELLER, MUST TRY, NONE). |
| `Votes` | Combined total votes received. |
| `Prices` | Price of the menu item in INR. |
| `Average_Rating` | Mean rating calculated from available sources. |
| `Total_Votes` | Sum of all types of votes. |
| `Price_per_Vote` | Ratio of price to total votes (used to evaluate value for money). |
| `Log_Price` | Log-transformed price to reduce skewness in analysis. |
| `Is_Bestseller` | Binary flag indicating if item is marked as a bestseller. |
| `Restaurant_Popularity`| Number of items listed by the restaurant in the dataset. |
| `Avg_Rating_Restaurant`| Average rating of all items from the same restaurant. |
| `Avg_Price_Restaurant`| Average price of all items from the same restaurant. |
| `Avg_Rating_Cuisine` | Average rating across all restaurants serving the same cuisine. |
| `Avg_Price_Cuisine` | Average price across all restaurants serving the same cuisine. |
| `Avg_Rating_City` | Average rating across all restaurants in the same city. |
| `Avg_Price_City` | Average price of menu items in the same city. |
| `Is_Highly_Rated` | Binary flag for ratings ≥ 4.0. |
| `Is_Expensive` | Binary flag for prices above city’s average. |

---

## 📈 Key Analysis & Insights

The analysis was structured around the three core questions, leading to the following insights:

### 1. Cuisine Analysis (The Next Winning Cuisine)

* **Market Saturation:** The market is heavily dominated by a few cuisine types. `Beverages` (22k items), `Desserts` (5.5k), and `Fast Food` (5.2k) are the most common, indicating high saturation.
* **High-Potential, Low-Competition:** Cuisines like **`Seafood`**, **`Bakery`**, **`Mexican`**, **`Salad`**, and **`Tibetan`** show very high average ratings (often > 4.0) but have a significantly lower number of items. This signals a potential market gap for new, high-quality restaurants in these categories.
* **Price-Rating Matrix:**
    * **High-Cost, High-Rating:** `Lucknowi`, `Kebab`, and `Continental` are high-investment, high-return cuisines.
    * **Low-Cost, High-Rating:** `Bakery` and `Healthy Food` show high average ratings with more accessible price points.

### 2. Market & Location Analysis (Best City/Location)

* **City-Level Performance:** The analysis covers 6 cities: Hyderabad, Mumbai, Chennai, Jaipur, Pune, and Kochi.
* **Mature Market (Hyderabad):** Hyderabad demonstrates the highest average rating (~3.94) and the most total votes. It also has the highest number of restaurants, making it a mature and competitive, yet high-performing, market.
* **Growth Market (Kochi):** Kochi has a strong average rating (~3.89) but by far the lowest number of total restaurants. This suggests it is an **underserved market** with high user satisfaction and significant potential for growth.
* **Neighborhood Popularity:** At a more local level, neighborhoods like `C Scheme` (Jaipur) and `Chembur` (Mumbai) are highly popular and saturated. In contrast, areas like `Deccan Gymkhana` (Pune) have very few listings, indicating an emerging market.

### 3. Service Model (Dine-in vs. Delivery)

* **Ratings are Independent:** A statistical t-test confirmed a **significant difference** between `Dining_Rating` and `Delivery_Rating` (p-value < 0.05).
* **Votes are Independent:** There is only a weak positive correlation (`0.22`) between dining and delivery ratings, and a weak **negative correlation (`-0.24`)** between dining and delivery *votes*. This strongly implies that customers rate and engage with these two service types independently; success in one does not guarantee success in the other.
* **Cuisine-Specific Strategy:**
    * **Dine-in Focus:** Cuisines like `Mandi` and `Seafood` show significantly higher average *Dining Votes*, suggesting customers prefer an in-restaurant experience for these foods.
    * **Delivery Focus:** Cuisines like `Sichuan`, `Biryani`, and `Pizza` receive a much higher volume of *Delivery Votes*, making them ideal for a delivery-first or cloud-kitchen model.

## 🎨 Key Visualizations

The analysis used several visualizations to uncover these insights:

1.  **Count of Restaurants by Cuisine (Bar Chart):** Showed the heavy saturation of `Beverages` and `Fast Food`.
2.  **Heatmap of Average Rating and Average Price per Cuisine:** Was used to identify high-potential cuisines by cross-referencing ratings and price.
3.  **Bubble Chart of Cuisine Metrics:** Combined `Avg Rating`, `Avg Price`, and `Total Votes` to provide a holistic view of the cuisine landscape.
4.  **Total vs. Highly Rated Restaurants by City (Stacked Bar Chart):** Revealed the market saturation in Hyderabad versus the untapped potential in Kochi.
5.  **Comparison of Average Price and Average Rating by City (Combined Bar/Line Chart):** Showcased how different cities balance price and quality.
6.  **Average Dining vs. Delivery Votes by Cuisine (Stacked Bar Chart):** Clearly demonstrated the different customer engagement patterns for dine-in vs. delivery across cuisines.

## 🏁 Conclusion

This analysis provides actionable, data-driven strategies for restaurant owners and market entrants:

1.  **Avoid Saturated Markets:** Instead of competing in oversaturated markets like `Beverages` or `Fast Food`, focus on niche, high-rating cuisines such as **`Seafood`**, **`Bakery`**, or **`Mexican`**.
2.  **Target Growth Cities:** While Hyderabad is a high-performing market, it is also highly competitive. **Kochi** represents a significant, high-potential, unsaturated market for new restaurant entry.
3.  **Optimize Service Model:** The choice of dine-in vs. delivery is not one-size-fits-all. The strategy must be **cuisine-dependent**. Use data to decide whether to invest in a cloud kitchen (for `Biryani`, `Sichuan`) or a premium dine-in experience (for `Mandi`, `Seafood`).




# 📁 Repository Structure

README.md (This file)

Zomato Dataset.csv (The raw dataset used for the challenge)

zomato_dataset_data_description.xlsx (The raw dataset used for the challenge)

ZOMATO-DATA.ipynb (The main Jupyter Notebook with all my code and analysis)

Exploring-the-Zomato-Restaurant-Dataset.pptx (A summary of my findings and recommendations)



## 🚀 How to Run this Project

1.  Clone the repository:
    ```bash
    git clone [YOUR_REPOSITORY_LINK]
    ```
2.  Navigate to the project directory:
    ```bash
    cd zomato-analysis-project
    ```
3.  Install the required dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scipy
    ```
4.  Open the Jupyter Notebook (`.ipynb`) or run the Python script to view the full analysis.
