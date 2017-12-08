# Data Driven Journalism

A template for transparent, accountable data driven journalism.

## Motivation


### Why make our work transparent?
* Encourage better documentation and code commenting, saving future you and others time when deciphering your code
  - you will find yourself examining your code more closely, and in doing so may discover errors before publication
* Build trust with readers - be accountable
* Educational (students and other journalists can view and learn)
* Catalyze new projects

### Why make a Data Driven Journalism Cookiecutter?

This [blog post](https://blog.ouseful.info/2017/01/25/data-journalism-units-on-github/) talks about tools in data journalism transparency with a great list toward the bottom with examples in practice. You'll see that there is no consensus as to how to share information, what information to share, and the format of that information, meaning that **each time you look at a project, you have to figure out where everything is, and what is available.**

### Benefits to standardizing project structure for transparency
* Less of a chore if how to organize and what to include has already been figured out
* Documented projects with consistent structure are easier
  - to refer back to,
  - to train new journalists,
  - for the public to explore and scrutinize

The current repository tries to construct an organized, standardized "Data Journalism Project" structure. The directory structure is partly inspired by: [Reproducible Science Cookiecutter](https://github.com/mkrapp/cookiecutter-reproducible-science) by [Mario Krapp](https://github.com/mkrapp), and [Data Science Cookiecutter](https://github.com/drivendata/cookiecutter-data-science) by [drivendata](https://github.com/drivendata).
Data Journalism stories tend to be one-offs, and difficult or impossible to replicate by inputting data from a different city or industry, for example, so creating a new cookiecutter with a new organization structure seemed to make sense to me, rather than applying one of these existing projects directly. I also wanted to make it as lightweight as possible, since it is already going to feel like a lot of extra work to implement, until it becomes more familiar and routine.

## Requirements
This template was created with
* cookiecutter 1.6.0
* python 3.6

Install `cookiecutter` via the command line with `pip install cookiecutter`

For more on cookiecutter, go [here](https://cookiecutter.readthedocs.io/en/latest/installation.html)

Other versions of Python have not been tested.

There are several ways to install python. [This link](https://cookiecutter.readthedocs.io/en/latest/installation.html) also has details on installing a python interpreter. Because I do a lot of data analysis, I use python that comes with the [Anaconda distribution](https://www.anaconda.com/download/) which supplies lots of other awesome stuff for free, including Jupyter Notebook which is a popular tool for stepping people through a data analysis project.  

A GitHub account, while not necessary to _use_ this cookiecutter, _is_ required to make your data journalism transparent and available for others to examine. For instructions on how to set up an account, go [here](https://github.com/).
You will also need [git](https://git-scm.com/downloads) and/or [GitHub Desktop](https://desktop.github.com/). If you're a git-beginner, I recommend the desktop. If you love command line, go ahead with git. 

## Usage
To begin a new data-driven journalism project, open a terminal, navigate to where you want the project to reside, and type:

`cookiecutter gh:jastark/cookiecutter-data-driven-journalism`

and then complete the following:

- `full_name`: e.g. `Jennifer A. Stark` (this will be used to populate the `AUTHORS` file)
- `email`: e.g. `jastark1@gmail.com` (will populate the `AUTHORS` file)
- `github_username`: e.g. `JAStark` (will populate the `AUTHORS` file)
- `project_name`: the name of the published story for easy cross-referencing, or, if you don't know it yet, something relatable. This text will populate the `README` file.
- `project_slug`: leave empty. It will create a project directory named using `project_name` with underscores automatically added between words.
- `short_description`: a short description of the Project. This text will populate the `README.md`
- `ddj_cookiecutter_version`: leave empty.
- `date`: leave as-is.

and the project structure will automagically be created for you (see below "Project Structure").

## Project Structure
```
.
├── .gitignore
├── AUTHORS.md
├── LICENSE
├── README.md
├── data
│   ├── external
│   ├── interim
│   ├── processed
│   └── raw
├── data-dictionary.md
├── figures
├── keys.txt
├── notebooks
├── references
└── requirements.txt

```
### .gitignore
This file is normally hidden from view. You can see it if you use [Atom](https://atom.io) text editor or if you type `ls -la` into the terminal.

Edit this file to include any additional files or directories you wish _not_ to publish to GitHub.

### AUTHORS.md
This will be automatically populated with the creators name, email address, and github account as per the inputs prompted above. There is also space for the by-line author (if different from the person who worked on the data part) and for additional supporting authors that you can edit manually.

### LICENSE
For your data-driven journalism project, this is set to the Creative Commons ShareAlike 4.0 International License. For more information on licenses, click [here](https://choosealicense.com).

### README.md
This will be automatically populated with the project name and the short description as per the prompts described above. It will also have a section on the origin of the cookiecutter and the license, with a link to the full text of the license within LICENSE.

This file should be edited to add relevant sections such as:
* [Links]() to the data*
* [Link]() to the published story
* Motivation for the project/story
* Data description
* **Non-technical description** of the process overall
  - where data came from,
  - how it was processed and analyzed,
  - any challenges or issues encountered along the way etc
  - findings

Data* greater than 100MB cannot be stored on GitHub, so alternative locations might be:
* Google Drive
* [data.world](https://data.world) where data can be stored for free
* Dropbox

*Shared data should always be anonymized.*

`README`, `AUTHORS`, and `data-dictionary` are markdown files. For more on how to write markdown, see [here](https://guides.github.com/features/mastering-markdown/).

### data
Here is contained four directories: `raw`, `interim`, `external`, and `processed`.
* `raw` is left alone. It contains the data in its rawest form from when it entered your hands. Data is only _read_ from here. Altered, processed versions are saved elsewhere.

    This directory is also automatically included in the `.gitignore` file, so that it will not be included when you publish the project on GitHub. This is because raw data is typically either too large for GitHub (limit of 100MB) or contains sensitive information that should not be published.

* `interim` includes data after stage(s) of cleaning or processing of some kind.

* `external` may include data that is required for data processing, such as shape files for location data analysis.
* `processed` contains data in its final form that is used for the final analysis.


### data-dictionary.md
This file will include a description of each column in each dataset, and a definition of terms.

### figures
If images are created (charts, maps) they can be stored in the `figures` directory.

### keys.txt
File includes any secret keys, passwords, or tokens used to access databases or APIs etc. This file is already included in the `.gitignore` file so that it will not be published on GitHub.

### notebooks
All commented Jupyter notebooks and scripts used to process and analyze data. It can be helpful to name your notebooks/scripts with numbers to help others understand the order in which to run them. Eg. `1_first_script.py`, `2_second_script.ipynb`.

### references
In this directory, you can put any documents that contributed to this project, eg data dictionaries, FOIA requests, manuals, notes, sources, articles, academic papers, and other explanatory materials. Anything you like that would be helpful to share.

### requirements.txt
Software, libraries, and languages, including versions, used in the creation of your project.

____
## Feedback
I am very interested in your feedback. If you find you're fighting with the project structure, or you find yourself always adding a specific additional folder, let me know.

Also let me know if this does not work for your data journalism at _all_. I made this based on my experience, and from what I have seen elsewhere (e.g. [here](https://blog.ouseful.info/2017/01/25/data-journalism-units-on-github/)). However, there are workflows and approaches to data journalism that I am not familiar with that may not be facilitated with this cookiecutter. Therefore, I can adjust this one, or perhaps make a whole new one! Again, let me know.

Finally, if you have feedback related to this documentation - if anything is unclear or lacking, do let me know.

Send feedback via GitHub Issues (a tab close to the top of this page) so that others can see what comments have already been made, and can see my responses :memo:

## Licence

This project is licensed under the terms of [MIT License](/LICENSE)
