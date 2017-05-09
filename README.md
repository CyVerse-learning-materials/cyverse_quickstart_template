# Template CyVerse Quickstart Repo

You should import this repo to build CyVerse Quickstarts

## How CyVerse Learning Center documentation is built

Each CyVerse Tutorial or Quickstart has its own [ReadtheDocs](https://readthedocs.org/) page which in turn is built from its own repo (See the template repos at [https://github.com/CyVerse-learning-materials](https://github.com/CyVerse-learning-materials)). Starting from a [ResStructured text file](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html) (index.rst) The documentation is built using [Sphinx](http://www.sphinx-doc.org/en/1.4.8/), and hosted on a repo configured with GitHub [Webhooks/Services](http://docs.readthedocs.io/en/latest/webhooks.html). Finally, the site is added to ReadtheDocs. Directions for completing this workflow are below **(See Building a Tutorial from Scratch)**.


## Documentation types

- **Tutorials:** Tutorials teach. Users should be able to follow an example dataset through the steps of a tutorial and gain understanding about what is happening along those steps. These are in-depth guides that usually address a scientific question by covering the major steps of a scientific workflow. A tutorial is ‘successful’ when a user is able to follow the tutorial a second time with their own data and obtain reasonable results.
- **Quickstarts:** These materials are short tutorials that cover the minimal amount of information needed to complete an **operational task** (e.g. uploading data, reformatting a file, etc. ); there is no significant explanation of the science or interpretation of results. QSs highlight available resources, answer common questions (derived from user forum), and refer users to the most appropriate materials.

**Examples:**

- Uploading a file: Quickstart
- Cleaning FastQ reads: Quickstart
- Uploading files to SRA: Could be both
- Assembling a transcriptome: Tutorial


## What this repo contains

|Item|Description|Notes|
|----|-----------|-----|
|index.rst|edit this template to create the documentation|You can preview .rst using [RestView](http://rst.ninjs.org/)|
|quickstart_template.md|Markdown version of template|documents written in markdown will need to be covered to restructured text. [PanDoc](http://pandoc.org/) can do this|
|/img (folder)|Place images for your tutorials here|CyVerse logos and other useful images are already here| 
|/slides (folder)|Place slides associated with your tutorial here|version controlled files preferred, PPT acceptable|
|/misc (folder)|miscellaneous items associated with this tutorial| if at all possible, files should be hosted (with anonymous access) at the CyVerse public Data Commons site|
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
2. Make edits directly to the **index.rst** file. Edits may be made to the fork the web interface to your GitHub account or [clone](https://help.github.com/articles/cloning-a-repository/) the repo to work on your local computer. For very significant changes (we suggest [making a new branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/)). 
3. Commit change; if working from a local copy, push those changes to your fork in Github. 
4. Submit a pull request back to the master repository; you may need to act on feedback before your request is merged. 


## Building a Quickstart from Scratch

If you want to go beyond just creating a markdown file, you will need to install some software. 

**You will need the following software**

1. Python (2.7.9 or later) - This is required for the Sphinx package that will build our documentation:
    - https://www.python.org/downloads/
2. If needed, install pip: 
    - https://packaging.python.org/installing/#install-pip-setuptools-and-wheel
3. Sphinx - This will build our tutorials into HTML and other formats (this uses the Python package installer 'pip' so Python must be installed first); we will also install the theme we need for our documentation
        
        $ pip install sphinx sphinx-autobuild sphinx_rtd_theme
4. RestView - Optional, but makes it easy to preview ReStructured text files [http://rst.ninjs.org/](http://rst.ninjs.org/) or install:

        $ pip install restview 
5. git - We use git to version control our documentation and manage with GitHub
    - https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

**Note:** For your convenience, a markdown version of the template is provided. We'd appreciate if you convert it to ReStructured text, but since the conversion is not perfect, let us know if you need help and we will assist you with the process. 


**You will need the following accounts**

1. GitHub account - Will make it possible to collaborate on the documentation:
    - https://github.com/
    

### Procedure 

1. **Import** (not clone) the CyVerse base tutorial repo following GitHub's directions here: https://help.github.com/articles/importing-a-repository-with-github-importer/
    - The CyVerse base quickstart repo URL is **https://github.com/CyVerse-learning-materials/cyverse_quickstart_template**
    - Name your repo for the name of your quickstart e.g. 
    *'name_quickstart'* 
2. Edit the **index.rst**. Save images or other files in the appropriate directories.  **See our recommended style guide for writing documentation below.**
3. Where possible, we recommend keeping quickstart documentation on a single index.rst page.  If needed, a 'step2.rst' page is included and you can copy as needed. Either way, update the table of contents included in 'index.rst'. We will have **only one tutorial or quick start per repo.**
4. Save your work as  *'index.rst'*
5. Edit the *'conf.py'* file to set the project and author information
6. Build the tutorial:

        $ make html
7. Your HTML site will be in the _build directory that has been created (you can preview this in your web browser at this time).
8. Commit your changes and push the tutorial back to GitHub.
9. Notify [Tutorials@CyVerse.org](mailto:Tutorials@CyVerse.org) that your tutorial is ready for inclusion in the main CyVerse documentation repo. We will review and verify the contribution, and add you as a maintainer repo in the CyVerse collection. You should make future edits following the instructions above for 'Fixing and/or improving documentation via GitHub.' Alternatively, you can host your tutorial independently on ReadTheDocs following their [instructions for importing documentation](https://docs.readthedocs.io/en/latest/getting_started.html#import-your-docs). We will also follow up about ensuring test data associated with the documentation are available and open. 

### Documentation Style Guide

*General Principles*

- Write instructions in short numbered steps. 
- Where possible limit step to one action; small final actions such as 'press submit' should be separated by a semicolon
- Limit the use of screenshots; where they are needed, use ReStructured text directives for [substitution of images](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions) and label them in numbered order in the text (e.g. |image1|)
- Example data associated with documentation should be anonymously available on CyVerse Data Commons (Tutorials@cyverse.org can help you with this)
- Discovery Environment applications should be directly linked to documentation (clicking the 'info' button on any application will give you the 'App URL')
- Atmosphere images should be directly linked to documentation (e.g. "atmo.cyverse.org/application/images/####". 

*Specific examples*

|Instruction|Example|
|-----------|-------|
|Steps generally begin with a verb or preposition|<ul><li>Click on the button<li>Under the "Result" menu</ul>|
|Locations of files are given in absolute paths|<ul><li>/dir1/dir2/file.extension</ul>|
|Top-level menus in Discovery Environment Apps in double quotes|<ul><li>Under "Input" select...</ul>|
|Subheadings/steps in Discovery Environment Apps in single quotes|<ul><li>For 'sensitivity' enter...</ul>|
|Buttons and keywords in bold|<ul><li>Click on **Apps**<li>Select **Arabidopsis**<li>Set 'sensitivity' to **Medium**</ul>|
