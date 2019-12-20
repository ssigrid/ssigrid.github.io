---
layout: default
---
## About the Course
Command Line Tools for Linguistics, or KIK-LG219 is an introduction to the UNIX comman line environment. With many practical exercises the learning curve is pretty steep. Some examples of what one learns on the course include: 

* Use of regular expressions.
* The basics of processing corpora.
* Installation of programs.
* Basic script writing.
* Use of remote servers.
* The basics of GitHub Pages.


### Week 1: Introduction to Command Line Environments
In the first week we took a look at some backround knowledge, such as what is is Linux, Unix, and an operating system. For the practical part we set up the command line environments and started operating in them. 

Some of the basic comands, which I learned during week 1:

| command | example	      		| what does it do			 	|
| ------- | ---------------------------	| --------------------------------------------- |
| `mv` 	  | `mv file 1 file2` 		| moves or renames files			|
| `wget`  | `wget <url>`  		| downloads files from the Internet		|
| `echo`  | `echo "Hello, World!"`	| prints the argument				|
| `touch` | `touch <newfilename>`	| creates a new file or changes its timestamp	|


### Week 2: Navigating a UNIX System
Copying, moving, and removing directories, checking and changing permissions, controlling processes and working on remote servers. These are some of the practical things I either learned or revised during the second week of the course. In addition to this we learned about. 

Perhaps the most useful lesson of the week was the one on permissions of files. For me this meant checking permissions and changing them with the command `chmod`. This has also come with the great skill of using Google to check the correct options for this or any other command I've used. Below chmod command which grant execution permissions only for the owner. The u stands for user and x for execution permissions.
`chmod u+x`


### Week 3: Basic Corpus Processing
Week 3 included more theory, since we learned about binary encoding. For the practical part we used UNIX command meant for processing text files and searching in them. 

The most intresting lesson of the week was how to use egrep to count word frequencies. This is done by `egrep <pattern> <file> | wc -l`. The patter could be for example "^aA", which would mean word starting with upper or lowercase a. `wc -l`counts the lines, which would be the matching patterns. 

Pipeline commands are something I need to work on, but after this week I at least can handle the very basics. 


### Week 4: Advanced Corpus Processing
Carrying on where week 3 left off, in week 4 we learned more complex pipelines and the use of command sed. We also created a freqlist file from a gutenberg book. This was done by command `cat <file.txt> | tr -s '\n\t\r' '\n' | tr -dc "A-Za-z0-9'\n" | sort | uniq -c | sort -nr`

The first tr parameter with opiton -s replaces the listed characters with new lines. The second tr with -dc deletes the characters which are not in the list. The sort parameter without options puts the file into alphabetical order. Uniq -c counts thethe occurenses of a word together and finally sort -nr sorts the file in order from highest frequency to lowest.  

Week 4 feels familiar, however, as I stated below Week 3, pipeline commands, especially the more complex ones, are still difficult for me. I could probably get one working, but it would take time and great effort.


### Week 5: Scripting and Configuration Files
Scripting and configuration files seemed to be the hardest part of the course for me. Whoever learning how to edit environment variables was great fun as well as usefull for me later on. For example I've had to edit the PATH variable in .bash_profile more than once. 

In Week 5 we used if statements. As a basic example of this: 
````
a=1
b=2
if b > a:
	print("b is greater than a")
```
If this if statement were run, it would print out the tezxt "b is greater than a", since a and b have been defined and the if statement is truea according to the given parameters. This command could also have an addition of else, which could have an print command for situation where b = a or b < a. 


### Week 6: Installing and Running Programs 
Week 6 was for installing programs like NLTK and blliparser, which I had some trouble with. We also used sudo, which meant setting a root user, and learned to write and run Makefiles, which were rather easy to use, if one does not count the actual scripting done in them. 

```
bothfiles: file1 file2
        cat $^ > $@
```
A Makefile example, where cat command is used to make bothfiles file, where file 1 and 2 are concatenated to one longer file. 

<p align="center">
<img src="assets/images/scripting.jpg"/>
</p>
_Pictured: Real-life footage of bllipparser and I_.

### Week 7: Version Control
Week 7 is where we learned version control and installed Git. I personally learned everything I now know about GitHub during this week, since I had never used it before. I've got pushing and pulling under control, but for example branching is still a mystery to me. 

Creating a branch:
```
$ git branch <branch_name>
```
Switching to a branch:
```
$ git branch <branch_name>
```
Pushing a branch:  
```
$ git add <branch_name>
$ git commit -m "edited branch"
$ git push -u origin <branch_name>
```
Merging a branch
```
$ git checkout master
$ git merge <branch_name>
$ git push origin master
```

### Final Week: Jekyll and Github pages
With the Final Assigment came installing Jekyll and learning how to use GitHub pages. After wasting a whole day by trying to get the ruby to work, I learned perhaps the most important lesson of the course: one should update their software every now and then. 

Compared to the mess with that learning to use Markdown files has not only been fun but also nice and easy. In fact I'm thinking of learning more about GitHub pages in the future. I imagine this means that I will keep using my new best friend, the code `bundle exec jekyll serve`.
