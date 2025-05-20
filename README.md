# R_code_cheatsheets
place to store useful chucks of code to easily find

## file nameing comventions
wo_   <- unfinshed script \
get_  <- make a new data frame \
plot_ <- figues \
fun_  <- functions \
stat_ <- analysis 
 
### GGplot 

theme(legend.position = "none") <- remove legend \
theme(axis.text.x = element_blank()) <- remove x labels



### push notifications using push bullet
fist AIP needs to be created at online account (in settings)
then donwlad phone app 
and link to R with  

library(RPushbullet)
pbSetup(apikey = "o.5f7ZVtw8kAsYQK4HxRJLlVNiIcJzXYhY")


library(RPushbullet)
pbSetup(apikey = "o.5f7ZVtw8kAsYQK4HxRJLlVNiIcJzXYhY")

# to send simple notification 
pbPost("note", title = "R Alert", body = 'Script finished 💃 ')


# to send error 
tryCatch({

~ insert code here ~

})
}, error = function(e) {
  pbPost(
    type = "note",
    title = "🚨 R Script Failed!",
    body = paste(
      "Error:", e$message, "\n",
      "Time:", format(Sys.time(), "%Y-%m-%d %I:%M %p")
    )
  )
})
