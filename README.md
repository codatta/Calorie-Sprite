# Calorie-Sprite

## 1. Product Overview
- Product Name: Calorie Sprite
- Product Positioning: A health app that identifies food and tracks its calorie content and other information through photos.
- Product Diagram:
<div align="center">
  <img src="https://github.com/user-attachments/assets/7cf11175-d108-44b5-9619-bc7e53ca0aea" alt="diagram_image" width="20%">
</div>

- Target Users: Individuals focused on healthy eating, fitness, and weight management.
- User Needs: Easily understand the health status of their diet.
- Core Functions:
  - Photo Recognition of Food (p0): Users can take photos of food with their mobile phones to recognize the name of the food, cooking method, estimated weight, etc.
  - Food Nutritional Analysis (p1): Accurately analyze the nutritional content of food, calorie content, and identify potential allergens or unsuitable demographics.
  - Search for Target Food (p2): Users can search for food suitable for specific demographics or healthier food options (e.g., “low-sodium chicken breast”).
  - Dietary Structure Analysis (p3): Based on the user’s long-term dietary records, analyze the health status of their diet and provide optimization suggestions.
- Technical Route:
  - Utilize LLM + real data collected by ourselves to train a specialized large model in the food domain.

## 2. Demand Research
- Research on Similar Products:
  - Foodvisor - This app uses photo-based tracking to provide instant nutritional analysis of meals snapped by the user’s camera, making it simple to log meals and track dietary intake.
  - Calorimate - Offers AI nutrition analysis and calorie-free meal tracking, focusing on providing effortless calorie calculations for both recipes and meals.
  - Lifesum - A comprehensive food tracking app that offers free and premium versions, with features like meal plans and daily scores to help users track their progress.
  - MacrosAI - Allows users to track calories using images, simple meal descriptions, or a barcode scanner, aiming to simplify calorie estimation, especially in places like restaurants.
  - Calorik - An AI-powered nutrition supertracker that promises to end the hassle of manual calorie counting by using advanced AI to predict calories and macros even without full ingredient lists.
  - Calo AI - Not only counts calories but also tracks exercise and overall health, integrating seamlessly with popular apps like MyFitnessPal to support users’ fitness journeys.
- Research Findings:
  - There are many apps related to healthy eating.
  - With the emergence of LLMs, there has been a rapid increase in healthy eating apps based on LLMs over the past year.
  - The current apps all have issues with accuracy in their results.

## 3. Technical Feasibility Study
### 3.1 Research Findings
- The current capability of LLMs has already achieved a fairly decent baseline standard.
- The existing food datasets provide limited supplementation to the LLM; we need more effective data.
- We will utilize the Codatta platform to collect more effective data.
### 3.2 Current State of Food Recognition Capabilities Based on Existing LLM
- promot：
As a dietary expert, you are capable of helping me assess the caloric intake and the intake of fats, carbohydrates, and proteins in my daily diet. I will provide you with actual photographs of the food, and you will perform an accurate assessment, including an explanation of the calculation process.
Next, I will provide you with pictures of the food, and you need to produce a table that includes the identified food name, cooking method, estimated weight, and estimated nutrients (including fats, proteins, carbohydrates, sodium, and calories), and provide cumulative results.
- Input: Food image
- Model Performance:
  - The biggest advantages of Claude 3.5 are twofold: 1) Consideration of cooking methods; 2) Estimation of weight (other models generally estimate based on common scenarios with less reference to image information).
  - Current issues with the large model include: 1) Difficulty in accurately identifying some foods (e.g., chive pockets, luncheon meat cooked in hot pot); 2) Difficulty in accurately recognizing the weight of the food.
![image](https://github.com/user-attachments/assets/70fc8e77-f489-41c4-b429-905d5be36072)

### 3.3 Existing Food Datasets
The existing publicly available food-related datasets primarily focus on foods in their raw state or standardized packaged products. Data on homemade foods commonly prepared by the general public is very rare.
The following are food datasets provided through crowdsourcing methods that were found:
- https://world.openfoodfacts.org/ 
  - This platform relies on user-contributed uploads and annotations of food information, containing 3.52 million entries (some duplicates) of food images and annotated data (nutritional content, origin, sales region, health certifications, etc.).
  - However, the data mainly consists of standardized food products (packaged foods or items from chain restaurants like KFC), and homemade foods are not included.
### 3.4 Our Data Collection Plan
- https://codatta.io/: This is a Web3-based platform for data annotation and assetization, with over 200,000 users from around the world.

## 4. Project Plan
- Phase One: Feasibility Study
  - Business Feasibility Study
  - Technical Feasibility Study
- Phase Two: MVP Product Implementation
  - Implementation of a domain-specific large model based on the existing LLM + a small amount of annotated data
  - MVP product launch based on an X (formerly Twitter) Bot
- Phase Three: Beta Product Implementation
  - Collecting a large amount of food annotation data via Codatta
  - Developing a high-quality domain-specific large model through fine-tuning the LLM
  - Design and development of a multi-entry product
- Phase Four: Official Product Launch and Operation
  - Designing and developing a product with comprehensive capabilities and user-friendly interactions
  - Operating the product to attract more users
