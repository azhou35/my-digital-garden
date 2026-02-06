---
title: "the scaling era"
---

#thinkpiece 
by dwarkesh patel
![[Screenshot 2025-12-22 at 8.45.44 PM.png]]
- only took chatgpt 3.5 - 2 months to get 100M users
![[Screenshot 2025-12-22 at 8.49.07 PM.png]]
- it's v abrupt: you can predict statistical avgs of the weather but the weather of one particular day is very hard to predict
- why do scaling laws work? how do we have sm faith that if we 10x $ we wont see diminishing returns 
	- data manifold: structure representing all positible data points, conceptualized as a surface w a coplex shape in a high dimensional space
	- think of neural networks as mapping their data to some kind of data manifold that has some dimensionality
		- networks just fit a curve to a data manifold
		- aka doing science, get data points on x vs y, and fit some sort of curve to that 
		- as you increase # of parameters, cutting up data manifold into more and more high resolution pieces 
			- asking how will the error scale as u chop it into more and more pieces
			- you get a powre law scaling in the # of parameters
	- scaling law tells you what happens to the *log* of your next word prediction accuracy - how do you link this to actual reasning capability
- most creatures have small brains -> save biological energy
- humans - big brain -> increase the returns of large brains
	- language
	- technology 
- *Bitter Lesson* essay - there are two things you can scale
	- search
	- learning
	- He writes that sophisticated methods using limited compute will always lose out to simple methods that continue to scale with increased computation.”
- atm models can blend things
	- but agi wouldn't mimic
		- it would search thru an infinite sample space of possibilities make *unpredictable moves*
- reasoning improves sublinearly vs inearly 
- pretraining = magic
	- 