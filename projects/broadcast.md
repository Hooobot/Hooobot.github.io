---
layout: project
type: project
image: img/uhb/broadcastlogo.png
title: "UH Broadcast"
date: 2022
published: true
labels:
  - Web Application
  - JavaScript
  - GitHub
  - UH Manoa
summary: ""
---

## UH Broadcast
UH-Broadcast is an example web application that provides pages to view and post listings of various items for the UH community.
This application was designed, implemented, and maintained by five individuals including myself and serves to only be accessible by individuals within the hawaii.edu domain. 


### Overview
The problem: UHM students have a “rapid” churn rate in goods and services. Students leave the dorm for an on-campus apartment and need to get rid of dorm-specific stuff and acquire apartment-specific stuff. Students graduate and need to get rid of stuff because they’re moving off-island. There is therefore a tremendous amount of “campus-specific” goods and services that could be more effectively recycled and reused if there was an effective marketplace for these specific kinds of items.

The solution: UH-Broadcast is an application for UHM students to facilitate buying and selling of student-related goods and services.
<br>
<center>
  <img src="../img/uhb/landing.png">
</center>
<br>

Above shows a picture of the landing page for UH Broadcast. In doing our project, we were also able to implement continuous integration which confirms a working testflow for our pages.

Badge from Integration:
<br>
<br>
[![ci-UH-Broadcast](https://github.com/UH-Broadcast/BroadcastHosting/actions/workflows/ci.yml/badge.svg)](https://github.com/UH-Broadcast/BroadcastHosting/actions/workflows/ci.yml)

<br>
Moreover, we are able to execute a [Digital Ocean Deployment](http://uh-broadcast.online/).

### Contributions

On my end, I was able to contribute to most of the styling, deployment, and took a jab at back-end. I was interested more in how the item database within our project could be better structured and pushed out to the audience, allowing users to better manage, perceive, and interact with items while still being within audience to the application. One of my earliest contibutions was the implementation of the restriction to @hawaii.edu domains. By specifying the Sign Up page to only allow for "@hawaii.edu" emails it then restricts the user to only be certified from the hawaii domain. By limiting the users in this manner, we can ensure a more catered audience, as per the goal of the application. However, further development might yield for a more cerfied way using the credentials from the UH login system.
<br>
As for my front-end work, I contributed most of that to the CSS file of our project, as show below:
<br>
```css
/* Use 0pen Sans as the default sans serif font. */
@import url("https://fonts.googleapis.com/css?family=Open+Sans:300,400,500,700|Source+Code+Pro:300,400,500,700");

/* Set up some CSS variables to theme the application. */
:root {
  --matr-navbar-bg: #376551;
  --matr-navbar-bg-rgb: 10, 68, 10;
  --matr-navbar-text-color: white;
  --matr-navbar-highlight-text: white;
}

/* Change bootstrap variable values.
 See https://getbootstrap.com/docs/5.2/customize/css-variables/
 */
body {
  --bs-dark: var(--matr-navbar-bg);
  --bs-dark-rgb: var(--matr-navbar-bg-rgb);
  background-image: url("images/ManoaWallpaper.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;
}


body .navbar {
  --bs-navbar-active-color: var(--matr-navbar-highlight-text);
  --bs-navbar-brand-color: var(--matr-navbar-text-color);
  --bs-navbar-brand-hover-color: var(--matr-navbar-highlight-text);
  --bs-navbar-color: var(--matr-navbar-text-color);
  --bs-navbar-hover-color: var(--matr-navbar-highlight-text);
}

.navbar a.nav-link.active {
  color: var(--matr-navbar-highlight-text);
}

footer, footer a {
  color: var(--matr-navbar-text-color);
}

.landing-page-white {

}

/* Set the alert background on the signin and signup pages. */
#signin-page .alert-light, #signup-page .alert-light {
  --bs-alert-bg: var(--matr-navbar-bg);
}

/* Define custom styles */
.gray-background {
  background-color: var(--matr-navbar-bg);
  color: var(--bs-dark);
  padding-top: 10px;
  padding-bottom: 20px;
}

.navbar {
  font-family: "Academy Engraved LET";
  font-size: 20px;
  font-weight: bold;
  align-items: center;
}

.nav-link {
  margin-right: 30px;
}

#manoaBackground {
  background-image: url("public/images/ManoaWallpaper.jpg");

}
/*
#adminbutton {
  background-color: darkgreen;
} */

#listitembutton {
  background-color: #376551;
}

#catBar{
  color: darkgray;
}
```
<br>
In doing so, I was able to manage changes to most of the site without directly editing each page, saving a good bit of convenience and continuity. However, for some particular pages, such as the Categories page, it required specific edits for margins and such that allowed for a better styling overall.


### Where to Learn More

More information on this project can be found [here](https://uh-broadcast.github.io/). <br>
Additionally, the deployment for the site can be found [here](https://uh-broadcast.online).

