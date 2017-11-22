### Directory Structure Best Practice
Time spent at the beginning of the project to define folder hierarchy and file naming conventions will make it much easier to keep things organized and findable, both throughout the project and after project completion. Adhering to well-thought out naming conventions:

* helps prevent accidental overwrites or deletion
* makes it easier to locate specific data files
* makes collaborating on the same files less confusing

### File naming best practices

Include a few pieces of descriptive information in the filename, in a standard order, to make it clear what the file contains. For example, filenames could include:

* experiment name or acronym
* researcher initials
* date data collected
* type of data
* conditions
* file version
* file extension for application-specific files

#### Consider sort order:

If it is useful for files to stay in chronological order, a good convention is to start file names with `YYYYMMDD` or `YYMMDD`.

If you are using a sequential numbering system, use leading zeros to maintain sort order, e.g. `007` will sort before `700`.

Do not use special (i.e. non-alphanumeric) characters in names such as:  
```" / \ : * ? ‘ < > [ ] [ ] { }  ( ) & $ ~ ! @ #  % ^   , '```

These could be interpreted by programs or operating systems in unexpected ways.

Do not use spaces in file or folder names, as some operating systems will not recognize them and you will need to enclose them in quotation marks to reference them in scripts and programs. Alternatives to spaces in filenames:

* Underscores, e.g. file_name.xxx
* Dashes, e.g. file-name.xxx
* No separation, e.g. filename.xxx
* Camel case, where the first letter of each section of text is capitalized, e.g. FileName.xxx
* Keep names short, no more than 25 characters.

### File Versioning Best Practices

File versioning ensures that you always understand what version of a file you are working with, and what are the working and final versions of files. Recommended file versioning practices:

* Include a version number at the end of the file name such as v01. Change this version number each time the file is saved.
* For the final version, substitute the word FINAL for the version number.
* Take advantage of the versioning capabilities available in collaborative workspaces such as github OSF, Google Drive, and Box.
* Track versions of computer code with versioning software such as Git, Subversion, or CVS.

### Directory Structure Best Practices
Directories can be organized in many different ways. Consider what makes sense for your project and research team, and how people new to the project might look for files.

Once you determine how you want your directories to be organized, it is a good idea to stub out an empty directory structure to hold future data, and to document the contents of each directory in a readme file.

Directory Best Practices

* Organize directories hierarchically, with broader topics at the top level of the hierarchy and more specific topics lower in the structure.
* Group files of similar information together in a single directory.
* Name directories after aspects of the project rather than after the names of individual researchers.
* Once you have decided on a directory structure, follow it consistently and audit it periodically.
* Separate ongoing and completed work.

### Sources
http://guides.lib.umich.edu/datamanagement/files
