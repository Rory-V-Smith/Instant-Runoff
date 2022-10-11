# Instant-Runoff
Calculates the winner of an election using an 'instant-runoff' algorithm, a ranked choice voting system, per the below.
>./runoff Alice Bob Charlie
>Number of voters: 5
>Rank 1: Alice
>Rank 2: Bob
>Rank 3: Charlie

>Rank 1: Alice
>Rank 2: Charlie
>Rank 3: Bob

>Rank 1: Bob
>Rank 2: Charlie
>Rank 3: Alice

>Rank 1: Bob
>Rank 2: Alice
>Rank 3: Charlie

>Rank 1: Charlie
>Rank 2: Alice
>Rank 3: Bob

>Alice

Completed in part of Harvard's [CS50 - Introduction to Computer Science, 2020](https://cs50.harvard.edu/x/2020/)
This was pset 3: [Runoff](https://cs50.harvard.edu/x/2020/psets/3/runoff/)

### Background
In a ranked-choice system, voters can vote for more than one candidate. Instead of just voting for their top choice, they can rank the candidates in order of preference. 
Each voter, in addition to specifying their first preference candidate, can also indicated their second and third choices. This system account can account for a tied elections and can calculate a winner.
 In an instant runoff election, voters can rank as many candidates as they wish. If any candidate has a majority (more than 50%) of the first preference votes, that candidate is declared the winner of the election.
If no candidate has more than 50% of the vote, then an “instant runoff” occurrs. The candidate who received the fewest number of votes is eliminated from the election, and anyone who originally chose that candidate as their first preference now has their second preference considered. Why do it this way? Effectively, this simulates what would have happened if the least popular candidate had not been in the election to begin with.
The process repeats: if no candidate has a majority of the votes, the last place candidate is eliminated, and anyone who voted for them will instead vote for their next preference (who hasn’t themselves already been eliminated). Once a candidate has a majority, that candidate is declared the winner.
