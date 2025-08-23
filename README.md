# Car Price Predictor

This project helps you check whether a car listed on **PakWheels** is **fairly priced** or **undervalued**.  

It works in three steps:  
1. **Scrape data** from PakWheels ads.  
2. **Train a machine learning model** on the scraped data to estimate fair car prices.  
3. **Predict** the expected price of all cars in the dataset (or a single car ad).  

---

## 1. Web Scraping

Notebook: `PakWheels_webscraper.ipynb`  

- Open the notebook and paste the **PakWheels search URL** (e.g. all Suzuki Mehran ads in Islamabad).  
- The scraper will:  
  - Visit each ad on the search results page.  
  - Collect details (price, mileage, year, etc.).  
  - Save everything into a **CSV file** inside the `data/` folder.  
- You can change:  
  - How many ads to scrape.  
  - Output filename.  

---

## 2. Get Results from Complete Data

Notebook: `Data_analysis,_model_training_&_results.ipynb`  

- Load the CSV file from the scraper.  
- The notebook will:  
  - Clean and preprocess the data.  
  - Train a **Random Forest model** to estimate car prices.  
  - Save the trained model in the `models/` folder.  
  - Generate a **results CSV** in the `results/` folder, sorted by which cars are **listed most below their predicted price**.  

This helps you quickly see which ads are the **best deals**.  

---

## 3. Get Result for One Ad

Notebook: `Single_Car_Price_Predictor.ipynb`  

- Use this if you only want to check the price of a **single car ad**.  
- You need:  
  - A trained model (from step 2).  
  - The brand and model of the car.  
- The notebook will load the model and give the **predicted fair price** for that car.  

👉 Tip: Works best when you train the model on **one car type** (e.g. only Suzuki Mehran).  
- To train on all cars together, set `use_all_data = True`.  

---

## Example Data and Models

- Sample datasets and models for **Suzuki Mehran** and **Toyo**
