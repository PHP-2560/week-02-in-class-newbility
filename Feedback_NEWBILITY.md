


You haven’t learned ggplot yet but for problem 11, you don’t specify variables using the $ in ggplot.

Correct way to plot:
delay<-flights %>%
    group_by(tailnum) %>%
    summarise(count=n(),dist=mean(distance,na.rm=TRUE),delay=mean(arr_delay,na.rm=TRUE))

  ggplot(delay, aes(dist, delay)) +
  geom_point(aes(size = count), alpha = 1/2) +
  geom_smooth() +
  scale_size_area()
