# Polymer

A casual social negotiation game.

- Required Materials: 2 packs of french playing cards, 1 timer
- 5-15 players
- Takes about 10 minutes

## Setup

Players should sit such that each player has a neighbor to their left and right.

Shuffle all the cards (without jokers) and deal the same number to each player depending on the number of players: 5 -> 20, 6 -> 17, 7 -> 14, 8 -> 13, 9 -> 11, 10 -> 10, 11 -> 9, 12 -> 8, 13 -> 8, 14 -> 7, 15 -> 6

Players should not look at their cards until the timer starts. Now setup a countdown timer to 10 minutes. The timer should be visible to all players.

## Gameplay

When all players are ready, start the timer, at which point all players can look at their cards.

Players can freely (asynchronously) trade any of their cards with their immediate neighbors (to their left and right only), however they must always keep the same total number of cards.

Once a trade has been executed, it can only be undone if both players agree.

### Loaning

Players can temporarily loan out some of their cards to either neighbor, provided that they get sufficient cards back by the end of the game. During the game, a player may at any time “call in” their loan, at which point the debtor must immediately return the same number of cards to the loaner (or at least as many cards as they hold) before executing any other trades.

## Scoring

Once the timer reaches 0, all players must stop trading and now hold the same number of cards as they started with.

Each player shows all the patterns in their hand, where a pattern can be either a group or a sequence. A group is a set of at least two cards with the same rank. A sequence is a set of at least two cards with the same suit and consecutive ranks. Each card can be used in at most one group or sequence. The ranks of the cards: A, 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K (and loops around, so A can both precede 2 and follow K).

The player's final score is: (number of cards in their longest pattern) * (sum of the lengths of their immediate neighbors' longest patterns) + (sum of the (lengths-1) of all other patterns in the players hand)

For example, if a player has a sequence of length 4, a sequence of length 3 and two pairs, and their neighbors' longest patterns are a group of length 5 and sequence of length 6, then their score is: 4 * (5+6) + (3-1) + (2-1) + (2-1) = 48.

In the rare case of a tie, the first tiebreaker is the highest rank card in the player's longest pattern (the highest possible rank is a K for this purpose). The second and third tiebreaker is the higher and lower of the two ranks in the player's neighbors' longest patterns, respectively.


