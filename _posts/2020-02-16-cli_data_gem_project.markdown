---
layout: post
title:      "CLI Data Gem Project"
date:       2020-02-16 21:36:47 -0500
permalink:  cli_data_gem_project
---


This project was a lot of fun, though I do wish I worked on it over the course of the two weeks rather than last minute. Work has been crazy and I was fortunate to have a lot of time at the end here to push through it!

This gem will allow you to type in the name of a Pokemon to learn about its ID, height, and weight.

A struggle that I ran into (and got stuck for about five hours) had to do with actually parsing through the format of the JSON in the API to pull the data that I needed. For a long time my responses were coming back as nil and the the instance of the Pokemon were not being created. The solution ended up being RIDICULOUSLY simple, but that seems to be how it goes with stuff like this. 

What I had was...

    response = HTTParty.get(url + "pokemon/#{name}")
    response.parsed_response 
    name = ["name"]
    id = ["id"]
    height = ["height"]
    weight = ["weight"]
	 
These values kept returning nil, and a pokemon could not be instantiated.
	 
The simple solution was this...
	 
	    response = HTTParty.get(url + "pokemon/#{name}")
      response.parsed_response 
      name = response["name"]
      id = response["id"]
      height = response["height"]
      weight = response["weight"]
			
It only took about five hours of playing around with pry to realize the mistake!
			
All in all it was a lot of fun, and I learned a lot through completing this project. I definitely feel a lot more comfortable working with objects in Ruby, and connecting to an API is not as intimidating as it was. I hope you enjoy the gem!
			
			

