---
title: "Viewing GitHub Pages Locally"
categories:
  - Blog
  - Community
  - Data Saturdays

tags:
 - Blog
 - Events
 - Community
 - Data Saturdays
 - Automation
 - YAML
 - docker
 - jekyll
 - GitHub Pages

image: 
  path: https://datasaturdays.com/assets/design/facebook/c.facebook%201r.png  
  thumbnail: https://datasaturdays.com/assets/design/facebook/c.facebook%201r.png  
  caption: "Data Saturdays"

author: robsewell
---
This blog was syndicated from [blog.robsewell.com](https://blog.robsewell.com)
# Data Saturdays Has New Clothes!

The Data Saturdays Admins asked the community to vote on their favourite logo for the Data Saturdays website. After over 400 votes the results came in.

[![newclothes](https://blog.robsewell.com//assets/uploads/2021/newdatasaturdayclothes.jpg)](https://twitter.com/datasaturdays/status/1380152923498352644)

Denny Cherry & Associates Consulting [https://www.dcac.com/](https://www.dcac.com/) generously supported Data Saturdays and paid for the artist to design the logo and create the artifacts via [99designs.com](https://99designs.com). THANK YOU Denny and many thanks to Monica Rathbun [twitter](https://twitter.com/SQLEspresso) - [blog](https://sqlespresso.com/) for all of the hard work in organising and administering all of the requirements and handling all of the communication with the artists.

<!--more-->

# Now we have to update the web-site

The next challenge we face is to update the website. As the website is hosted on GitHub Pages using Jekyll, this means that we can easily update the website by updating the code and letting GitHub actions build the new site but we have no way of checking the way that it looks before we push the changes. With such a radical change required, I felt that it would be a good idea to explore how to do this locally.

## Install everything you need locally

I examined the requirements to create a local development environment and this meant installing Jekyll and Ruby and a host of other things, there appeared to be a whole bundle of quirks and strange errors that may or may not need to be handled so I quickly went off that idea!!  

## Docker to the rescue

This is a fantastic use case for using a Docker container. I can host all of the required bits inside a container, spin it up and down as I need it and I don't have to worry about polluting my machine with software and settings or the pain of having to configure it to work.  

Also, other people have already done a lot of the work so I dont have to.  

With thanks to Hans Kristian Flaatten [GitHub](https://github.com/Starefossen) - [Twitter](https://twitter.com/Starefossen) who has created [this docker image](https://github.com/Starefossen/docker-github-pages) it is as easy as  

````
docker run -it --rm -v "$PWD":/usr/src/app -p "4000:4000" starefossen/github-pages
````

Now I can see my changes locally in my browser at `http://localhost:4000/`  

[![localdev](https://blog.robsewell.com//assets/uploads/2021/localdev.jpg)](https://blog.robsewell.com//assets/uploads/2021/localdev.jpg)

I am running Docker in WSL2. I followed these [instructions](https://code.visualstudio.com/blogs/2020/03/02/docker-in-wsl2) to set it up

# Develop and Test

Now I can make changes to the code in the website and save the file and the site will update. In the below video, you can see that I have updated the favicon so that the new logo appears.

<iframe width="650" height="250" src="https://blog.robsewell.com/assets/uploads/2021/livedevelop.mp4" frameborder="0" allowfullscreen></iframe>   

I shall go back to editing the site now.

# Data Saturdays

You can find the [Data Saturdays web-site here](https://datasaturdays.com). There is a list of all of the upcoming and past Data Saturdays events available.