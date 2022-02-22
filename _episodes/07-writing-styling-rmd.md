---
title: "Writing and Styling Rmd Documents"
teaching: 10
exercises: 05
questions:
- "What is the Visual Editor in Rstudio?"
- "Which features does the Visual Editor have?"
- "How can I can apply styling and formatting to rmd documents in Rstudio more easily?"
- "How to add inline code?"

objectives:
- "Learn how to enable the visual editor."
- "Get familiar with its basic functionalities."
- "Apply rmd formatting and styling using the visual editor."
- "Learn how to add inline code to your rdm document."

keypoints:
- "The visual editor has made formatting much easier."
- "You can apply rmd styling without prior Rmarkdown knowledge."
- "You can include inline code to narratives for basic calculations."
---

## Formatting Rmd Documents with the Visual Editor

As we mentioned earlier, the visual editor in RStudio has made RMarkdown formatting much more effortless. It provides improved productivity for composing longer-form articles and analyses with R Markdown. The visual markdown editing is available in RStudio v1.4 or higher. Markdown documents can be edited in either source or visual mode. To switch into visual mode for a given document, toggle on the compass  icon at the top-right of the document toolbar (or alternatively the ⌘⇧ F4 keyboard shortcut). This will prompt a formatting bar through which you can apply styling, add links, create tables, and others similar to functions you find in google docs and other document editors. Note that you can switch between source and visual mode at any time (editing location and undo/redo state will be preserved when you switch). Let’s try it! Feel free to follow along or just watch this quick demo. But first, make sure to have your visual editor enabled on your screen. 

### Editor Toolbar

The editor toolbar includes buttons for the most commonly used formatting commands:

![Fig. 5.1 - Toolbar](../fig/07-toolbar.png)

Additional commands are available on the Format, Insert, and Table menus:

![Fig. 5.2 - Menu](../fig/07-menu.png)

> ## Tip: Inserting anything with shortcuts
> You can also use the catch-all ⌘ / shortcut to insert just about anything. Just execute the shortcut then type what you want to insert. For example: `/lis` will prompt listing options.
>
{: .callout}


### *Applying Emphasis*

At the very top of the document we have a recommended citation for the sample data paper (**FIXME1**). We want to emphasize the title of the journal, “Data in brief” in italics. Select the text and click in the I icon and voilà! Remember to delete (FIXME1).


### *Adding Links*
In the same citation we have just worked on, let’s now add a link to it by selecting and copying the doi address. Then, click on the link icon and paste the address in the URL field. Simple right? If you prefer, you can also the drop-down insert menu, or even use shortcuts. By hovering the mouse over the desired icon, you will see which keys you should use. For a complete list of editing shortcuts, check this link. Tip: if you didn’t intend to use a shortcut and want to reverse its effect, just press the backspace key.


### *Adding Headings*

Adding headings to a Rmarkdown document in Rstudio is as simple as applying links. Let’s say we want the abstract section as a Heading Level 2. We can select the “abstract” then, and under “Normal” on the left-hand side of the menu, we can choose the desired level. Again, all the shortcuts will be listed next to the styling in the menu. Now apply the same heading to keywords and Level 1 to “Specifications Table” (**FIXME2**).


### *Creating Tables*

Because creating tables manually in Rmd documents could be a little painful for beginners, Rstudio released an add-in functionality for tables back in 2018. The new visual editor, however, have made the process to create rmd tables more similar to other editors we use daily. In our template, we have the specification table with 10 rows and two columns (FIXME3). If we were willing to add that table, we could do that by inserting a table to a selected part of the documents and by specifying the desired number of rows and columns.  Including a caption is optional, but recommended. We can add or delete rows and columns, add a header that will be set bold by default but can be changed, and set the desired alignment. Select the desired text and click on the crossed T icon if you wish to clear formatting.


### *Creating Bullet and Numbered Lists*

Again, similarly to other document editors, Rstudio allows you to turn text into bullet or numbered lists. Let’s apply a bullet list to the paragraphs specifying the values of the data reported in the data paper (**FIXME4**). Assuming we were willing to create a numbered list instead, we could have followed the same process and chosen the other icon. We can also sink or lift the listed items.


### *Adding Images*

You may need to include static images to your manuscripts. For that, you can use the insert image function, click on the painting icon or even use the shortcut that shows right next to the function in the menu. After browsing and upload the desired image you may also specify the caption and the image title, as well as adjust dimensions if needed. Let's insert two images Fig. 1 (**FIXME5**) and Fig. 2 (**FIXME6**).  


### *Adding Formulas*

If you have math formula in your manuscript there are three different ways you may insert one. Let's look for **FIXME7** for an example. Point and click at the insert menu, use the catch-all `⌘ /` keyboard short and then get to inline math mode, or type the formula content between dollar signs `$`. You will notice that the color and font type will change, as Rstudio identifies the block as an inline equation.

## Adding Inline Code

You can also include `r code` directly in your text. Say you are discussing some of the summary statistics in your manuscript, Rmarkdown makes this possible through HTML/LaTeX inline code which allows you to calculate simple expressions integrated to your narrative. Inline code enables you to insert `r code` into your document to dynamically updated portions of your text. In other words, if your data set changes for any reason the code will automatically update the calculation specified. 

This can be helpful when referring to specific variables on your data. For example, you should include numbers that are derived from the data as code not as numbers. Thus, rather than writing “The CSV file contains choice consistency data for 10.000 simulated participants” (**FIXME8**), insert a bit of code that, when evaluated, gives the number of individuals. Please note that this insertion is not included in the visual editor, so we need to do write an expression, for example:

The CSV file contains choice consistency data for ` `r nrow(bronars_simulation_data.csv)` ` simulated participants.

If you update your dataset this value will be correct. But, remember to check if you are calling the correct dataset.


> ## CHALLENGE 5.1 - Adding inline code
> Suppose we would like to add some information to the sentence we have jsut adjusted in our manuscript. We would like to include the average for the variable *violation_counts* present in the same dataset. Which inline code we would have to add to following sentence?
> 
> The CSV file contains choice consistency data for ` `r nrow(bronars_simulation_data.csv)` ` simulated participants, that have been used to determine the power of our food-choice task design to detect choice consistency violations, which averaged ` `enter inline code here` `. 
> What inline code would you enter? What number would replace the inline code?
> 
> Tip: we will need to use a `dataset$variable syntax`!
> 
>> ## Solution:
>> ` `r mean(bronars_simulation_data$violation_counts)` `
>> 5.3924
> {: .solution}
{: .challenge}


> ## Important Note:
> Make sure the file you are calling is in the right subdirectory and your working directory is set appropriately.
>
{: .callout}


> ## More on inline codes:
> R Markdown will always display the results of inline code, but not the code. Inline expressions do not take knitr options.
>
{: .callout}


## Keyboard Shortcuts
As you become a more regular Rstudio user, you may also consider using some keyboard shortcuts for all basic editing tasks. Visual mode supports both traditional keyboard shortcuts (e.g. ⌘ B for bold) as well as markdown shortcuts (using markdown syntax directly). For example, enclose **bold** text in asterisks or type ## and press space to create a second level heading. Here are some of the most commonly used shortcuts:

![Fig. 5.3 - Shortcuts](../fig/07-shortcuts.png)


## Other Editing Features
The visual editor allows users to insert images by browsing their location or copying and pasting it to the rmd document directly. There are also options to add html, line blocks, blockquotes, and footnotes. Up next we will learn more about how to add code chunks. In further episodes we will also learn how to insert citations and create a bibliography.