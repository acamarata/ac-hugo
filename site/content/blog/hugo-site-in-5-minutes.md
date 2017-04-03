+++
date = "2017-04-03"
draft = false
title = "Deploying a site with Hugo in 5 minutes"
+++

Today we'll be using a specific boilerplate of Hugo which combines with Node to enhance it called [Victor-Hugo](https://github.com/netlify/victor-hugo) and deploying via Netlify's CDN. This 5 minute setup will cover the basic deployment of the site with a standard setup. I've used this deployment for this very blog you're reading now and I plan to blog any enhancements. Hugo is very customizable so feel free to tweak after you deploy.

*Background Reading: I wrote a blog post [here]({{< relref "blog/modern-static-websites.md" >}}) that discusses the many benefits of modern static site generators in todays web economy. I also wrote a comparison of some of them and why we're going to use Hugo [here]({{< relref "blog/comparing-jekyll-hugo-roots.md" >}}).  Finally, one of the best benefits of static hosting is free CDN hosting and I wrote a comparison of those and why we'll be using Netlify [here]({{< relref "blog/comparing-netlify-ghp-surge-forge-aws.md" >}}).*

## Requirements

1. [GitHub](https://github.com) account.
2. [Netlify](https://www.netlify.com) account for hosting (will be created in step 1 if you don't have).
3. [Git](https://git-scm.com) installed on your computer to push changes.
4. A text editor or IDE, such as [Atom](https://atom.io), to edit the files.

## 1. Deploying Victor-Hugo with Netlify

**~1 min**: Netlify has a feature to deploy any existing repository (such as the Victor-Hugo one above) easily by first cloning it to your own GitHub repository so you can make any changes you want and then deploying that to Netlify in one step.  At the bottom of the Victor-Hugo repository you'll see a button that says "Deploy to netlify" but you can also click [here](https://app.netlify.com/start/deploy?repository=https://github.com/eliwilliamson/victor-hugo) to get started. This will open you to Netlify's site like in the pictures below.

<center>
{{< figure src="/images/hsi5m-1a.jpg" >}}
{{< figure src="/images/hsi5m-1b.jpg" >}}
{{< figure src="/images/hsi5m-1c.jpg" >}}
</center>

## 2. Clone repository to your computer

**~30 sec**: Next you'll have to clone the repository to your local computer for editing the site with your information. You can also install the dependencies and then use `npm start` to view your site from your computer in your browser to check changes before you commit to GitHub and Netlify.

```
cd ~/Sites
git clone git@github.com:username/repositoryName.git
cd respositoryName
npm install
npm start
```

## 3. Make changes locally

**~3 min**: Open the files in your preferred text editor. Everything you'll need to change will be in the `/site` folder.

1. Copy a profile picture to `/site/static/images/`. The theme defaults to `avatar.jpg` but this is a setting in the `config.toml`.
2. Open and edit the `/site/config.toml` which will be straight forward, especially if your's looking at the site locally from `npm start` above. The things I changed for this blog are: `title, disqusShortname, googleAnalytics, (params) name, description, avatar, bio, github, linkedin, copyright, (about) title, content, (contact) title, contact, address, phone, email, and (menu)`. If you don't have accounts for anything right now just leave it blank (or make it blank) and you can change this at any time.
3. The default theme uses Formspree for the contact form. If you set the email in the last step just send anything via the contact form and the first time used it will verify your email instead of just sending.

## 4. Push to Git and done

**~30 sec**: Congratulations, you now have a basic site. Now commit and push your changes. Remember how Netlify asked to authorize with your GitHub account in Step 1? When we did this Netlify created a token with GitHub for notifications. So once you push changes to GitHub it will then notify Netlify that you updated. Netlify will then automatically grab the new files and updates and redeploy your site. Netlify uses instant cache invalidation to make sure visitors to your site, even returning, get the new version of your site and not a cached version. This all happens in a matter of seconds between GitHub and Netlify. After this you can visit your site with whatever you named it on step one at yoursite.netlify.com (to customize your domain you can do this any time in the Netlify dashboard if you own a domain).

```
git commit -m "initial site setup"
git push origin master
```

## 5. Updating site

The longer part now will be your real content. The portfolio will be setup via the `config.toml` as well as making a resume (CV) and editing the first two example posts to get your blog started. With the `npm start` command above you can view your site locally and then push any changes to your live site when ready. On this site I've already done a few of these steps but will be blogging soon on these steps. In the meanwhile check out the [Hugo Introduction](https://gohugo.io/overview/introduction/) to get going.
