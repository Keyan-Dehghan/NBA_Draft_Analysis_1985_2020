# Examining the NBA draft from 1985-2020

Analyzing Drafts from 1985-2020 in order to determine how draft picks and team quality affect the quality of players in the long run

Context:
In the NBA, the draft is arguably the main way to get talented players without having to give up much value in return. It allows a team to select players, and hope that they can translate from a lower level of play all the way to the highest level of basketball. However, it’s very difficult to predict whether a player will live up to their expectations, or whether they’ll struggle to perform very well in the NBA, making it very risky, with some teams drafting better than others. In the draft, higher picks are more likely to become star players, however, an important question in the NBA draft is “How much more valuable are high picks, in relation to low picks?” Another important question when considering drafting is “What types of teams are best at developing talent in the NBA? Is it good or bad teams that are better at getting the best out of a prospect?” The analysis here is used to give answers to those two questions.

Data Structure Overview:
The main variables used to judge the relationship between draft picks and value include metrics for a player’s value, namely Win Shares (WS), and Value Over Replacement Player (VORP), both found on basketball reference, and both aiming to estimate a player’s value in just one number. When it comes to team quality, the main metrics in question were win percentage, net rating (point differential per 100 possessions), pythagorean win loss% (Predicted win loss percentage based on point differential), and SRS (Net rating adjusted for strength of schedule). All of the team strength metrics were also expressed in percentile rankings in order to determine the relative quality of the teams.

Additionally, the averages for WS & VORP were computed for all players from 1985-2020, in order to form a baseline, where a player being below the line was considered below average, and this formed the basis for comparing picks.

In order to perform the analysis, I performed data cleaning on excel, combined the data on SQL, and performed a regression on jupyter notebooks

Summary:
The data in question shows that the quality of players by draft picks follows a sort of reciprocal shape, whereby the top few picks are quite valuable, with the first pick being the most valuable, after which picks 6-15 are considerably less valuable, remaining picks in the first round (16-30) tend to yield below average players, and 2nd round picks almost always yield below average players, with most picks in the second round being roughly equal in value.

Additionally, after having run a regression, what I found was that worse teams are either slightly better, or no better at drafting than good teams, based on the metrics.

Deep Dive:
In the drafts, the first overall pick was found to be quite valuable, with the average first pick having the value of multi time all star Larry Johnson, with remaining picks in the top 5 being roughly equal. Afterwards, remaining picks in the top 15 are far less valuable, approaching the territory of producing average players, picks 16-30 are similar in value, with almost all of the picks individually yielding below average players, and picks 31-60 all yield below average results.

What I found interesting was just how early in the draft you start to see teams struggle to get good players, as by the end of the draft lottery, not only are the picks not returning great value, but the players in question are essentially average. Additionally, I was shocked that roughly half of the picks in the first round yield below average players. Another surprising finding is that 2nd round picks have roughly the same value.

The results of the regression I got were that worse teams are only slightly better at drafting, all else equal, as based on pythagorean win loss percentage (which almost always had a statistically significant impact on player quality, regardless of the dependent variable), however, net rating percentile either had the opposite effect on player quality, or was statistically insignificant. Additionally, the fact that all of the other metrics for team quality didn’t take on a clear direction in aggregate likely means that team quality isn’t extremely relevant when it comes to how well teams are able to get the most out of players.

The diminishing returns of the NBA draft may also explain why some bad teams continue to stay bad for a long time. While they may get ostensibly valuable picks, their inability to get the highest picks (especially the first pick) means they often fail to have the ability to draft a transformational talent, or they get high picks in predominantly weaker drafts. However, it’s certainly true that some teams draft far better or worse than others.
As an example, the Boston Celtics took arguably the best player in back to back drafts with the 3rd pick (Jaylen Brown and Jayson Tatum in 2016 & 2017), both of which were years where they owned another team’s draft pick despite being a solid playoff team, while the Lakers, who picked 2nd in 3 consecutive drafts came away with a far worse collection of players (D’Angelo Russell in 2015, Brandon Ingram in 2016, & Lonzo Ball in 2017).

Recommendations:
My main recommendations for NBA teams when drafting are centered around not overvaluing top 5 picks past the first overall pick, as even though they may be considered far better assets, in practice, they aren’t quite as prestigious as they seem.
Additionally, picks 6-15 are generally not far off in terms of value, which means that trading up from the early teens to get into the top 10 typically isn’t a great decision.
The same is the case for picks 16 through the end of the first round, and for almost the entire 2nd round, which are similar in value.

This may mean that teams are better off trading down more often than they do, and that trading up is generally a bad idea. Additionally, I think the data shows that the idea of a first round pick is better than the players who are actually drafted, which means that it’s typically a good decision to trade first round picks in order to obtain proven players.

While these results do suffer from a small sample size, as can be seen by discrete dropoffs in pick quality (which will likely smooth out with more drafts), what is likely is that there are still certain bunches of picks that have similar value to each other.

Limitations:
In my opinion, the main limitation that came from the analysis involved the inability to analyze the types of players who were drafted by certain teams, whether they drafted for fit, or whether they aimed for who they saw as the best player available on the draft board. In my opinion, this is a crucial question to ask, however, it’s one that requires both an analysis of drafts in the long run, as well as a very heavy knowledge of NBA drafts, and team needs throughout the past few decades.

I think knowing whether fit or best player available is better is very important because that sort of decision starts to really matter once you get past the 10th pick, after which, most players who are drafted are average at best, and trying to get optimal returns from picks is both very important, and very difficult. Knowing what strategy is best between the two is very important, and knowing when a certain player is such a good fit, or such a talented player that it overrides general patterns is a worthwhile question to ask.

Additionally, these findings do not account for the fact that some drafts are better than others, and some have more depth than others. In those cases, the optimal decision can potentially vary. Many drafts are weak, or don’t have much value past the first few picks, which means trading down is typically a very smart decision, however, in other drafts, the opposite is true. However, on average, there are many trades that teams make that are not very smart, and come from overvaluing certain picks.
