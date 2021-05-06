# scrapping-press-freedom-index

# Summary

In this project, we are trying the scrape the data of `Press freedom ranking 2021`. It is Published every year since 2002 by `Reporters Without Borders (RSF)`, the World Press Freedom Index is an important advocacy tool based on the principle of emulation between states. The Index ranks `180 countries and regions` according to the level of freedom available to journalists.

#### Data we are scrapping:
* Name of the Country
* Current rank
* Details page url.
* Abuse Score
* Underlying situation score
* Global score
* Previous rankings (2013-2020)
* Journalists killed (2021)
* Citizen Journalists killed (2021)
* Media assistants killed (2021)

#### Stratergy:

* Using the [base url](https://rsf.org/en/ranking_table), we fetch the HTML page using the requests library.
* The HTML code is converted to a parsing tree using BeautifulSoup library.
* Using the methods provided by the BeautifulSoup library, we parse certain HTML snippets with identifiers such as class names, ids, attributes etc.
* In case of the above project, we parsed a tbody HTML snippet with `<tr>`(rows) corresponding to the data(`<td>`) each country.
* After attributes fetched here are `Name, Details page url, Abuse score, Underlying situation score and global score`.
* Now, we loop through the urls list and fetch the HTML pages of each individual country using the same methodology mentioned above.
* Here, we fetch the data of `Previous rankings(2013-2020), Current ranking, Journalists killed, Citizen Journalists killed, Media assistants killed for the year 2021`.
* The lists of data is put together into a dict(`scrappedData_final`) with keys pertaining to the name of the columns.
* Using pandas library, we now convert the data into a DataFrame which provides with various method to manipute and analyze the data.
* Using the method `to_csv` provided by pandas, we now save the Dataframe to a csv file(`press-freedom-index.csv`).

