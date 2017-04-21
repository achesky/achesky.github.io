---
layout: post
title:  "Create a Team and Heroes! "
date:   2017-04-21 00:01:05 +0000
---


For my blog assignment this time around, I'm going to explain how I created the nested forms superhero lab. This lab involved creating a form (on a webpage) where a user fills in the aspects of their team (name, motto) as well as the members of their team - the superheroes! Each superhero has a name, a power and a bio. 

The first think I did was create the '/' route in the controller to display a page `super_hero`. This page holds the code for the nested form! 

The form's method is `post` and it's action is `/teams`, so that the form's responses are posted to the /teams page. The type of all of the input fields is `text`. But those are the easy parts. I'll give one segment of the code and walk through it. 

`<label for="hero 1 name">hero 1 name:</label>
  <input type="text" id="member1_name" name="team[members][][name]"></br>
  <label for="hero 1 power">hero 1 power:</label>
  <input type="text" id="member1_power" name="team[members][][power]"></br>
  <label for="hero 1 bio">hero 1 bio:</label>
  <input type="text" id="member1_bio" name="team[members][][bio]"></br></br></br>`
	
This section is for the part of the form used to describe the first superhero of the team. All of the input secions are labeled hero 1 and then either name, power, or bio. The user's text is then recorded in `params` as `team[members][][name]` or a variation with power or bio instead of name. 

These values are then used in my controller. 
`post "/teams" do
      @team_name = params[:team][:name]
      @team_motto = params[:team][:motto]
      @hero_name = []
      @hero_power = []
      @hero_bio = []
      @team_members = params[:team][:members]
      @team_members.each do |hero|
        @hero_name << hero[:name]
        @hero_power << hero[:power]
        @hero_bio << hero[:bio]
      end`

I recorded these values from the form as instance variables. These variables are then accessed in my team.erb file, which is called in the controller after the section of code above. 

`<h1><%= @team_name %></h1>
<h2>Team Motto: <%= @team_motto %></h2>

<% @team_members.each.with_index do |hero, index| %>
  <h2>Hero Name: <%= @hero_name[index] %></h2>
  <p>
    Hero Power: <%= @hero_power[index] %>
    <br>
    Hero Biography: <%= @hero_bio[index] %>
  </p>
<% end %>`

This code displays the team's name and motto, as well as the name, power, and bio of each superhero on the team! 

Tada! Learning Sinatra so far has been challenging, but very interesting.
