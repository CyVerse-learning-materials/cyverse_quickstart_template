# Base CyVerse Tutorial Repo

You should copy this repo to build CyVerse Tutorials or Quickstarts

## How CyVerse tutorials are built

Each CyVerse Tutorial or Quick Start has its own [ReadtheDocs](https://readthedocs.org/) page which in turn is built from its own repo. Starting from a [markdown](https://guides.github.com/features/mastering-markdown/) file, documentation is converted to [ReStructured Text](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions) using [PanDoc](http://pandoc.org/). The automatically generated .rst file will need some fixing to add helpful ReStructured text [directives](http://docutils.sourceforge.net/docs/ref/rst/directives.html). Next, the documentation is built using [Sphinx](http://www.sphinx-doc.org/en/1.4.8/), and hosted on a repo configured with GitHub [Webhooks/Services](http://docs.readthedocs.io/en/latest/webhooks.html). Finally, the site is added to ReadtheDocs for serving. Directions for completing this workflow are below **(See Building a Tutorial from Scratch)**.

## Documentation types

- **Tutorials:** Tutorials teach. Users should be able to follow an example dataset through the steps of a tutorial and gain understanding about what is happening along those steps. These are in-depth guides that usually address a scientific question by covering the major steps of a scientific workflow. A tutorial is ‘successful’ when a user is able to follow the tutorial a second time with their own data and obtain reasonable results.
- **Quick Starts:** These materials are short tutorials that cover the minimal amount of information needed to complete an **operational task** (e.g. uploading data, reformatting a file, etc. ); there is no significant explanation of the science or interpretation of results. QSs highlight available resources, answer common questions (derived from user forum), and refer users to the most appropriate materials.

**Examples:**

- Uploading a file: Quick Start
- Cleaning FastQ reads: Quick Start
- Uploading files to SRA: Could be both
- Assembling a transcriptome: Tutorial


## What this repo contains

|Item|Description|Notes|
|----|-----------|-----|
|tutorial_template.md|Edit this template to create a tutorial|documents written in markdown will need to be covered to restructured text|
|quickstart_template.md|Edit this template to create a quickstart|documents written in markdown will need to be covered to restructured text|
|/img (folder)|Place images for your tutorials here|CyVerse logos and other useful images are already here| 
|/slides (folder)|Place slides associated with your tutorial here|version controlled files preferred, PPT acceptable|
|/workflows (folder)|Version-controlled workflows built with yED||
|/misc (folder)|miscellaneous items associated with this tutorial| if at all possible, files should be hosted (with anonymous access) at the CyVerse public Data Commons site. A sample **conf.py** file is located here|
|License.md|License|this license file applies to all materials created by CyVerse for this documentation|
|Contributors_maintainers.md|Contact information and recognition||


## Simple contribution instructions

### Reporting an error or issue via GitHub

- Click the 'issues' tab at the top of this GitHub page to let us know about a simple mistake such as a typo or missing file. 
 
 OR
 
- Send an email to [Tutorials@CyVerse.org](mailto:tutorials@cyverse.org)

## More complex contributions

### Fixing and/or improving documentation via GitHub

1. [Fork](https://help.github.com/articles/fork-a-repo/) this repo to your GitHub account
2. Make edits directly to the **markdown version** of the documentation if there is one, or if there is no markdown version, edit the version written in restructured text. Edits may be made to the fork the web interface to your GitHub account or [clone](https://help.github.com/articles/cloning-a-repository/) the repo to work on your local computer. For very significant changes (we suggest [making a new branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/). 
3. Commit change; if working from a local copy, push those changes to your fork in Github. 
4. Submit a pull request back to the master repository; you may need to act on feedback before your request is merged. 


## Building a Tutorial from Scratch

If you want to go beyond just creating a markdown file, you will need to install some software. 

**You will need the following software**

1. Markdown Editor - Optional, but makes it easy to preview the markdown
    - free markdown editors: 
        - MacDown(mac): http://macdown.uranusjr.com/ 
        - Markdown Pad(windows): http://markdownpad.com/ 
        - ReText(linux): https://github.com/retext-project/retext 
2. Python (2.7.9 or later) - This is required for the Sphinx package that will build our documentation:
    - https://www.python.org/downloads/
3. If needed, install pip: 
    - https://packaging.python.org/installing/#install-pip-setuptools-and-wheel
4. Sphinx - This will build our tutorials into HTML and other formats (this uses the Python package installer 'pip' so Python must be installed first); we will also install the theme we need for our documentation
        
        $pip install sphinx sphinx-autobuild
        $ pip install sphinx_rtd_theme
5. Pandoc - This will convert Markdown into ReStructured text
    - http://pandoc.org/installing.html
6. RestView - Optional, but makes it easy to preview ReStructured text files
    - http://rst.ninjs.org/
7. git - We use git to version control our documentation and manage with GitHub
    - https://git-scm.com/book/en/v2/Getting-Started-Installing-Git


**You will need the following accounts**

1. GitHub account - Will make it possible to collaborate on the documentation:
    - https://github.com/
    

### Procedure 

1. Import the CyVerse base tutorial repo following GitHub's directions here: https://help.github.com/articles/importing-a-repository-with-github-importer/
    - The CyVerse base tutorial repo URL is **https://github.com/CyVerse-learning-materials/cyverse_base_tutorial_repo**
    - Name your repo for the name of your quick start or tutorial, e.g. 
    *'name_quickstart'* or *'name_tutorial'*
2. Edit the **markdown version** of the template you are working from. Save images or other files in the appropriate directories. 
3. Delete unused templates. We will have **only one tutorial or quick start per repo.**
4. Save your markdown as  *'name_quickstart.md'* or *'name_tutorial.md'*
5. In the repo directory start the process of building the tutorial files:
        
        $ sphinx-quickstart --project='title_of_your_tutorial_or_quick start' --author="your_name" -v=1.0
        # you may accept most defaults (by hitting enter)
        # Enter the following values as prompted
        # Project name: the title of your tutorial/quick start
        # Author name(s): your name
        # Project version: 1.0 (all new tutorials start with v 1.0)       
6. Convert the markdown file to ReStructured text file (which we will call *index.rst*) using Pandoc:

        $ pandoc -f markdown -t rst -o index.rst your_file_name.md    

    For convenience, the templates have a few ReStructured text elements that may not be properly converted by Pandoc. You will need to check the converted ReStructured text. You can use an online viewer [http://rst.ninjs.org/](http://rst.ninjs.org/) or you can view live changes using restview [http://rst.ninjs.org/](http://rst.ninjs.org/)
7. You may need to edit the *'conf.py'* file to change the following lines:
     - (line 52) copyright = 'YEAR, CyVerse'
     - (line 113) html_theme = 'sphinx_rtd_theme'
   We have provided a sample  *'conf.py'* file in the */misc* folder which you could also edit and replace.    
8. Build the tutorial:

        $ make html
9. Your HTML site will be in the _build directory that has been created. 
10. Commit your changes and push the tutorial back to GitHub.
11. Notify [Tutorials@CyVerse.org](mailto:Tutorials@CyVerse.org) that your tutorial is ready for inclusion in the main CyVerse documentation repo. We will review and verify the contribution, and add you as a maintainer repo in the CyVerse collection. You should make future edits following the instructions above for 'Fixing and/or improving documentation via GitHub.' Alternatively, you can host your tutorial independently on ReadTheDocs following their [instructions for importing documentation](https://docs.readthedocs.io/en/latest/getting_started.html#import-your-docs). 


## Other tutorial elements

**Workflow Diagrams:** Version controlled workflow diagrams can be built using [yEd](http://www.yworks.com/products/yed).
 
