# EXPERIMENT-4
 Data Wrangling and Visualization

 Name: Ramirez, Gav Wrangler A.

Section: 2ECE-A

# ECE BOARD EXAM PROBLEM:

Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given. 

Create the following data frames based on the format provided:

- Example: Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas
 
> To start our data structure, we call out panda first. Then to read the Excel file given, we use .read_excel() and print it.


    import pandas as pd

    board = pd.read_excel('board2.xlsx')
    board

> To only find the people who are > 70 in Math and whose hometown is Visayas, use .loc[] and print it.

    Vis = board.loc[(board['Math']>70)&(board['Hometown']=='Visayas'), ['Name', 'Gender', 'Track', 'Math']]
    Vis

- Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as
Instrumentation and hometown Luzon
> Same as the previous item, we use .loc[] and find > 70 in Electronics and are in Luzon and print it.

    Instru = board.loc[(board['Electronics']>70)&(board['Hometown']=='Luzon'), ['Name', 'GEAS', 'Electronics']]
    Instru

- Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female
> Next, we find the average is >=55, their hometown is Mindanao, and their Gender is Female then print.

    Mindy = board.loc[(board['Average']>=55)&(board['Hometown']=='Mindanao')&(board['Gender']=='Female'), ['Name', 'Track', 'Electronics']]
    Mindy

 # Creating the Graph
Create a visualization that shows how the different features contributes to average grade. Does
chosen track in college, gender, or hometown contributes to a higher average score?

> To create the visuals we first call out matplotlib.pyplot and seaborn.

    import seaborn as sns
    import matplotlib.pyplot as plt

> To create the visual of average grade by track, we use the following, then print.

    sns.barplot(data = board, x='Track', y='Average')
    plt.title('Average Grade by Track')
    plt.show()

> Like the first, to create the visual of average grade by gender.

    sns.boxplot(data = board ,x='Gender', y='Average')
    plt.title('Average Grade by Gender')
    plt.show()
    
> Likewise, for average grade by hometown, we also use the following.
    
    sns.boxplot(data = board ,x='Hometown', y='Average')
    plt.title('Average Grade by Hometown')
    plt.show()


# Change log
- 0.1 Added the files
- 0.2 Added the .README file

