# EM Cmap Scoring Tool

## :shipit: Overview

The EM Cmap Scoring Tool is a desktop application developed to automatically assess Concept Maps using Traditional and Categorical Scoring Methods. By default the tool was developed to assess Entrepreneurial Mindset Concept Maps however, by changing the Wordbank default file it can be used to assess Concept Maps from other subjects. To do so, please refer to the section "Creating a New WordBank"

### Table of contents:
[Installing EM Cmap Scoring Tool](#wrench-installing-em-cmap-scoring-tool)

[User's Manual](#book-users-manual)

[Creating a New WordBank](#floppy_disk-creating-a-new-wordbank)

[Including a New Codebook](#orange_book-including-a-new-codebook)

## :wrench: Installing EM Cmap Scoring Tool
The original realese under the name "EM_Cmap_Scoring_Tool_Launcher" was found to have a bug in the way the algorithm assigned the highest hierarchy.

The new release under the name "EM_Cmap_Scoring_Tool_V_1_1" addresses the situation.

- Please go over and click the [**EM_Cmap_Scoring_Tool_V_1_1.zip**](https://github.com/EM-Cmap-Scoring-Tool/EM_Cmap_Scoring_Tool/blob/main/Releases/EM_Cmap_Scoring_Tool_V_1_1.zip) that is under the *Releases* folder at the top of this page, then clik on the *Download* option on the right side of the screen.
  
![image](https://user-images.githubusercontent.com/74432387/252469796-8bc02477-e390-4e0a-9deb-421043caebd0.png)
 
- Under your computer folder, right-click **EM_Cmap_Scoring_Tool_Launcher.zip** and select *Extract all*.
  - :warning: Please do not go diectly into the .zip folder
  
| ![imagen](https://user-images.githubusercontent.com/78668372/233404342-ba3c8d10-e2c7-437e-a0da-82f20dab5c04.png) |
| :-: |
| Figure 1: .zip extraction procedure |

- Open the resulting folder after the extraction and double click on the **Cmap_Scoring_Tool_Launcher** application file to run the program (Figure 2).

| ![imagen](https://user-images.githubusercontent.com/74432387/252414286-d4566db1-8365-40d9-adc7-01254f520460.png) |
| :-: |
| Figure 2: Launch program |

- If Windows alerts you because of the application being unknown, please click on *Run anyway* or *More information* and then *Run anyway*

| <img src="https://user-images.githubusercontent.com/78668372/229847812-d8e15832-8819-401c-af6d-07d6c938bb0a.png" width=50% height=60%> |
| :-: |
| Figure 3: Protection window |

## :book: User's Manual
### :mailbox_with_mail: Input Files Type
The EM Cmap Scoring tool was designed to read CXL files exported from CmapTools (https://cmap.ihmc.us/), a free software to create concept maps. 
After creating a concept map in CmapTools, the map should be exported as CXL (File -> Export Cmap As -> CXL File...)

### :crystal_ball: Main Graphical User Interface

| ![imagen](https://user-images.githubusercontent.com/74432387/252414649-71da88b1-9c81-4f96-a788-0f2138b8e537.png) |
| :-: |
| Figure 4: EM Cmap Scoring tool GUI UPDATE |

After lauching the EM Camp Scoring Tool, a main GUI is displayed (Figure 4) with the following elements:  

1. Radio button to select the Scoring method. You can choose either "Traditional" or "Categorical" 
2. Text box to write the root concept
3. *Browse* button to select the .cxl files to score.
4. *Browse* button to select the path and filename for the Results Report.
5. *Help* button that opens a window to explain how to prepare the Cmaps files and how to use the Scoring Tool.
6. *Codebook* nutton to open a PDF with the descrition of the Categories in the WordBank for the Categorical Method
7. *Run* button to execute the scoring.

### :bar_chart: Scoring Methods 

### Traditional Scoring Method
This method assigns a score based on the number of concepts (NC), the number of hierarchies (NH), the highest hierarchy (HH), and the number of crosslinks (NCL) between concepts.
NC is the number of concepts that have connections with other concepts in the map; NH are the number of branches (hierarchies) that come from the root concept; HH is the hierarchy (branch) with the largest number of concepts; and NCL are the number of connections between concepts from different hierarchies.
The formula to get the score based on these metrics is: Score = (NC) + 5*(HH) + 10*(NCL)

Figure 5 shows an example a concept map with 9 concepts. Figure 6 shows the identification of the different hierarchies and the highest hierarchy (HH). Figure 7 highlights the crosslink in this concept map. For this example, the NC corresponds to 9, NH is 3, HH is hierarchy 2 with 3 levels, and NCL value corresponds to 1.

| ![imagen](https://user-images.githubusercontent.com/78668372/229846688-053cee04-0534-417b-a71f-7421fccae00b.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229847229-deb70aed-940f-49b2-89c1-6a0e4ce86f47.png)    | ![imagen](https://user-images.githubusercontent.com/78668372/229847398-aec3cc25-ae7f-4eb0-b5ba-2de266ecda3a.png) |
| :-: | :-: | :-: |
| Figure 5: EM Cmap example. | Figure 6: Number of hierarchies (NH) and highest hierarcy (HH) identification. | Figure 7: Number of crosslinks (NCL) identification. |

### Categorical Scoring Method
This method assigns a complexity score (CO) based on the number of concepts (NC), the number of categories that have concepts in it (NCAT), and the number of interlinks between categories (NIL). 
NC is the number of concepts that have a category assigned from those on the Wordbank file; NCAT is the number of main categories that contains at least one concept; and NIL is the number of connections between concepts of different categories. The Wordbank included by default with the Scoring Tool can be found in [Word Bank](https://github.com/RMejiaE/EM-Cmap-Scoring-Tool/blob/main/Phase_2/WordBank.csv).
The formula to get the complexity score based on these metrics is: CO = NC*(NIL/NCAT) 

Figure 8 shows an example of a concept map with 9 concepts. Figure 9 shows the categories assigned to each concept using a word bank. Figure 10 highlights the interlinks between categories. For this example, NC is 9, NCAT is 3, and NIL value corresponds to 2.

| ![imagen](https://user-images.githubusercontent.com/78668372/229618016-94668494-1f69-418b-9535-5520c98fda32.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618225-0650527c-9952-4f7c-af26-fb7dd75c95c5.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618261-4721051f-92f2-4f9b-9fdc-54e18428638a.png) |
| :-: | :-: | :-: |
| Figure 8: EM Cmap example. | Figure 9: Number of categories (NCAT) identification. | Figure 10: Number of interlinks (NIL) identification. |

### 🔮 Manual Categorization GUI 

When the Categorical Method is selected, the Scoring Tool will display a new window “Manual Concept Categorization” with the concepts in the Concept Map that were not found in the Wordbank file. The scoring tool will pre-assign these concepts to the category of the higher concept in their hierarchy. In the “Manual concept Categorization” window the user can leave the preassigned category or select a different category from a scrolling menu (Figure 11). 

| ![image](https://user-images.githubusercontent.com/74432387/252460986-5ce64957-6e1c-4ba5-acbe-9cec378855d0.png) |
| :-: |
| Figure 11: Manual Categorization GUI dropdown menu update |

To accept the preassigned or new category, the radio button must remain in “Accept all assignments” and the user must press “Continue” (Figure 12).
The user can also select “Reject all assignments and leave all concepts [that were not found in the Wordbank] in No category”. In this case, those concepts will not count for the Score.   

|![image](https://user-images.githubusercontent.com/74432387/252420985-c84d36d8-6e3e-480f-ae1a-00096d6246e8.png)|
| :-: |
| Figure 12: Accept or Reject categories for concepts not found in the Wordbank |

## :floppy_disk: Creating a New WordBank

The Wordbank can be changed by replacing the csv file name “WordBank.csv” in the same folder where the __Cmap_Scoring_Tool_Launcher__ application is. The new Wordbank must have the same file name “WordBank.csv” and the content must comply with some rules that are explained below.

### Creating a new Worbank file
To create a new Wordbank follow these steps:
1.	Open Excel and create a new blank workbook.
2.	Select __File -> Save As__
3.	Under the file name write __WordBank__  (be aware of the capitalized B).
4.	Under filetype select CSV UTF-8
5.	Press __Save__

### Populating the new WordBank file
The new WordBank must have the following structure:
- Each category (or subcategory) occupies one row:
   - In the first cell goes the number of the category
   - In the second cell goes the number of the subcategory. __If that row corresponds to a category the number must be the same as the first cell__
   - In the third cell goes the name of the category.
   - From the fourth cell onwards go the concepts in this category or subcategory (if there are no concepts in the category or subcategory these cells can be left blank). Each concept must occupy one cell, you can add as many concepts as Excel allows. Concepts can be composed of two words. Be aware that the Scoring tool will look for the exact match of the complete concept.  
- The first row of the file has the headers of each column. In column A goes “Category”, column B “Subcategory”, column C “Name”, and column D “Words”. The Scoring tool ignores this first row of the WordBank, then don’t include a category in this row, just leave the headers.

Figure 13 shows the structure of the WordBank that comes by default with the Scoring tool. This WordBank was created for Entrepreneurial Mindset concept maps. 
