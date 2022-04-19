# Submit comment
Users can provide their rating with a comment to explain it to other users. 
# 1 Flow of Events
## 1.1 Basic Flow
- user opens product page of a specific product ([search bar](./UC1_Searchbar.md)/[barcode](./UC4_Scanner.md))
- user clicks on the desired amount of stars
- user enters a comment
- user clicks on the checkmark to submit his comment
- comment is saved to the database

### 1.1.1 Activity Diagram
![Activity Diagram](../resources/UC9_SubmitComment.drawio.svg)

### 1.1.2 Mock-up
![Ingredients Screenshot](../resources/Ingredients_ratings.PNG)

### 1.1.3 Narrative
(n/a)

## 1.2 Alternative Flows
The comment contains inadmissible content:
- user opens product page of a specific product ([search bar](./UC1_Searchbar.md)/[barcode](./UC4_Scanner.md))
- user clicks on the desired amount of stars
- user enters a inadmissible comment
- the user submits his rating
- the user gets an error message which tells him to alter his comments content

# 2 Special Requirements
(n/a)

# 3 Preconditions
- user knows which specific product he wants to rate and comment
- the user is logged in

# 4 Postconditions
(n/a)

# 5 Extension Points
(n/a)
