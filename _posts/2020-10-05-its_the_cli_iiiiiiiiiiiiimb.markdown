---
layout: post
title:      "'It's the CLI_iiiiiiiiiiiiimb!'"
date:       2020-10-05 20:25:45 -0400
permalink:  its_the_cli_iiiiiiiiiiiiimb
---





Me at the THOUGHT of completing my very first portfolio project :



![anxious spongebob](https://media.giphy.com/media/HThocT5vEPT9K/giphy.gif)

![anxious spongebob 2](https://media.giphy.com/media/tvU9iTev6uBIQ/giphy.gif)




At first glance, it seemed like such a daunting task. 


The first chance I have to really prove myself, to put the skills I've built up to this point, to the ultimate test. Not just another codealong or lab.


This was it!


But I soon found I wasn't alone in my feelings and journey. Many of my classmates were feeling the same! 


I knew I just needed a quick pick me up before I started, so I grabbed a latte from Dunkin, made it back home, opened my laptop, and put on an inspirational music playlist. 


I started mapping out my program. 

Who is my user? 

How will they experience my program? 

Will it run slow? If so, how could I potentially refactor to make it faster. 

Will I use a scraper, or an API. Hmmm.... let's see... API! ABSOLUTELY. 

What are some of the best API's to use? 

Where can I find an API? 

Where can I find an open-source API that doesn't require authorization. 

... 


All of these questions floating around in my mind, keying me up, causing me to just stop and stare at the screen.  I felt stuck once again.




![spongebob computer](https://media.giphy.com/media/DBW3BniaWrFo4/giphy.gif)





AND THEN . . . 

that infamous and infectious song starting playing in my ear. . .


"...I can almost see it
That dream I'm dreaming but
There's a voice inside my head saying
You'll never reach it,
Every step I'm taking,
Every move I make feels
Lost with no direction
My faith is shaking but I
Gotta keep trying
Gotta keep my head held high..."


I was reviIIIIVED!



I took a breath and starting clacking away at the keyboard once again. 


Fast forward ------ 


I hit a stumbling block when the API I had requested from the author was no longer available!


Scratch that idea....


I had to rewrite all my plans.... 



![spongebob lips](https://media.giphy.com/media/xTeV7WNYcKddLV5R3G/giphy.gif)




So I finally found an API that worked and could easily be integrated into my program. 


Whew!


It also had many attributes that I could add onto my second level. Which would give the user more detailed information their selection. 


Now that I had a great working API, I was ready to move onto building out my API class structure. 


I took what I had learned in previous lessons and labs, with some minor tweaks, and VOILA!


We have an API class!


class API
    def self.get_data
        response = RestClient.get("https://swapi.dev/api/planets/")
        planets_array = JSON.parse(response.body)["results"]
        planets_array.each do |planetzz|
            PlanetFax.new(planetzz)
        end
    end

end


So what is happening here?  Why would I need to set up a class just for the API data? 

Well, I am first creating this class so that I can call upon it in CLI class later on. 



![easy button](https://media.giphy.com/media/Rl9Yqavfj2Ula/giphy.gif)








Onto the CLI class :







![ron swanson](https://media.giphy.com/media/NJlMya8d3RNCw/giphy.gif)







class CLI
    def call
        puts "Welcome to PlanetFax, stargazer!"
        puts "To see planets, enter 'planetz'"
        puts "To exit PlanetFax, enter 'exit'"
        API.get_data
        menu

    end
		
		
		
		
		
		
Naturally, I cooked up a call method that would print out a welcome message and prompts for the user. 

Underneath, you'll notice the API class! Which I am now invoking in order to retrieve that data and spit it out in a readable form for the user. 

Underneath, the menu method is then invoked, which brings us to the menu method. 


The menu method I knew would incapsulate if/else statements based on the user's input. 


So....  where to begin ?


As I began to ponder... the song continued in my ear... 


"... There's always gonna be another mountain
I'm always gonna wanna make it move
Always gonna be an uphill battle
Sometimes I'm gonna have to lose
Ain't about how fast I get there
Ain't about what's waiting on the other side
It's the CLIiiiiiiiiiimb! "



I was inspired once again and somewhere within my mind, the info was always there... the thought came to me almost instantaneously. 






    def menu
        input = gets.strip.downcase

        if input == "planetz"
            planets_list
            menu

        elsif input == "exit"
            goodbye

        else
            invalid_entry

        end
				
	   end
end



How would the user input their information?       input!

And what methods are typically used for user input?    gets!

And what is the user wants to be cool and just prefers to input random stuff?   For example:   ExIT,   PLanetZ    ,  etc?

I need to make everything uniform, get rid of white space and such... hmmmmm

AH HA! 

#strip    #downcase




































































































. . .


And in case you just got a case of nostalgia (circa 2009).  Here you go...


https://www.youtube.com/watch?v=NG2zyeVRcbs


You're welcome!

( I also sincerely apologize if this song is now stuck in your head... )




![miley cyrus winking](https://media.giphy.com/media/4ejXFozWGT1HG/giphy.gif)







