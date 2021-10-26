# Show nutritional values
This feature is closely related to [Show ingredients](./UC2_Ingredients.md). Just as ingredients, the nutritional values of a product are fundamental when deciding on buying it. Nutrients listed here should not only be limited to what is shown on the product and thus *may* include additional nutritional values.

Basic key figures are:
- Calorific Value
- Total Fat
    - Saturated Fat
- Total Carbohydrates
    - Fibre
    - Sugars
- Protein
- Salt

# 1. Flow of Events
## 1.1 Basic Flow
- user opens product page of a specific product ([search bar](./UC1_Searchbar.md)/[barcode](./UC4_Scanner.md))
- information is fetched from the database
- information is shown in dedicated section of product page

### 1.1.1 Activity Diagram
TODO

### 1.1.2 Mock-up
TODO

### 1.1.3 Narrative
TODO

## 1.2 Alternative Flows
If no information for a specific product is present:
- user opens product page of a specific product ([search bar](./UC1_Searchbar.md)/[barcode](./UC4_Scanner.md))
- information is fetched from the database
- error message "no information for nutritional values found" is shown

# 2. Special Requirements
(n/a)

# 3. Preconditions
- user knows which specific product he wants to know the nutritional values of
- the product is present in the database

# 4. Postconditions
(n/a)
 
# 5. Extension Points
(n/a)