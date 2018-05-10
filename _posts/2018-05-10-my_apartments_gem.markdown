---
layout: post
title:      "My Apartments Gem"
date:       2018-05-10 12:08:00 -0400
permalink:  my_apartments_gem
---



Finding a site for the CLI gem took much time because initially things were not working and the CSS selectors yielded empty arrays.
I did not know what was wrong with my work.. until a fellow student who had a similar problem pointed to the fact that perhaps this website uses Javascript and therefore isn’t detected by Nokogiri.

I live in New York, and finding an apartment in the city can sometimes be a challenge… So I found this topic interesting.

This experience was nice in the sense that when I started this project, I did not know how I will get from the start point to the end point. However, watching the walk through and seeing a finished gem were really helpful. And then, overcoming this challenge and working out the problems again and again added knowledge and had built confidence, as well.

And now, a few words about the flow of the gem:

The gem is invoked from ./bin/apartments
* All object classes are accessed via the module Apartments,  which requires the environment.
* An instance of CLI is created, and the call method is called
* The (CLI instance) call method creates an instance of Scraper, and calls the (Scraper instance) method make_apartments. The page is scraped into an array, and from each item in this array, an apartment object is being built and put in the (Apartment class) @@all array. 
* At this point, control returns to the call method. The user is welcomed to the NY listing, and is presented with the latest listing of 120 apartments in the NY area.
* The user can recursively choose an apartment to look at, or exit.
 

The content of your blog post goes here.
