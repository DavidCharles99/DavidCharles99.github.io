---
layout: post
title:      "first cli gem built from scratch "
date:       2019-02-17 23:38:10 +0000
permalink:  first_cli_gem_built_from_scratch
---

This project felt a little daunting at first, but as I slowly progressed, constantly falling over, I learned so much. As I was following the cli code-along video, I noticed my gem bundler wasn’t working properly, actually at all for that matter. It turns out you can’t download ruby gems on the OS ruby, as it could compromise the whole system. So I had to use rbenv to download a sperate version of ruby that I could use. This simple problem alone took far too long and was extremely frustrating. 

Once I got the bundler installed I was making head way fast. But once I got to using nokogiri and open-uri I hit a brick wall. My program kept failing, the web page not opening, over and over again. It took a full day’s worth of hairpulling to find the culprit, sigh I typed require 'open_uri'  instead of require 'open-uri'. 

The program was working beautifully, scraping the webpage info and getting back specific data on each coin. The only problem was once you typed in the name of the coin you wanted more info on, it displayed the same exact info for all the coins. This was no es bueno, the problem was I made a instance variable named @coin_mc equal to coin_mc, and just said ‘puts “#{@coin_mc}”’. I toiled over this problem for a long time, but I thought real hard and saw ‘@coins = GroupVenture::Coin.scrape_coins’ and was reminded that it was an array. So I replaced ‘puts “#{@coin_mc}”’ with puts "#{GroupVenture::Coin.scrape_coins[0].mc}" and it worked wonderfully. 

Now that my program worked, going one level deep wasn’t enough. I quickly added a buy function as a cherry on top. So to do this I puts "type y/n to buy" accompanied by gets.strip. After, I made a class variable for each coin that acted as a counter and puts "you have #{@@counter1} bitcoin". This worked great, but what if someone wanted to check their balance?  I made a new method called “wallet” that puts all of the individual class variables in a nice ordered bracket.  

	
