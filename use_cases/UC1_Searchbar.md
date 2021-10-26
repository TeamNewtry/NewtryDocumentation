# Search products by search bar
Accessing the more detailed product information requires being able to find a specific product and access it's details. For this purpose a search bar which is able to find the product by its barcode number or product name has to be implemented.

# 1 Flow of Events
## 1.1 Basic Flow
- User clicks on "search bar" or "search" icon
- User inputs a Productname or EAN into the "search bar"
- List of products is updated live 
- Name and picture of the product is shown

### 1.1.1 Activity Diagram

### 1.1.2 Mock-up
TODO

### 1.1.3 Narrative
TODO

## 1.2 Alternative Flows
If there are no productinformations:
- User clicks on "search bar" or "search" icon
- User inputs a Productname or EAN into the "search bar"
- List of products is updated live 
- Error message "no product found" is shown

If there are mutlible products with the name ore EAN:
- User clicks on "search bar" or "search" icon
- User inputs a productname or EAN into the "search bar"
- List of products is updated live  
- A list of all found products is shown


# 2 Special Requirements
(n/a)

# 3 Preconditions
- Productinfortmations are stored in the DB
- User has the productname or EAN
# 4 Postconditions
(n/a)
 
# 5 Extension Points
(n/a)