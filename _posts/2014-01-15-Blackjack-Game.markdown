---
layout: post
title:  "Let's Gamble"
date:   2014-01-15 10:33:06
---

Let's Gamble !!, instead of a nap during your break, now you can play Blacjack!!

Enjoy ;)

Ps : it's an open source project, please feel free to improve it.


{% highlight ruby %}

score = 0
bankscore =0

while score < 21
	puts "card ? answer by (y or n)"
	answer = gets.chomp
	if answer == "y"
		 score += rand(1..11)
		 if bankscore <= 16
		 		bankscore += rand(1..11)
		 end
		 puts "you score is #{score}, bank is #{bankscore}"
	else
		while bankscore <= 16
					bankscore += rand(1..11)
		end
		break
	end
end

if bankscore > 21
	puts "you win"
else 
	if score > 21
		puts "you loose bank : #{bankscore} you : #{score}"
  elsif score == 21
	 	if bankscore != 21 
	 		puts "Blackjack!"
	 	else 
	 		puts "You loose bank : #{bankscore} you : #{score}"
	 	end
  elsif score > bankscore
		puts "You win bank : #{bankscore} you : #{score}"
  else
		puts "You loose bank : #{bankscore} you : #{score}"
	end 
end
{% endhighlight %}