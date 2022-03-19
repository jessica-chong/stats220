# Steps to create the meme 
Below are some steps that I used to create the meme shown.
![]()

## 

```{r}
library(magick)

#text one
text1 <- image_blank(width = 500, 
                     height = 150, 
                     color = "#fef6e1") %>%
  image_annotate(text = "Me when watching clips\n of puppies on phone", 
                 font = "Trebuchet", 
                 size = "40",
                 gravity = "South")

#text two
text2 <- image_blank(width = 500, 
                    height = 150, 
                    color = "#fef6e1") %>%
  image_annotate(text = "Me when seeing real\n puppies in friend's house",
                 size = "40",
                 font = "Trebuchet",
                 gravity = "South")

#image one
happy_rabbit <- image_read("https://i.pinimg.com/originals/ca/2c/45/ca2c450faa4d350db3b79e0b571d0c20.png") %>%
  image_crop("1000x550") %>%
  image_scale(500)

#image two
scared_rabbit <- image_read("https://i.ytimg.com/vi/PEyMsHQlExY/maxresdefault.jpg") %>%
  image_crop("1000x620+75") %>%
  image_flip() %>%
  image_crop("1000x520+55") %>%
  image_flip() %>%
  image_scale(500)

#text row
first_row <- image_append(c(text1, text2))

#image row
second_row <- image_append(c(happy_rabbit, scared_rabbit))

#meme
meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(700)
```
