# Scan barcode
To ease the use of the app and make it more appealing to the user it should be possible to just scan the barcode of a product instead of having to use the search bar manually.

# 1. Flow of Events
## 1.1 Basic Flow
- user clicks on symbol to open scanner
- user scans barcode
- information is fetched from the database
- product page belonging to the scanned barcode is opened

### 1.1.1 Activity Diagram
![Activity Diagram of Scanner](../resources/UC4_Scanner.drawio.svg)

### 1.1.2 Mock-up
![Image of Scanner](../resources/Scan.png)

### 1.1.3 Narrative
```gherkin
Feature: Scan Barcode

    As any user I want to be able to scan products by clicking on the scan button.

    Scenario: Open the scanner 
        Given I am on the homepage
        When I click on the scan button
        Then the scanner page opens

    Scenario: Scan a product
        Given that I am on the scanner page
        When I scan a products barcode
        Then the app will try to fetch "dmBio Nusskernmischung"

    Scenario: No product found
        Given that I scanned a products barcode
        When "dmBio Nusskernmischung" has no database entry
        Then a error message will be displayed on the screen
    
    Scenario: Product found
        Given that i scanned a products barcode
        When "dmBio Nusskernmischung" has a database entry
        Then the product page opens
```

## 1.2 Alternative Flows
(n/a)

# 2. Special Requirements
- all typical EAN/EAN-13 barcodes are expected to be supported
- device features a decent camera

# 3. Preconditions
- barcode is readable: shape of barcode (crinkles), lighting conditions
- user has granted the app permission to use the camera 

# 4. Postconditions
(n/a)
 
# 5. Extension Points
(n/a)
