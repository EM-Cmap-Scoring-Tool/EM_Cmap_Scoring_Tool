# EM Cmap Scoring Tool REVIEW AND UPDATE IMAGES AND TEXT
Repository containing the distribution version of the EM Cmap Scoring Tool

## :wrench: Installing EM Cmap Scoring Tool
- Please go over and click the [**EM_Cmap_Scoring_Tool_Launcher.zip**](https://github.com/RMejiaE/EM-Cmap-Scoring-Tool/blob/main/Phase_5/EM_Cmap_Scoring_Tool_Launcher.zip) at the top of this page, then clik on the *Download* option on the right side of the screen.
- Under your computer folder, right-click **EM_Cmap_Scoring_Tool_Launcher.zip** and select *Extract all*.
  - :warning: Please do not go diectly into the .zip folder
  
| ![imagen](https://user-images.githubusercontent.com/78668372/233404342-ba3c8d10-e2c7-437e-a0da-82f20dab5c04.png) |
| :-: |
| Figure 1: .zip extraction procedure |

- Open the resulting folder after the extraction and double click on the **Cmap_Scoring_Tool_Launcher** application file to run the program (Figure 2).

| ![imagen](https://user-images.githubusercontent.com/78668372/230093790-764e3e18-1c3c-4f5b-88ff-1b8e95e21c47.png) |
| :-: |
| Figure 2: Launch program |

- If Windows alerts you because of the application beign unknown, please click on *Run anyway* or *More information* and then *Run anyway*

| <img src="https://user-images.githubusercontent.com/78668372/229847812-d8e15832-8819-401c-af6d-07d6c938bb0a.png" width=50% height=60%> |
| :-: |
| Figure 3: Protection window |

## :crystal_ball: Graphical User Interface (GUI) UPDATE

| ![imagen](https://user-images.githubusercontent.com/78668372/245651333-1d85aebc-c658-4ef8-b2c7-63a9037726f5.png) |
| :-: |
| Figure 4: EM Cmap Scoring tool GUI UPDATE |

Figure 4 shows the GUI, it elements are described below: 

1. Text box to write the root concept.
2. *Browse* button to select the Cmap files for scoring.
3. *Browse* button to select the path where scoring report will be saved.
4. Scoring method selection
5. *Help* button that opens a window to explain how to prepare the Cmaps files and how to use the Scoring Tool.
6. *Run* button to execute the scoring.

## 🔮 Manual Categorization GUI UPDATE
Additional elements were added to the program that help the user to identify the categories and subcategories in the Manual Categorization GUI. 

Categories were left in the same level and subcategories are presented with a tab and a '-' at the start, as can be seen in Figure 5.

| ![imagen](https://user-images.githubusercontent.com/78668372/245650502-b4fe9877-406d-4909-8f53-5d93dfcc1b3f.png) |
| :-: |
| Figure 5: Manual Categorization GUI dropdown menu update |

# 📚 Theoretical Framework
![imagen](https://user-images.githubusercontent.com/78668372/222168066-8f58282b-3591-43e3-a3ed-1d50a78556a4.png)

Figure 6: Cmap example[1]
## Traditional Scoring Method
This method assigns a score based on the number of concepts (NC), the number of hierarchies (NH), the highest hierarchy (HH), and the number of cross links (NCL) between concepts.

As seen in Figure 6, the NC is the ammount of bubbles, the NH are the different paths that leave the root concept, the HH is the hierarchy containing most concepts, and the NCL are the connections between concepts of different hierarchies.

Score = (NC) + 5*(HH) + 10*(NCL)
## Categorical Scoring Method
This method identifies the number of concepts (NC) present in the Cmap, then classifies the concepts into categories, and lastly, it calculates the number of concepts in each category to finally compute the number of categories (NCAT) that contain at least one concept. After that, it calculates the number of  connections between concepts of different categories, better known as interlinks (NIL). The score is meassure by the level of complexity (CO) of the Cmap.

CO = NC*(NIL/NCAT)

On Figure 6, each concept would be assigned a number depending on the category for the NC and NCAT calculation, and them the connection between **Foundations** and **Floor** would be checked to see if the two concepts are from different categories.

## :bar_chart: Scoring Methods 
The program receives the Cmap files as a .cxl extention that contains the different concepts listed and the connections between them. The extraction algorithm takes all the concepts and concepts linked pairs and stores them as two lists to be used for scoring calculation.
### Traditional
The number of concepts (NC) is obtained by counting all the concepts, excluding the root concept, present in the Cmap. The number of hierarchies (NH) is obtained by identifying the concepts that are connected directly to the root conept. The highest hierarchy (HH) corresponds to the hierarchy with the longest level. Lastly, the number of cross links (NCL) is obtained by counting the connections between paired concepts that are from different hierarchies.

| ![imagen](https://user-images.githubusercontent.com/78668372/229846688-053cee04-0534-417b-a71f-7421fccae00b.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229847229-deb70aed-940f-49b2-89c1-6a0e4ce86f47.png)    | ![imagen](https://user-images.githubusercontent.com/78668372/229847398-aec3cc25-ae7f-4eb0-b5ba-2de266ecda3a.png) |
| :-: | :-: | :-: |
| Figure 7: EM Cmap example with number of concepts (NC) identification. | Figure 8: Number of hierarchies (NH) and highest hierarcy (HH) identification. | Figure 9: Number of crosslinks (NCL) identification. |

Figure 7 shows an example of a concept map with 9 concepts. After listing them, hierarchies and its concepts are identifyed (Figure 8). The subindex after the dot serves here to illustrate the level of each hierarchy and hence, the longest one. Finally crosslinks are identified (Figure 9).
For this example, the NC will correspond to 9, NH is 3, the HH will be hierarchy 2 with 3 levels, and NCL value corresponds to 1.

### Categorical
The number of concepts (NC) is obtained by counting all the concepts, excluding the root concept, present in the Cmap. The number of categories (NCAT) is obtained by classifying the concepts present into each of the categories and counting the ones that contain at least one concept. For the case of Entrepreneurial Mindset (EM), the cateogries were defined by the [Word Bank](https://github.com/RMejiaE/EM-Cmap-Scoring-Tool/blob/main/Phase_2/WordBank.csv) developed by the research team members. Lastly, the number of interlinks (NIL) is obtained by counting the connections between paired concepts that are from different categories.

| ![imagen](https://user-images.githubusercontent.com/78668372/229618016-94668494-1f69-418b-9535-5520c98fda32.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618225-0650527c-9952-4f7c-af26-fb7dd75c95c5.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618261-4721051f-92f2-4f9b-9fdc-54e18428638a.png) |
| :-: | :-: | :-: |
| Figure 10: EM Cmap example with number of concepts (NC) identification. | Figure 11: Number of categories (NCAT) identification. | Figure 12: Number of interlinks (NIL) identification. |

Figure 10 shows an example of a concept map with 9 concepts. After listing the concepts, they are categorized using a word bank (Figure 11) and finally interlinks are identified (Figure 12).
For this example, the NC will correspond to 9, NCAT will be 3, and NIL value corresponds to 2.


# 📑 References
1. Watson MK, Barrella E, Pelkey J. Assessment of conceptual knowledge using a component-based concept map scoring program. The International journal of engineering education. 2018;34(3):1025-1037.
