<!---

Images can be added in-line as a reStructured text substitution, but will not render in Markdown. See reStructured text example. http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions

|CyVerse logo|

--->

#Tutorial name
<!---
Use short, imperative titles e.g. Upload and share data, uploading and sharing data
--->

## Goal

<!---
Avoid covering upstream and downstream steps that are not explicitly and necessarily part of the tutorial - write or link to separate quick starts/tutorials for those steps.
--->

<!---
A few sentences (50 words or less) describing the ultimate goal of the steps in this tutorial.
--->

## Prerequisites
<!---
Insert short description
--->


### Input and example data

*In order to complete this tutorial you will need to have the following inputs prepared*

|Input File(s)|Format|Preparation/Notes|Example Data|
|-------------|------|-----------------|------------|
||||

<!---
Insert short description
--->

<!---
*You may find the following tutorials useful for completing this one:*

|Related tutorial|Description|Link|
|----------------|-----------|----|
|Name|Description|[Link]()|
|||
--->

<!---
**Example data citation:**

Links to papers, SRA, etc. 
--->

### Downloads, access, and services

*In order to complete this tutorial you may also need:*

|Prerequisite|Preparation/Notes|Link/Download|
|------------|-----------------|-------------|
|Reference genome|Provide your own genome in FASTA format or use CyVerse provided genome|[Supported CyVerse Genomes](http://datacommons.cyverse.org/browse/iplant/home/shared/iplantcollaborative/genomeservices/builds/1.0.0/24_77)|



### Platform(s)

<!---
Keep only the relevant entries and delete/hide the remaining
--->

*We will use the following CyVerse platform(s):*

|Platform|Interface|Link|Platform Documentation|Quick Start|
|--------|---------|----|----------------------|-----------|
|Discovery Environment|Web/Point-and-click|[Discovery Environment](https://de.iplantcollaborative.org)|[Manual](https://wiki.cyverse.org/wiki/display/DEmanual/Table+of+Contents)|[Quick Start]()
|Atmosphere|Command-line (ssh) and/or Desktop (VNC)|[Atmosphere](https://atmo.cyverse.org)|[Manual](https://wiki.cyverse.org/wiki/display/atmman/Atmosphere+Manual+Table+of+Contents)|[Quick Start]()|
|BisQue|Web/Point-and-click and/or Command-line (API)|[BisQue](http://bisque.iplantcollaborative.org/client_service)|[Manual](https://wiki.cyverse.org/wiki/display/BIS)|[Quick Start]()|
|DNA Subway|Web/Point-and-click|[DNA Subway](http://dnasubway.iplantcollaborative.org/)|[Manual](http://dnasubway.iplantcollaborative.org/files/pdf/DNA_Subway_Guide.pdf)|[Quick Start]()|
|Agave API|Command-line (API)|[Agave API](https://agaveapi.co)|[Live Docs](https://agaveapi.co)|[Quick Start]()|


---

## Overview

<!---
Text and workflow image go here. Using reStructured text, we can place a link to an image in pipe form (label images 'image n' with n=0 being image 0 and so on). At the end of the document add the image names, links, and parameters. 
--->

<!---

Images can be added in-line as a reStructured text substitution, but will not render in Markdown. See reStructured text example here. http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions

|image 0|

--->

### Apps and atmosphere images

**Discovery Environment App(s):**

<!---
Links to Apps in the DE which are found by clicking the INFO button; select and copy App URL. Use DOI links if available, otherwise link to github docker image (See: https://github.com/iPlantCollaborativeOpenSource/docker-builds). 
--->

|App name|Version|Description|App Link|Docker/DOI Link|
|--------|-------|-----------|--------|---------------|
|Muscle|3.8.31|Multiple sequence aligner|[App](https://de.iplantcollaborative.org/de/?type=apps&app-id=9b41c9e4-5031-4a49-b1cb-c471335df16e)

**Atmosphere Image(s):**

|Image name|Version|Description|Link|Docker/DOI Link|
|----------|-------|-----------|----|---------------|
|CyVerse CentOS 6.8 GUI Base|1.0|base image CentOS 6.8 with GNOME GUI|[Image](https://atmo.cyverse.org/application/images/1384)|


## Directions

<!---

Style recommendations for DE:

1. Steps generally begin with a verb or preposition:

    "Click on the XXXX button" OR  "Under the 'Results Menu'"

2. Locations parenthetical and separated by carets. Locations not preceded by (semi)colons don't use parenthesis. (optional: ultimate object in bold):

    "(Username > analyses > output)" OR "Output is located at: Username >                 
    analyses > **output**"
    
3. Buttons and key words in bold:
    "Click on **Apps**" or "Select **Arabidopsis**"

4. App accordion menu titles in double quotes " "

5. App header description in single quotes ' '

--->

### Subsection 1 name

**Task:**

<!---
1-2 sentence description of what happens here
--->


**Input(s):**

|File|Description|Example input(s)|
|----|-----------|----------------|
|file.extenstion|.extension file (required)||
||||

<!---
Steps and text go here
--->

<!---
.. Hint::
	You can insert reStructured text directives in the Markdown. The formatting will have to be fixed later in the .rst document see [rst docs](http://docutils.sourceforge.net/docs/ref/rst/directives.html#admonitions)
--->

**Output(s):**

|File|Description|Example output(s)|
|----|-----------|-----------------|
||||

---

### Subsection 2 name

**Task:**
<!---
1-2 sentence description of what happens here
--->


**Input(s):**

|File|Description|Example input(s)|
|----|-----------|----------------|
||||

<!---
Steps and text go here
--->

**Output(s):**

|File|Description|Example output(s)|
|----|-----------|-----------------|
||||

---

### Subsection 3 name

**Task:**
<!---
1-2 sentence description of what happens here
--->


**Input(s):**

|File|Description|Example input(s)|
|----|-----------|----------------|
||||

<!---
Steps and text go here
--->

**Output(s):**

|File|Description|Example output(s)|
|----|-----------|-----------------|
||||

---

### Subsection 4 name

**Task:**
<!---
1-2 sentence description of what happens here
--->


**Input(s):**

|File|Description|Example input(s)|
|----|-----------|----------------|
||||

<!---
Steps and text go here
--->

**Outputs:**

|File|Description|Example output(s)|
|----|-----------|-----------------|
||||




## Summary

<!---
Summary and example figures
--->

**Next Steps:**



## FAQ


<!---
Optional list of one or more FAQ questions
--->

1. **Question:**
    a. 
2. **Question:**
    a. 


## More help/additional information

<!---
Short description and links to any reading materials
--->

- **Search for an answer:** [CyVerse Learning Center](http://www.cyverse.org/learning-center) or [CyVerse Wiki](https://wiki.cyverse.org/wiki/dashboard.action)
- **Post your question to the user forum:** [Ask CyVerse](http://ask.iplantcollaborative.org/questions/)

### Fix or improve this tutorial 


- **Fix this tutorial on GitHub:** [GitHub](Link_to_gh_readme)
- **Send a note:** [Tutorials@CyVerse.org](mailto:Tutorials@CyVerse.org)
<!---

SAMPLE DIRECTIVES (DELETE UNUSED ONES)
--------------------------------------

See: http://docutils.sourceforge.net/docs/ref/rst/directives.html#admonitions

.. Danger::
	This step is dangerous

.. Important::
	This step is important
	
.. Caution::
	Exercise caution
	
.. Hint::
	This is a hint

.. Important::
	This is very important

.. note:: This is a note admonition.
   This is the second line of the first paragraph.

   - The note contains all indented body elements
     following.
   - It includes this bullet list.



.. |CyVerse logo| image:: ./img/cyverse_rgb.png
    :width: 500
    :height: 100
--->
