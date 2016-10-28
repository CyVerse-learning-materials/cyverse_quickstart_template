# Base CyVerse Tutorial Repo

You should copy this repo to build CyVerse Tutorials or Quickstarts

## How CyVerse tutorials are built

Each CyVerse Tutorial or Quick Start has its own [ReadtheDocs](https://readthedocs.org/) page which in turn is built from its own repo. Starting from a [markdown](https://guides.github.com/features/mastering-markdown/) file, documentation is converted to [ReStructured Text](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions) using [PanDoc](http://pandoc.org/). The automatically generated .rst file will need some fixing to add helpful ReStructured text [directives](http://docutils.sourceforge.net/docs/ref/rst/directives.html). Next, the documentation is built using [Sphinx](http://www.sphinx-doc.org/en/1.4.8/), and hosted on a repo configured with GitHub [Webhooks/Services](http://docs.readthedocs.io/en/latest/webhooks.html). Finally, the site is added to ReadtheDocs for serving. Directions for completing this workflow are below **(See Building a Tutorial from Scratch)**.

## Documentation types

- **Tutorials:** Tutorials teach. Users should be able to follow an example dataset through the steps of a tutorial and gain understanding about what is happening along those steps. These are in-depth guides that usually address a scientific question by covering the major steps of a scientific workflow. A tutorial is ‘successful’ when a user is able to follow the tutorial a second time with their own data and obtain reasonable results.
- **Quick Starts:** These materials are short tutorials that cover the minimal amount of needed to complete an **operational task** (e.g. uploading data, reformatting a file, etc. ); there is no significant explanation of the science or interpretation of results. QSs highlight available resources, answer common questions (derived from user forum), and refer users to the most appropriate materials.

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
|/misc (folder)|miscelaneous items associated with this tutorial| if at all possible, files should be hosted (with anonymous access) at the CyVerse public Data Commons site. A sample **config.py** file is located here|
|License.md|License|this license file applies to all materials created by CyVerse for this documentation|
|Contributors_maintainers.md|Contact information and recognition||


## Simple contribution instructions

### Reporting an error via GitHub

- Click 'issues' at the top of this GitHub page to let us know about a simple mistake such as a typo or missing file. 
 
 OR
 
- Send an email to [Tutorials@CyVerse.org](mailto:tutorials@cyverse.org)

## More complex contributions

### Fixing and/or improving documentation via GitHub

1. [Fork](https://help.github.com/articles/fork-a-repo/) this repo to your GitHub account
2. Make edits directly to the **markdown version** of the documentation if there is one, or if there is no markdown version, edit the version written in restructured text. Edits may be made to the fork the web interface to your GitHub account or [clone](https://help.github.com/articles/cloning-a-repository/) the repo to work on your local computer. For very significant changes (we suggest [making a new branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/). 
3. Commit change; if working from a local copy, push those changes to your fork in Github
4. Submit a pull request back to the master repository; you may need to act on feedback before your request is merged. 


## Building a Tutorial from Scratch

1. Starting from the chosen template, write the tutorial. 
    - free markdown editors: 
        - http://macdown.uranusjr.com/ (mac)
        - http://markdownpad.com/ (windows)
2. Save the tutorial and related files to their respective directories in the repo. 
3. Install sphinx
    ```
    $pip install sphinx sphinx-autobuild
    ```
2. Create a directory for your tutorial; at this time you might want to [initialize a git repository](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/).
3. In the new directory, start the process of building sphinx pages
    ```
    $ sphinx-quickstart
    # you may accept all defaults
    ```
4. You will now have a placeholder 'index.rst' file which will be the page for your tutorial
5. Convert the markdown file to restructured text using pandoc
    - install pandoc; see http://pandoc.org/installing.html or if you have homebrew:
        ```
        $ brew install pandoc
        ```
    - Convert from markdown to restructured text (here making the output file index.rst
        ```
        $ pandoc -f markdown -t rst -o index.rst your_file_name.md
        ```
    - There don't seem to be too many nice ways to preview the restructured text to check for broken formatting /conversion errors. You can use an online viewer (http://rst.ninjs.org/) or you can view live changes using restview (https://mg.pov.lt/restview/)
6. Change the the following defaults in the `config.py1` file to the following: 
    a. line 113: html_theme = 'sphinx_rtd_theme'
    b. line 52: copyright = '2016, CyVerse'
    c. line 53: author = 'your_name'
7. Build the tutorial:
    ```
    $ make html
    ```
8. Your HTML site will be in the _build directory that has been created. 
9. Push the tutorial to a repo in Github.
9. In the GitHub repo settings, under 'Integrations & services' go to 'Add service' and add 'ReadTheDocs'
10. Go to http://readthedocs.org/ sign-in; follow the directions to add/create a project and use your repo at the URL to import from. 
11. You should now have a site for your documentation. 

## Other tutorial elements

**Workflow Diagrams:** Version controlled workflow diagrams can be built using [yEd](http://www.yworks.com/products/yed).
 
