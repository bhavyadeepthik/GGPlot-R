# GGPlot-R-Diamonds
GG-PLOT-R
Authour-@Bhavya-Deepthi

library(ggplot2)

diamonds<-ggplot2::diamonds

View(diamonds)

ggplot( diamonds) + geom_bar( mapping = aes( x = cut))

ggplot( data = diamonds, mapping = aes( x = price, y = ..density..) ) + geom_freqpoly( mapping = aes( color = cut), binwidth = 500)

ggplot( data = diamonds, mapping = aes( x = cut, y = price)) + geom_boxplot()

#the following graph has too much points but we can see the trend 

ggplot( data = diamonds) + geom_point( mapping = aes( x = carat, y = price))

#with geom_smooth it is more clear

# the graph below shows that for all cut the trend is when carat increase price increase

# so carat has a strong influence on prices , but for some cut (ideal) there is a decrease 

# of price above 2.5 carats as shown in the graph below

ggplot( data = diamonds,mapping = aes(x = carat, y = price,color=cut)) +geom_point() +geom_smooth()

#there are very few diamonds of more than 4 carats

bigcarat<-subset(diamonds,diamonds$carat>=4)

# box plot is perfect to analyse price for the different cut the average price of cuts is

# close we conclude that price has no clear influence on prices.

# this graph below shows that the ideal cut (best) has average price lower than fair cut 

# (low quality) ! which is very surprising 

ggplot ( data = diamonds , mapping = aes ( x = cut , y = price )) + geom_boxplot () 

# correlation between price and carat is very high (close to 1) 

cor(diamonds$price,diamonds$carat)

# correlation between price and depth is very low close to 0 )

cor(diamonds$depth,diamonds$price)
