Official Inquiries collects, preserves and presents key document from official inquries in a useful and usable form.

How to contribute reports
============================

## Create a GitHub account

## Create a repository
* GitHub’s instructions for creating a repository are available [here](https://help.github.com/articles/create-a-repo/)
* Naming your repository:
  * When choosing a name for your repository, the convention we use is [name of inquiry body]-[date (yyyymmdd)]-[title].
  * Each word should be separated with a dash “-” for easy reading.
* How to structure your repository
  * Our repositories are structured as follows:
  * [repository]
    * archive
      * [archive of original source documents]
    * scripts
      *README.md (detailing any important scripts used to create the repository)
    * text
     * [text extracted from source documents]
    * README.md
    * Datapackage.json
  * To see an example, have a look at our repository on the Senate PSI report on the 2008 financial crisis [here](https://github.com/official-inquiries/senate-psi-20110403-wall-street-and-the-financial-crisis).

## Using Git to sync your repository with GitHub
* After creating the repository on GitHub, you will need to clone it to your computer. This can be done by navigating to the directory where you want to clone the repository and using the command `git clone [url of repository]`.
* Then, you can make changes to the contents of the repository on your computer. When you create a new file, use the command `git add [file path]`to add it to the list of files you would like to commit.
* When you are happy with your changes to the repository, use the command `git commit` to commit them. Don’t forget to add a brief note about the changes you are committing.
  * The formatting conventions we use for the note are [nature of note][size of changes][brief description]
  * For example: `[archive][l] added archive of original reports` to denote that you made a large change to the archive section, by adding the original reports to it.
* To sync your changes with the GitHub repository, use the command `git push` to push your changes from your local repository to the online version.
* Storing large files:
  * Sometimes, you will need to upload large files (ie larger than 50mb) to GitHub. It is not advisable to simply upload such large files as they are, so it is important to use git’s large file storage when doing so.
  * GitHub provides its own instructions on how to use lfs [here](https://github.com/github/git-lfs)
* Other important commands:
  * git status: at any point during the process, you can use `git status` to check the status of your local changes.
  * git pull: use `git pull` to pull changes made to the online repository and bring your local version up to date with them.

## Writing a README.md
* The purpose of the README.md is to give a basic outline of what the report contains
* The README.md should be written in _markdown_. A guide to _markdown_ and its syntax can be found [here](https://daringfireball.net/projects/markdown/).
* Have a look at some of the README.md files in the existing official-inquiries repositories to get an idea of how to structure it. Generally, it should contain:
  * An introductory paragraph, explaining what the report is.
  * A summary of the report’s contents.
  * Where you found the materials.
  * What the license for the materials is.

## Writing a datapackage.json
* The datapackage file is a convenient means of storing data about the repository.
* A guide to its use can be found [here](http://dataprotocols.org/data-packages/)
* Have a look at the datapackage.json for the Senate PSI financial crisis report [here](https://github.com/official-inquiries/senate-psi-20110403-wall-street-and-the-financial-crisis/blob/master/datapackage.json) to get an idea of the syntax and contents you will need.

## Extracting text from a .pdf
* Usually, you will have to extract text from a .pdf file of a report to get text for your _text_ directory.
To do this, we use PDFMiner
* Instructions on how to install and use PDFMiner can be found [here](http://www.unixuser.org/~euske/python/pdfminer/)

## Raising issues on GitHub
* You can raise any project issues on GitHub using the issues tab on the web interface
Or, help solve any issues listed there

Contributing to existing repositories
===========================

## Converting archive files to text
* The most simple way to help is to take files in the /archive/ directory of a repository, convert them into .txt format, and place them in the /text/ directory. We currently do this using PDFMiner. Instructions on how to install and use PDFMiner can be found [here](http://www.unixuser.org/~euske/python/pdfminer/)

## Tidying text files into markdown
* The next step is to convert these text files to markdown so that they can be put up on the website.
* A file with the `.md` extension should be added to the repository's /markdown/ directory. If the report has multiple volumes, the file should be placed in an appropriate subdirectory.
* Each text file will vary in how it is untidy, but the basic prerequisites of a web-ready file are:
  * Working headings and subheadings with a table of contents at the top
   * Headings will need to be added in markdown, with `#` for a main heading, `##` for a subheading, etc.
   * A table of contents will need to be added at the top, by adding the code `* TOC` and then `{:toc}` on the next line. This will automatically generate a table of contents for the headings you have added.
  * No superfluous text
   * The most obvious candidate for deletion is the report's own table of contents, which will not be useful
   * Page numbers and page names (for example, where the title of the report is printed at the bottom of every page) should also be removed if possible
   
    
