# EXPERIMENT-4
 Data Wrangling and Visualization

 Name: Ramirez, Gav Wrangler A.

Section: 2ECE-A

# ECE BOARD EXAM PROBLEM:

Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given. 

Create the following data frames based on the format provided:

 - Example: Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas
 - Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
 - Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female

> To start our data structure, we call out panda first. Then to read the Excel file given, we use .read_excel() and print it.


    import pandas as pd

    board = pd.read_excel('board2.xlsx')
    board
> OUTPUT:
>
> <img width="569" alt="image" src="https://github.com/user-attachments/assets/ab1ac89b-8e29-4f7d-b8b0-0de7e65a5ca1">

# The hometown is Visayas, and the score in Math is greater than or equal to 70 

> To only find the people who are > 70 in Math and whose hometown is Visayas, use .loc[] and print it.

    Vis = board.loc[(board['Math']>70)&(board['Hometown']=='Visayas'), ['Name', 'Gender', 'Track', 'Math']]
    Vis
    
> OUTPUT:
> 
> <img width="270" alt="image" src="https://github.com/user-attachments/assets/bc053c4b-93e3-4ea3-a145-65021df280c8">

# The track is Instrumentation, the hometown is Luzon, and the score in electronics is greater than or equal to 70 
> Same as the previous item, we use .loc[] and find > 70 in Electronics and are in Luzon and print it.

    Instru = board.loc[(board['Electronics']>70)&(board['Hometown']=='Luzon'), ['Name', 'GEAS', 'Electronics']]
    Instru
> OUTPUT:
> 
> <img width="192" alt="image" src="https://github.com/user-attachments/assets/c3a4e715-5181-4299-a16d-0b2f09289630">

# The hometown is Mindanao, the gender is Female, and the average grade is greater than or equal to 55
> Next, we find the average is >=55, their hometown is Mindanao, and their Gender is Female then print.

    Mindy = board.loc[(board['Average']>=55)&(board['Hometown']=='Mindanao')&(board['Gender']=='Female'), ['Name', 'Track', 'Electronics']]
    Mindy
> OUTPUT:
> 
> <img width="250" alt="image" src="https://github.com/user-attachments/assets/5b1c8a4b-1008-4242-b793-a843d429b0fd">


 # Creating the Graph
Create a visualization that shows how the different features contributes to average grade. Does
chosen track in college, gender, or hometown contributes to a higher average score?

- To create the visuals we first call out matplotlib.pyplot and seaborn.

      import seaborn as sns
      import matplotlib.pyplot as plt

- To create the visual of average grade by track, we use the following, then print.

      sns.barplot(data = board, x='Track', y='Average')
      plt.title('Average Grade by Track')
      plt.show()
> OUTPUT:
>  
> <img width="519" alt="image" src="https://github.com/user-attachments/assets/57667335-4874-4518-ae33-488098946516">

- Like the first, to create the visual of average grade by gender.

      sns.boxplot(data = board ,x='Gender', y='Average')
      plt.title('Average Grade by Gender')
      plt.show()
> OUTPUT:
> 
> <img width="519" alt="image" src="https://github.com/user-attachments/assets/8f57fa19-72ad-44e4-be6f-3651798ae4a1">

- Likewise, for average grade by hometown, we also use the following.
    
      sns.boxplot(data = board ,x='Hometown', y='Average')
      plt.title('Average Grade by Hometown')
      plt.show()
> OUTPUT:
>  
> <img width="556" alt="image" src="https://github.com/user-attachments/assets/d0764f68-0822-46a2-9fce-6e9887911955">


# Change log
- 0.1 Added the files.
- 0.2 Added the .README file.
- 0.3 Edited the .README file.

