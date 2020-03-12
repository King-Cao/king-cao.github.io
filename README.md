# Sway01 Blog
This is one personal blog. Welcome to this New World! 



## Components

1. Jekyll + Github Page
2. Forked [Hux Theme](https://github.com/Huxpro/huxpro.github.io)




## Local Environment Setup
My laptop's OS is macOS Catalina 10.15.3, so I need to install Homebrew first to install missing packages for macOS.

0. Homebrew (https://brew.sh/)

1. Jekyll 4.0 (https://jekyllrb.com/docs/installation/macos/)

  > Recommend to install ruby with **rbenv** to seperate with system ruby.

2. *NodeJS* (optional) (https://nodejs.org/en/download/)

After above packages are installed, fork this project and run below command to start:

```shell
bundle exec jekyll serve --watch
```

Then you can access local blog via  http://127.0.0.1:4000



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

