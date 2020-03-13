# Sway01 Blog
This is one personal blog. Welcome to this New World! 



## Components

1. Jekyll + Github Page
2. Forked [Hux Theme](https://github.com/Huxpro/huxpro.github.io)




## Local Environment Setup
For macOS:

0. Install Homebrew (https://brew.sh/)

   ```shell
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
   ```

1. Install **ruby** with **rbenv**

   ```shell
   # Install rbenv and ruby-build
   brew install rbenv
   
   # Set up rbenv integration with your shell
   rbenv init
   
   # Check your installation
   curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
   
   # !!! RESTART TERMINAL FIRST BEFORE RUN BELOW COMMAND !!!
   rbenv install 2.6.3
   
   # Add gem path, gem is under $HOME/.gem/ruby/X.X.0/bin. Replace X.X.0 with your true folder name
   echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.bash_profile
   
   ```

2. Install [bundler](https://bundler.io/)

   ```shell
   gem install bundler
   ```

3. fork this project

   ```shell
   git clone https://github.com/kingcpro/kingcpro.github.io.git
   ```

4. use [bundler](https://bundler.io/) to install necessary packages

   > bundler will use Gemfile to manage dependencies , Gemfile.lock will keep all installed dependent packages. 
   >
   > Github Pages use jekyll 3.8.5 while latest version is 4.0.0, so use bundle to keep same build environment with Github!!

   Gemfile is simple, only need to contain below two lines:

   ```shell
   source 'https://rubygems.org'
   gem 'github-pages', group: :jekyll_plugins
   ```

   Command to install all necessary packages:

   ```shell
   cd kingcpro.github.io
   bundle update
   ```

5. Install *NodeJS* (optional)

   Download package from [offcial portal](https://nodejs.org/en/download/) to install. We will need it to minify css file if necessary.

6. After above packages are installed, run below command to start:

   ```shell
   bundle exec jekyll serve --watch
   ```

   > --watch will reload pages after modified

7. Then you can access local blog via  http://127.0.0.1:4000

   

## FAQs

### 1. How to change the layout?
The mainly css file is css/hux-blog.min.css, it's source file is css/hux-blog.css. You can change css/hux-blog.css and use node-minify to generate it by manually.
```shell
npm install minify

# for npm >= 5.2.0
npx minify css/hux-blog.css > css/hux-blog.min.css

# for npm < 5.2.0
$(npm bin)/minify css/hux-blog.cs > css/hux-blog.min.css
```



### 2. Your site is having problems building: Unable to build page. Please try again later.

You will receive an email from github which said above error. The main problem is that your local build environment is different with github pages' environment. Please use bundler to setup local build environment to keep same as github pages' one.  

If you still have issue, please check [official troubleshooting page](https://help.github.com/en/github/working-with-github-pages/troubleshooting-jekyll-build-errors-for-github-pages-sites).

>  github pages dependency version: https://pages.github.com/versions/



