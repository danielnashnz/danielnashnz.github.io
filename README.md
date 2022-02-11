# danielnashnz - Transferring NYT Wordle Stats

## How to transfer Wordle statistics to New York Times
### N.B. This has not been tested on mobile browsers
You will need to open the sites in your usual browser you use for playing the game.

### Find the NYT Wordle page

* [https://www.nytimes.com/games/wordle/index.html](https://www.nytimes.com/games/wordle/index.html)

### Find the Original Wordle site

In another window or TAB, open whichever one of these sites you have been playing on:

  * [www.powerlanguage.co.uk](https://www.powerlanguage.co.uk/)
  * [powerlanguage.co.uk](https://powerlanguage.co.uk/)

You should see this page: **"Hi, I'm Josh"**

### Copy the Wordle stats

Now you need to open the Web Inspector for your browser:

* Right-click on an empty part of the page with your mouse and select `Inspect` or `Inspect Element`
* A new panel should open up with the page code in it
* Select the "Console" tab
* Copy/Paste or type into the Console panel at the `>` or `>>` prompt:
```bash
localStorage.getItem("statistics")
```
* A long string of characters containing your gaming stats should appear
* ... if they do not try the other link to the original Wordle site listed above

e.g.

```bash
 "{\"currentStreak\":16,\"maxStreak\":16,\"guesses\":{\"1\":0,\"2\":3,\"3\":9,\"4\":13,\"5\":4,\"6\":3,\"fail\":1},\"winPercentage\":97,\"gamesPlayed\":33,\"gamesWon\":32,\"averageGuesses\":4}"
```

* Copy *that* set of characters, including the `"` or `'` characters, to your clipboard, for instance by using the `CTRL-C` or `CMD-C` key combination.

### Transfer the stats to the New York Times

* Switch to the NYT Wordle page in the other window or tab.
* You need to open the Web Inspector again:

* Right-click on an empty part of the page with your mouse and select `Inspect` or `Inspect Element`
* A new panel should open up with the page code in it
* Select the "Console" tab
* Type into the Console panel at the `>` or `>>` prompt:
```bash
localStorage.setItem("nyt-wordle-statistics", "PASTE YOUR STATS FROM CLIPBOARD HERE")
```

Your stats should now be transferred.