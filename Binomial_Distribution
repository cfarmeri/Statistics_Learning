rm(list = ls(all.names = TRUE))
sessionInfo()
library(dplyr)
library(stringr)
library(lubridate)
library(ggplot2)
library(tidyverse)



g <- data.frame(x = seq(0, 100, 1)) %>% mutate(n20p05 = dbinom(x, size = 20, prob = 0.5), 
                                               n100p03 = dbinom(x, size = 100, prob = 0.3),
                                               n100p05 = dbinom(x, size = 100, prob = 0.5),
                                               n100p07 = dbinom(x, size = 100, prob = 0.7)) %>%
  gather(type, val, -x) %>%
  ggplot(aes(x = x, y = val))
g <- g + geom_area(aes(fill = type), 
                   stat = "identity",
                   position = "dodge",
                   size = 1, alpha = 0.5)
g <- g + ggtitle("Binomial Distribution")
g <- g + theme(plot.title = element_text(hjust = 0.5))
g <- g + scale_fill_hue(name = "Parameter", labels = c(n20p05 = "n=20, p=0.5", n100p03 = "n=100, p=0.3", n100p05 = "n=100, p=0.5", n100p07 = "n=100, p=0.7"))
g

