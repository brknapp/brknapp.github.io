Third Blog Post: Project 1
================

[GitHub Pages Repo](https://brknapp.github.io/Project_1/) [Regular
Repo](https://github.com/brknapp/Project_1)

For this project, I used the OMDb API to get data about movies. I
selected this API because I wanted to see if ratings and box office
earnings were correlated. That is, if a movie was highly rated, did that
mean it earned a lot of money at the box office?

I made several functions that will help the user get data from this API.
I tried to make ones that could be flexible enough to handle anyone’s
needs. Before I made my functions, I tried to think about what
parameters someone might have. They might want to search for one
stand-alone title, like “The Wizard of Oz”, or they might want to search
for all of the movies in one series, like the Star Wars franchise, or
multiple series. They may also have a title and a date, like Star Wars:
Episode VII - The Force Awakens (2015), or a valid IMDb ID.

Then, I formatted the data by converting the appropriate columns from
character to numeric and from character to date and creating two new
columns showing the average rating and a summary of the awards the movie
may have won or was nominated for. The two new columns proved useful for
my exploratory data analysis. Creating the average rating column was
somewhat challenging because I had to accommodate for some of the movies
in my data set that had an NA in the Metascore column. I also had to do
a lot of parsing, especially in the Ratings.Value column because some
values were fractions and others had a percent sign.

Lastly, I made several tables and graphs summarizing both categorical
and quantitative data. I learned that that there were a diverse set of
genres in my data. I also discovered that a good amount of the movies in
my data set won awards or was nominated for an award. Also, there does
seem to be a slight correlation between ratings and box office earnings.
It would be interesting to see if the box office earnings were adjusted
for inflation.

If I did a similar project in the future, I would have someone, who is
not familiar with R programming, test my functions to make sure they
make sense and that they’re easy to use. I would have also tested my
functions with more movie titles and series titles to make sure that
they work for any search term.
