---
title: Build a personal website with Jekyll and GitHub pages
layout: post
date: 2019-08-23 14:08
image: /assets/images/GitHubJekyll.png
headerImage: true
tag:
- github pages
- jekyll
- portfolio
- website
star: false
category: blog
author: mayokunadeniyi
description: How to build a personal website using Jekyll and GitHub pages.
---


# Introduction
It is the year 2019 and having a personal website is, if not compulsory, one of the best things to have as an individual more specifically, as a Software Developer. Be it [Medium](https://medium.com/), [Hashnode](https://hashnode.com/), [Dev.to](https://dev.to/) or any other online publishing platform, having a personal website helps you create an online presence for yourself. 

A personal website is an important tool if you belong to a profession that requires a showcase of your portfolio. You could showcase things you've built, projects you've worked on, manage a blog, add information about yourself and a whole lot more on your personal website.

If only we could wield our wands and build a stunning website with just a simple wave :sweat_smile: I mean, not all of us write HTML, JavaScript and CSS. Thankfully, we've got something close to the wand in the form of [Jekyll](https://jekyllrb.com/) and [GitHub Pages](https://help.github.com/en/articles/what-is-github-pages) :muscle:

---

### What is Jekyll and GitHub Pages ?
>**Jekyll** is a simple, blog-aware, static site generator for personal, project, or organization sites. 

>**GitHub Pages** on the other hand is a static site hosting service designed to host your personal, organization, or project pages directly from a GitHub repository.

---

# Getting Started
You'll need to have a [GitHub account](https://github.com) to get started with GitHub Pages as we will be hosting our website's files in a GitHub repository.

---

## Step 1: Setting up your environment
Some operating systems come pre-installed with these tools, but if this isn't true for you or to be sure, do the following:
* Install [Ruby](https://www.ruby-lang.org/en/downloads/)
    * Check if it's properly installed with `ruby -v ` in terminal or in command prompt
    <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/1.png?raw=true" style="width:80%"></a></p>
* Install [RubyGems](https://rubygems.org/pages/download)
    * Check if it's properly installed with `gem -v` in terminal or command prompt
    <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/2.png?raw=true" style="width:80%"></a></p>
* Install [GCC](https://gcc.gnu.org/install/) and [Make](https://www.gnu.org/software/make/)
    * Check using `gcc -v`, `g++ -v ` and `make -v` in terminal or command prompt
    <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/3.png?raw=true" style="width:80%"></a></p>

**For detailed install instructions have a look at the guide for your operating system. [macOS](https://jekyllrb.com/docs/installation/macos/), [Ubuntu Linux](https://jekyllrb.com/docs/installation/ubuntu/), [Other Linux distros](https://jekyllrb.com/docs/installation/other-linux), [Windows](https://jekyllrb.com/docs/installation/windows/).**

---


## Step 2: Install Jekyll and [Bundler](https://rubygems.org/gems/bundler) Gems

Install Jekyll and Bundler using `gem install jekyll bundler` in your terminal or command prompt. This command installs both Jekyll and Bundler.

After installation, check if Jekyll and Bundler were successfully installed using `jekyll -v` and `bundler -v`
 <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/4.png?raw=true" style="width:80%"></a></p>

 ---

## Step 3: Setup your personal website locally

* Go to [Jekyll Theme's website](http://jekyllthemes.org/) and select a theme you love
* Download and extract the theme's source code from the Jekyll Theme website to your computer
* Open a new terminal or command prompt window and navigate to the directory where you extracted your downloaded theme.
* In the directory containing the source code of your chosen theme, run `bundle exec jekyll serve`;
    * If you get an error when trying to do this, try the following:
        * `gem install pygments.rb`
        * `gem install bundler`
        * `bundle install`
    * After trying the above commands, run `bundle exec jekyll serve` again or return to the previous steps 
* After the command runs, go to your web browser and type `http://127.0.0.1:4000` which is your local host and hit enter, to see your website locally.

---

## Step 4: Editing the website 
Most of the time, the developer that built the theme you've chosen instructs you on how to add your information, add new blog posts, images, projects e.t.c These instructions are mostly found in the `README.md` file of the theme's repository on GitHub. 

I recommend using [Visual Studio Code](https://code.visualstudio.com/) for this but feel free to use any tool you find convenient. Open the project in your code editor, edit the theme by adding your information. You can always check `http://127.0.0.1:4000` to see any new changed you made after saving.

**Note: [Markdown](https://www.markdownguide.org/) is supported here so feel free! You could also learn how to use Markdown [here](https://www.markdownguide.org/)**

---

## Step 5: Hosting on GitHub 
* Create a new repository to host your website. The naming convention for the repository should follow the order **"YOUR_GITHUB_USERNAME" + ".github.io"**. For example, my GitHub username is **"mayokunthefirst"**, i'll name the repository **"mayokunthefirst.github.io"**. 
    * In the option where you're asked if you want to initialize the repository with a `README` when creating the new repository, don't check the box.
* Install [Git](https://git-scm.com/)
    * Check if you have Git installed using `git --version`
     <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/5.png?raw=true" style="width:80%"></a></p>
* After saving the changes you made to the website locally, open a new termainal or command prompt window and navigate to the directory where your website is on your local machine. 
* Initialize the directory with `git init` 
* Add the remote `git remote add origin https://github.com/YOUR_USER_NAME/YOUR_USER_NAME.github.io.git`
    * <p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/6.png?raw=true" style="width:80%"></a></p>
* Add all untracked files to git with `git add .`
* Commit your change with `git commit -m "Initial Commit"`
* Push your website's files to the GitHub repository you created with `git push -u origin master`
* After a successful push to GitHub, navigate to the repository on GitHub  to confirm. The repository have a name that follows **"YOUR_GITHUB_USERNAME" + ".github.io"** as described above. 

---

## Step 6: Verify your website is live
After following the above steps, open a new tab in your browser and type in **"YOUR_GITHUB_USERNAME" + ".github.io"** as described above. i.e **"mayokunthefirst.github.io"**, your website should be visible now :star:!

---

## Step 7: (Optional) Add a custom domain for website
If you own a custom domain, you can redirect it to your GitHub Pages website so it has a much more personal feel.
* Go to your website's repository on GitHub and go to **Settings -> GitHub Pages** add your customdomain and save.
<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/JekyllGitHub/7.png?raw=true" style="width:80%"></a></p>

* Next, go to your hosting provider and find the Manage DNS section. Add two records there.
    * Add a ***A record*** that points to `192.30.252.153`
    * Add a ***CNAME record*** that points to your GitHub Pages site **"YOUR_GITHUB_USERNAME" + ".github.io"**
    * Wait for changes to take effect and you’ll be able to access your personal website using your custom domain address
    

Should incase you run into any errors while trying to get this done, do send me a DM on [Twitter](https://twitter.com/mayokunadeniyi). Thank you for your time :thumbsup:












