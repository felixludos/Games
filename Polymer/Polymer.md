# Polymer

A casual social negotiation game.

- Required Materials: 2 packs of french playing cards, 1 timer
- 5-15 players
- Takes about 10 minutes

## Setup

Players should sit such that each player has a neighbor to their left and right.

Shuffle all the cards (without jokers) and deal the same number to each player depending on the number of players: 5 -> 16, 6 -> 14, 7 -> 12, 8 -> 10, 9 -> 9, 10 -> 8, 11 -> 8, 12 -> 7, 13 -> 7, 14 -> 6, 15 -> 6

Players should not look at their cards until the timer starts. Now setup a timer with N minutes where N is the number of players. The timer should be visible to all players.

## Gameplay

When all players are ready, start the timer, at which point all players can look at their cards.

Players can freely trade any of their cards with their immediate neighbors (to their left and right only), however they must always keep the same total number of cards.

Once a trade has been executed, it can only be undone if both players agree.

### Loaning

Optionally, you can allow players to temporarily loan out some of their cards to either neighbor, provided that they get sufficient cards back by the end of the game. During the game, a player may at any time “call in” their loan, at which point the debtor must immediately return the same number of cards to the loaner (or at least as many cards as they hold) before executing any other trades.

## Scoring

Once the timer reaches 0, all players must stop trading and now hold the same number of cards as they started with.

Each player’s receives a sequence score equal to the number of cards in the longest sequence of a single suit they hold in their hands. The ranks of the cards: A, 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K (and loops around, so A can both precede 2 and follow K)

Finally, each player receives victory points equal to the product of their score and the sum of their immediate neighbors’ scores. For example, if players A, B, C sit next to each other, and their longest sequences are 3, 5, and 6 respectively, then player B receives 5 * (3+6) = 45 victory points.

Winner is the player with the most victory points. If there is a tie, then winner is the player with the highest rank card in their sequence (A being the smallest, and K being the largest). The next tie breaker is the highest card in the sequences of the player’s immediate neighbors, and the final tie breaker is the highest card of the other neighbor.

