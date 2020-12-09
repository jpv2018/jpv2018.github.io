---
layout: post
title:      "Rails Project"
date:       2020-12-09 05:17:16 +0000
permalink:  rails_project
---


This project took more time investment than I had anticipated, but it was fun to build. One of the more challenging parts of building this app was figuring out how to put a form for a Judge to add a score for Player without rendering a #new page. The way that I found to do this was to create a judge_players controller and a judge_players#index page. The route for this page was /judges/:judge_id/players. I inserted the form_for :score inside of the @players.each do |p| so that it would render a form for each player to fill out a form while granting access to the attributes of that instance of Player. I did learn through much trial and error that all I had to type was p.id to pull the id of the Player instance in that form. I spent a lot of time trying to think of ways to do this, and overcomplicated it for quite some time, typing things like Player.find_by(params[:player_id] only to receive error after error. Funny how most of the time the answer is so simple. I learned a lot from this project and look forward to moving into Javascript!
