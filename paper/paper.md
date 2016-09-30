## Abstract

This is a project for [Statistics 159: Reproducible and Collaborative Data Science][stat159]. The purpose of this project is to explain some of the common tools that are used in data science, that not only make the data scientist’s life easier, but also help others who are trying to understand or replicate their projects. The tools I go over in this paper include Makefile, Git, GitHub, Pandoc and Markdown.

[stat159]: http://gastonsanchez.com/stat159/

---

## Introduction

As noted in the abstract, the tools I write about in this paper are: _Makefile, Git, GitHub, Pandoc and Markdown_. In putting together this project, I used each one of these tools in their respective manners. I used _Markdown_ to format this paper for the purpose of readability and the ability to incorporate links, photos as well as blocks of code. A _Makefile_ was used to put together the entire paper, meaning that it concats each of the sections to create a full-length paper. _Pandoc_ is used within the Makefile to convert the Markdown to HTML. I then used _Git_ to upload this project to _GitHub_, where it will be displayed to the world! If you didn’t understand any of that read on to learn what each of these tools do :) 

--- 

## Makefile

A _Makefile_ is a list of shell commands that is exectued within the shell itself. A Makefile is a great way to organize code compliation, and is a key tool for reproducible workflow. You can output almost anything within a Makefile, with common examples being html pages, md files and graphs. The output is produced via executing scripts that you have written, such as python and R scripts. Each command within a make file has two key file components: an object file and a source file. The source file is often the script, and the object file is the output of that particular script. The object file is the *target*, while the source file is the *dependency*. Below the target and dependencies are the system command(s), which specify how to interact with the dependency to product the target. 

`$ target: dependencies`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`system command(s)` 

Makefiles are executed just by calling `make` from the command line. 

Some key benefits of haivng a Makefile include: 

 * Instead of having one long and extensive script that pulls data, analyzes it, and produces an output, you can break up your code by task and then compile it with a Makefile. This makes it much easier for others to understand your code, and if a segment of the analysis needs to be changed it can be done so without altering other parts.  

 * You can separate your data analysis from the paper or document that describes the output of your analysis 

 * If you are analyzing data on a timely basis (for example, month by month) you can easily switch out the data input (the dependency) and then run the exact same code every month to produce the same output) 

---

## Git 
![][gitlogo]

_Git_ is an open-source version control system that is crucial for collaborating on projects. In a nutshell, Git is a command line tool that allows you to create repositories, access them from your local machine, make changes then push these changes to the online repository for other to access. Because of the way Git is structured, multiple individuals can be working on the same repository, and as long as their changes do not overlap, they can both contribute to the project (and if they are working on the same part, Git will warn you of this before you push your changes). Another major benefit of Git is it’s version control features—your versions are always stored locally for you to access, which is awesome if you mess up or accidentally delete a crucial function ;) This also means that there is very little you can’t do if you’re offline; you can commit your changes and then once you get a network connection you can push your changes.

The most used functions of Git during a project are the `pull`, `add`, `commit` and push features. To pull a project means to merge the copy online (the remote copy) with your local one (so if your collaborator made changes overnight, you can have the most up to date version to work with). Then you can edit your local copy of the script. Once you are done editing for the time being, you add your script to the staging area, commit the changes with a message of what you added, changed or removed, and then you can push your changes to Git! Simple and sweet.

Here's a walkthrough of some features you will more than likely use in a project if you're using Git:

#### Create a new repository
`$ git init`

#### Checkout a repository
`$ git clone /path/to/repository`

#### Update & merge
`$ git pull`

#### Add and commit
`$ git add <filename>'
'$ git commit -m "Commit message"`

#### Pushing changes
`$ git push origin master`

---

## GitHub
![][githublogo]

_GitHub_ is a Git repository hosting service. While Git works on the command line, GitHub provides a web interface for individuals and teams to access repositories and collaborate on projects.

To collaborate on a project, you just need to follow these [basic steps][githubsteps]:

1. Fork the target repo to your own account.
2. Clone the repo to your local machine.
3. Check out a new “topic branch” and make changes.
4. Push your topic branch to your fork
5. Use the diff viewer on GitHub to create a pull request via a discussion.
6. Make any requested changes.
7. The pull request is then merged (usually into the master branch) and the topic branch is deleted from the upstream (target) repo.

For this project, the role of GitHub is to showcase this project, and to allow anyone to view my work, and even add to it if they so choose. This project will be uploaded to a repository, and will include a README to explain how to navigate this project so that anyone can do it!

---

## Pandoc
![][pandoclogo]

_Pandoc_ is a tool that allows you to convert files from one markup format into another. Some examples of this include converting documents in markdown, textile, HTML, LaTeX to HTML formats, Microsoft Word, TeX formats and PDF. 

The simple conversion is done on the command line by typing: 

`$ pandoc –output document.docx document.text` 

It's as easy as that! 

For this specific paper, I used the command line

`$ pandoc paper.md -f markdown -t html -s -o paper.html`

---

## Markdown

![][markdownlogo]

_Markdown_ is a text-to-HTML conversion tool for web writers. Essentially, Markdown is [two things][markdownexplanation]:

1. A plain text formatting syntax
2. A software tool that converts the plain text formatting to HTML

The beauty of Markdown is it’s readability. The language doesn’t even look like it has been marked up in the final output! 

---

## Resources

### Makefile
* [Makefile Tutorial][mrbook]
* [GNU Make for Reproducible Data Analysis][gnumake]

### Git
* [What Is Version Control][versioncontrol]
* [Git Guide][rodgerdudler]

### GitHub
* [TechCrunch: What Exactly Is GitHub Anyway][techcrunchgithub]
* [How to Collaborate On GitHub][collaborateongithub]

### Pandoc
* [Pandoc Intro][pandoc]

### Markdown
* [Markdown Intro][markdownexplanation]

---

## My Thoughts

The easiest part of this project was typing it up in Markdown, because once you know the formulas for how to make your text look pretty, it’s very simple to replicate it throughout your project and in other projects. Another somewhat easy facet of this project was using Pandoc to convert the markdown file to html because it is just a simple line of code in the Makefile. I have used Git/GitHub before for projects, so this part was also fairly easy for me.

The more challenging part of this project was formulating the Makefile, purely because I have never worked with Makefiles before. Continuing though, however I think that Makefiles are incredibly useful for reproducible projects and look forward to implementing it in future projects. 

Initially I got stuck using Git to upload projects, simply because of the pull/push phenomenon (always pull before you push when collaborating!) I also got stuck with indenting and code blocks... But I learned that to indent something you use '& nbsp ;' in the Markdown file. Another semi tricky part was getting the spacing exactly how I wanted it. It took a few trials and errors before this beautiful paper was produced!

The most time consuming part of this project was deciding how to explain what each of the functions are (Makefile, Git, GitHub, Pandoc, Markdown) because I wanted whoever reads this project to understand the concepts of these tools, and also understand how they can implement them themselves. I also sifted through multiple resources to find the most helpful ones in understanding these tools. Another time consuming asset was formatting it precisely the way I wanted it to look in Markdown

I did not collaborate directly with anyone else on this project, but had some help from a classmate in formatting my Makefile as well as referred to notes from class and read multiple online resources.

This project in total took approximately eight hours over the course of a week.


[gitlogo]: https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/git-logo.png
[githublogo]: https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/github-logo.png
[githubsteps]: https://code.tutsplus.com/tutorials/how-to-collaborate-on-github--net-34267
[pandoclogo]: https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/pandoc-logo.png
[markdownlogo]: https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/markdown-logo.png
[markdownexplanation]: http://daringfireball.net/projects/markdown/
[mrbook]: http://mrbook.org/blog/tutorials/make/
[gnumake]: http://zmjones.com/make/
[versioncontrol]: https://www.atlassian.com/git/tutorials/what-is-version-control 
[rodgerdudler]: http://rogerdudler.github.io/git-guide/ 
[techcrunchgithub]: https://techcrunch.com/2012/07/14/what-exactly-is-github-anyway/
[collaborateongithub]: https://code.tutsplus.com/tutorials/how-to-collaborate-on-github--net-34267
[pandoc]: http://pandoc.org/ 
 

---



## Conlusion

In conclusion, reproducible and collaborative data science is made *10x easier* with just a few simple tools that are fairly easy to learn. Markdown can be used to format papers and descriptions of projects and Pandoc can then convert this Markdown into another readable format such as pdf or HTML. A Makefile can automate all of that with just a few simple lines, and Makefiles allow others to reproduce your work quickly and easily. Git and GitHub interact with one another to easily update your project from your local computer, and then allows the rest of the community to raed, contribute to, or reproduce your work!

![][stat159-logo]

[stat159-logo]: https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/stat159-logo.png