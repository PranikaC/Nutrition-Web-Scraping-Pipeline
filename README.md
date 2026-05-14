# Meal Plan Webscraping and Nutrition Comparison

This project scrapes weekly meal plans from Tastes Better From Scratch, matches the meals with recipe data from the Tasty API, and compares the meals using nutrition and cooking time information.

## Project Goal

The goal of this project is to turn a weekly meal plan into a more useful nutrition comparison. The notebook collects meal names, prices, recipe links, cook times, ingredients, calories, protein, carbs, and fat. It then uses this information to compare meals and meal plans.

## Files

README.md

Project overview and instructions.

Webscraping_Meals.ipynb

Main notebook for scraping, matching recipes, cleaning the data, making graphs, and comparing meal plans.

## What The Notebook Does

The notebook first imports the packages needed for webscraping, data cleaning, fuzzy matching, and plotting.

It then scrapes a weekly meal plan page from Tastes Better From Scratch. The scraped table includes the day of the week, recipe name, recipe link, and price.

Next, the notebook uses the Tasty API to search for similar recipes. Since recipe names do not always match exactly, fuzzy matching is used to find close recipe matches.

The matched recipes are used to add more details, including cook time, number of ingredients, meal type, calories, protein, carbs, and fat.

The notebook then cleans the data by removing rows with missing recipe or nutrition values. This keeps the final tables and graphs focused on recipes that can actually be compared.

After cleaning, the notebook labels meals as vegetarian or non vegetarian based on words in the meal name.

Finally, the notebook creates graphs and a final comparison table to compare Meal Plan 111 and Meal Plan 202.

## Main Functions

get_weekly_plan(plan_number)

Scrapes a meal plan page from Tastes Better From Scratch.

match_recipe(df_week)

Searches the Tasty API for matching recipes and adds nutrition and cooking details.

get_mealplan_data(meal_num)

Combines the scraping step and the recipe matching step into one function.

## Graphs

The calorie graph compares calories for vegetarian and non vegetarian meals in Meal Plan 202.

The protein and carbohydrate graph compares protein and carbs for each meal in Meal Plan 202.

These graphs help show that vegetarian meals are not always lower in calories and that meals like Chicken Gyros and Beef Noodle Soup can be stronger protein options.

## Final Comparison

The final comparison looks at Meal Plan 111 and Meal Plan 202.

Meal Plan 111 is generally more balanced in the cleaned results because it has lower average calories and carbs while still having slightly higher average protein.

Meal Plan 202 has more variety and includes strong protein options like Chicken Gyros and Beef Noodle Soup, but some meals are heavier in calories and carbs.

## How To Run

Open the notebook in Jupyter Notebook, JupyterLab, Google Colab, or VS Code.

Install the needed packages if they are missing.

```python
import sys
!{sys.executable} -m pip install rapidfuzz plotnine -q
```

Run the notebook from top to bottom.

The notebook uses live websites and APIs, so results may change if the websites update or if the API returns different matches.

## Notes

This project uses webscraping and API data, so the results depend on the current structure of the websites and the available API responses.



