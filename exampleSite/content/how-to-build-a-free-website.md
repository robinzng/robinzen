+++
Title = "Hello World and How I Got Here"
+++
### Hello World!

If you're reading this, that means I've successfully set up my free personal website!

In the process of creating my first website, I read a lot of online guides that basically made it seem like my only two options were: 

1. Pay for a service to make a custom website for me, or
2. Suck it up and go with a straight out-of-the-box solution.
      1. I also wasted a lot of time trying to hack out-of-the-box solutions to look the way I wanted them to, but this was inefficient and pretty buggy.


Thankfully, my good friend [Afnan](https://www.afnan.io), who is a genius at this sort of thing, told me about Hugo Themes. And now I'm here to teach you! 

This blog post is a guide to free web dev for everybody, even total beginners. Please [reach out](mailto:robinzeng1@gmail.com) if any of the steps are confusing, or if you have suggestions for improvement- I'm always looking to learn and grow!


### How to build a free website (for total beginners)
1. [A very high-level summary](/#a-very-high-level-summary)
2. [What to use and why](/#what-to-use-and-why)
3. [The code skeleton](/#the_code_skeleton)
4. [Deploying the code](/#deploying_the_code)
5. [Customizing your site](/#customizing_your_site)
6. [Publishing your site](/#publishing_your_site)

### A very high-level summary

Basically, all you need to create a website are:
* some set of instructions (the code), 
* somewhere to store the code (the repository), and 
* something to execute those instructions (the deployer). 

You'll also want a domain to make your website available to the world, but that's really the last step. Any website that tells you otherwise is not to be trusted. Domain names, like eulogies, should only be assigned at the end. 

### What to use and why

To build the code, we'll be using [Hugo themes](https://themes.gohugo.io/) as a (very robust) skeleton. Hugo themes are pre-built site themes that are incredibly customizable and relatively low maintenance. If you're happy with a theme as-is, the only language you need is Markdown. If you'd like to alter the skeleton, you just need some basic understanding of HTML and CSS and/or the ability to Google, copy-and-paste, and debug.

For editing code, I recommend downloading [Visual Studio Code](https://code.visualstudio.com/), which makes code a lot more readable than Notepad or Github (both of which, to be fair, work). Not a necessity, but free and incredibly helpful.

To store the code, sign up for a [Github](https://github.com/) account. You should also download the [desktop app](https://desktop.github.com/) for significant quality of life improvements. If you're new to the Git Desktop app, you can basically edit and save files locally on your computer, then commit and push the changes online whenever.

Finally, [Netlify](https://www.netlify.com/) is a solid deployer. It works seamlessly with Github, provides clear error messages that make debugging a breeze, and will easily link to whatever domain you do end up buying. Use your Github account to sign up and you're good to go! 

### The code skeleton

As mentioned earlier, [Hugo themes](https://themes.gohugo.io/) will serve as the scaffold for our code. I'm using ["Researcher" by Olivier Roques](https://themes.gohugo.io/hugo-researcher/), but all of their free options are fantastic. One piece of advice when choosing your own theme: prioritize features, not aesthetics. Trying to add a searchbar with code is orders of magnitude harder than changing the theme color from red to blue. Know which features are mandatory for your site to function fluidly, and look for those in the site demos.

Once you've found the perfect theme, it's time to move the code onto your desktop so that you can edit it. You do so by clicking "Download," which will take you to the Github repository of the theme's code. Fork it (copy it) over to a personal repository. Then, click on the green Download Code button to open the repository with Github Desktop. You can alter the Local Path to store the folder wherever you want on your computer. After you've cloned the repository, make sure you select that you're using the fork for your own purposes, and *not* to contribute to the parent repository! You definitely don't want to be making edits to the original theme. You should now be able to see the theme repository in your computer's file explorer. 

### Deploying the code

To deploy your site, you'll need to first check in your theme repository to see if you have a "netlify.toml" file. You should see it as soon as you open the theme folder (i.e. it shouldn't be in any subfolder). If you don't have it, feel free to download the [netlify.toml](https://github.com/robinzng/robinzen/blob/master/netlify.toml) file that I have in my Git. Make sure to commit to master and push changes whenever you make changes within your theme folder so that your local version is synced with your online repository! 

Sign into Netlify and click on "New site from Git." Select your repository from Github. On the "Build options, and deploy!" page, enter the build command as "hugo server". This is critical, as the build command is how Netlify is able to correctly execute your code. 

Your site should now be live! Click on the link that netlify provides (should be in the form of "https:// something - something - something .netlify.app") and you'll be able to see the unmodified theme. 

### Customizing your site

Now that everything's been linked together, open your theme folder in Visual Studio Code to start personalizing it. 

There's a lot of paths you can take from here, but I love a path of least resistance. So, rather than creating new code, we're simply going to edit the existing code in the "exampleSite" folder in your theme. The exact structure of the example site folder differs from theme to theme, so I encourage you to do some exploring on your own. However, a few constants that you should be aware of are: 

* Directly inside the exampleSite folder (NOT in a subfolder) should be a config.toml file. This file tells Netlify what theme to apply to the website. This is also where you can edit the overall organization of your site (e.g. title, menus, headers and footers). 
* The .scss scripts help determine the aesthetics of the site (e.g. colors, fonts, sizes). 
* The static folder is where you store the images, sounds, and other documents that you reference on your site.
* The layouts folder holds basic page structures (e.g. what does a 404 page vs. a blog post look like?)

There's a lot more ins and outs of each individual theme, but these are the broad strokes. Mess around with the code, try to break things and then piece them back together, and pretty soon you'll have a super sexy custom website! 

### Publishing your site

Once you've finalized your website and want the world to see it, you can FINALLY buy a domain. I suggest [Google Domains](https://domains.google/) for pretty cheap names and the ability to easily connect to Netlify. The instructions for connecting Netlify to Google Domains can be found [here](https://medium.com/@jacobsowles/how-to-deploy-a-google-domains-site-to-netlify-c62793d8c95e).

And that's it! Share this page if you found this tutorial helpful and straightforward. Again, if you have any suggestions, please [let me know](mailto:robinzeng1@gmail.com). 

With love and knowledge!! 
