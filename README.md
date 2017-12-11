
# cnmozzie.github.io
This is a website supported by github pages and jekyll.

## Preparation

 - [about github pages](https://pages.github.com/)
 - [about jekyll](https://jekyllrb.com/)
 - [about markdown](https://en.wikipedia.org/wiki/Markdown)
 - [about git and github](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
 - [about bootstrap](https://getbootstrap.com/docs/4.0/getting-started/introduction/)
 - [about fontawesome](https://fontawesome.com/icons?d=gallery)

If you come with any problems, report an issue [here](https://github.com/cnmozzie/cnmozzie.github.io/issues).

## Getting start

1. install jekyll and create a new Jekyll site at `./iontrapnet.github.io` by running ```jekyll new iontrapnet.github.io```
2. move to the project folder and run ```git init``` to build a Git repository
3. run ```$ git remote add origin git@github.com:iontrapnet/iontrapnet.github.io.git``` and ```git push -u origin master``` to connect with the remote repository on Github
4. Now you should have a github page on [https://iontrapnet.github.io](https://iontrapnet.github.io)

## Customization

Jekyll use a default theme called minima, we will overriding theme defaults by [this guide](https://jekyllrb.com/docs/themes/#overriding-theme-defaults).

### Global setting

We add css and javascript by overriding `_includes/head.html`.

 - We use bootstrap css by adding code ```<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">```
 - We use fontawesome icons by adding code ```<script defer src="https://use.fontawesome.com/releases/v5.0.0/js/all.js"></script>```
 - We add costumer css in `assets/main.scss` where we first import css from minima theme
 - We render the LaTex in the post by adding code ```<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>```
 
### Change the default layout

We first define a wrapper class in `main.scss` as a container. The whole content will show on this wrapper. Then we divided the page to a header, a footer and a section. Their position are defined in `main.scss`. 

We modified `_includes/header` and `_includes/footer` to change the content of header and footer. 

### Change the home layout

We modified `_layouts/home.html` to change the home layout.