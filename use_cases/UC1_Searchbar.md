# Search products by search bar
Accessing the more detailed product information requires being able to find a specific product and access it's details. For this purpose a search bar which is able to find the product by its barcode number or product name has to be implemented.

# 1 Flow of Events
## 1.1 Basic Flow
- user clicks on "search bar"
- user inputs a product name or EAN into the "search bar"
- list of products is updated on-the-fly
    - every result contains name and picture of the product
- user clicks on a specific product which opens the detailed product page

### 1.1.1 Activity Diagram

### 1.1.2 Mock-up
TODO

### 1.1.3 Narrative
TODO

## 1.2 Alternative Flows
If there are no products that fit the search term:
- user clicks on "search bar"
- user inputs a product name or EAN into the "search bar"
- list of products is updated on-the-fly
- error message "no product found" is shown

If there are multiple products with a matching name or EAN:
- user clicks on "search bar"
- user inputs a product name or EAN into the "search bar"
- list of products is updated on-the-fly 
- a list of all found products is shown


# 2 Special Requirements
(n/a)

# 3 Preconditions
- the product is present in the database
- user has the product name or EAN

# 4 Postconditions
(n/a)
 
# 5 Extension Points
(n/a)