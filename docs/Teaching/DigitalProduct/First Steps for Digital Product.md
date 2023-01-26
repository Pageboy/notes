## Introduction

1. You will learn how to style your own web site by creating a recipe web site with at least 5 recipes.
2. You will take these five recipes and create an enhanced eBook

## Think of a theme for your recipe product

You need to choose 5 or more recipes by theme, so that you can create a web site and a Recipe eBook. You need to find some logical reason to build this small collection. Examples might be:

- Favourite recipes from Scotland
- Seaside Recipes
- Pies and Pastries
- 5 Pasta Recipes from Italy
- Recipes from the Victorian Kitchen
- 5 Puddings

Suggest some recipe book titles that include 5 simple recipes

Still short on ideas? Go over to the [openAI playground](https://beta.openai.com/playground) here and create an account. Then simply ask for some ideas. Look what I got!

![[Screenshot 2023-01-26 at 15.46.47.png]]

You need to decide on a title (with an optional sub-title) and write an introduction (about 150 words) of the contents. The recipes can be from anywhere, or your own. You will work the title into an ebook cover (the second assignment) and the introduction and the image of the cover will go onto the web site. 

The theme is most important. You can think of a title for your product at the same time.

- The recipes should be in the public domain
- the images that you use should also be in the public domain or using a Creative Commons attribution licence

### Collect the recipes 
use any note or word processor to keep them somewhere. You can copy / paste from web sites.
There are a lot of links to web sites on moodle

## The web site
This will be hosted and be a live site.

### YouTube playlist
I have put together a YouTube playlist which covers all of this details here.

<iframe style="max-width:100%;" width="720" height="405" src="https://www.youtube.com/embed/videoseries?list=PL45AD0XX_t1IEkygJ45UErWNcXa3YblyT" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


For the following processes I suggest that you use *Google Chrome* rather than *Apple Safari*

- Create a free account on GitHub.com (You may already have an account)
- Create a new repository from this template
- Once logged in go to this site in another tab: https://github.com/Pageboy/student_recipes
- see the green button `Use this template` Hit that and `Create a new repository`

- You will need to name this repository. Remember what you called it
- make sure you make this *Public*

You should now have a repository built on this template. You can leave this site open for moment . Your site assets are stored here but the site will be built from these files at **Netlify**.

![[Screenshot 2023-01-13 at 10.11.59.png]]


## Steps to get working with this template

### In Github

- Create an account on [GitHub][6a43c620]
- After creating an account on GitHub, you first need to create new repository by cloning this template: https://github.com/Pageboy/student_recipes
- You will now have a name for the repository and your GitHub username.
- Keep the GitHub window open in your browser (because we will need to come back to this in a short while)

  [6a43c620]: https://github.com "Go to the Github web site"

### Netlify is where we build your site

- In another browser tab, go to [netlify.com](https://www.netlify.com)
- **Login** with your GitHub credentials
- create a `New Site with Git`
- put in the name of the GitHub repository that you created above.
- Your GitHub repository will be built as a web site with a randomly chosen URL. Something like `juicy_peach_9965.netlify.app`.
- Now change the first part of this URL to something that you want. In other words, the juicy_peach_9965 part can change to something that has not been taken (eg: *mytastyrecipes.netlify.app*)
- Keep the Netlify window open and do not sign out

### GitHub is where the files are located and updated.

Netlify needs to have permission to take your files from GitHub and build the site every time you make changes. Netlify needs 2  codes - an **ID** and a **secret**.

Now in Github, go to your GitHub account and on the left side at the bottom find Developer settings and then see `OAuth Apps`. In here you need to add a new app and after putting in the details (enter the complete URL of your site) you should be provided with a **Client ID** and a **Client Secret**. We need these 2 items in Netlify. Now go back to the Netlify window.

You will also need to enter the `callback` term in the last box. This should be exactly like this:

`https://api.netlify.com/auth/done`

Here is what that page will look like after you enter the details
![[oauth 1.png]]

### In Netlify

I hope you can see why I suggested keeping the 2 browser windows / tabs open now.
- Go to Site Settings > Access control > Scroll to the bottom and select OAuth > GitHub.
- Paste in here the 2 codes from GitHub, **Client ID** and **Client Secret**. Once you have entered these codes we need to go back to GitHub to make some essential settings so that the system knows about your chosen URL / web site name. 
  
So back to the GitHub window then.

### Back in Github you can now make some basic edits

You can edit a few settings directly in GitHub so we can begin using the CMS for the other settings. The minimum settings that need changing are in 2 files:

#### In the Admin folder

In the _admin_ folder find `config.yml` You need to edit some lines in this file.

```YAML
backend:
  name: github
  repo: githubusername/yourrepositoryname # Path to your GitHub repository
  branch: master # Branch to update (master by default)
  site_domain: yoursite.netlify.app #Your site on netlify
  use_graphql: true

publish_mode: editorial_workflow
show_preview_links: true
display_url: https://yoursite.netlify.app
```

Wherever you see `yoursite` change to the name of your site created on Netlify.

Also on **line 3** change the repo path. This will be the GitHub username followed by your repository name.

### Site configuration

Open `_config.yml` in a text editor to change some settings.

Change these variables in `_config.yml`:

```YAML
url: "https://yoursite.netlify.app"   #change this to yours
repository: yourusername/yourrepository
title: Your recipe collection
recipemenu: false # you can change to true and a menu of all recipes will appear
editbutton: false # you can navigate to edit your site by going to https://yoursite.netlify.app/admin
# change the above to true and an admin button will appear in your footer
searchbutton: false # you can have a search feature by adding this button to the footer
# change the above to true and a search button will appear in your footer
```

## Usage

`Jekyll` is a system for building and editing static web sites; meaning that it does not need a database for the content. Content can be added with a simple text language called `Markdown`. You can explore and learn **Markdown** here:

https://commonmark.org/help/tutorial/

Although the main content is built with markdown and converted to HTML automatically, you won't need to actually write in markdown, unless you want to. The site is set up to use a content management system (CMS) so that posting new content and setting up the site can be done through a web interface.


### Using the CMS to edit your site

Once these changes have been made in Github, you can now go to your new site and begin to add some further details through the CMS. You may need to wait for 5 minutes.

Your site will be live but there will be no styling; your task is to edit the CSS, and add your recipes and introduction text.


## HTML and CSS

right now your site doesn't have any styling at all so we need to take a copy of one of  your recipes and  go through a number of exercises to edit the stylesheet.

Find the program call *SiteSucker* (you can download a copy from moodle)

Paste in the URL box your live web site. This will be something like **myrecipes.netlify.app**

Press return.

Your complete web site will be saved in the downloads folder under the name *us.sitesucker.mac.sitesucker*. In that folder will be your site named as the url of your site. Move this folder out of the downloads folder and into your project space for your work (maybe in a Google Drive folder)



