# Polymer

<!-- begin-content-flag -->

A casual social negotiation game created in September 2023 with the help of several colleaguse at the IMPRS - Thank you for your enthusiasm and feedback!

- **Players**: 5-15 (recommended 6-10)
- **Materials**: two packs of french playing cards (2x52 cards, no jokers), 1 timer, optionally some tokens to serve as "good faith tokens"
- **Duration**: Takes about 15 minutes

## **Setup**
1. **Seating**: Players sit in a circle (such that each player has a neighbor on their left and right).
2. **Cards**: Shuffle all cards and deal the following number per player:
   - 5 players: 20 cards each
   - 6 players: 17 cards each
   - 7 players: 14 cards each
   - 8 players: 13 cards each
   - 9 players: 11 cards each
   - 10 players: 10 cards each
   - 11 players: 9 cards each
   - 12 players: 8 cards each
   - 13 players: 8 cards each
   - 14 players: 7 cards each
   - 15 players: 6 cards each
   - (if there are extra cards remaining, return them to the box without looking at them)
3. **Timer**: Set a countdown timer for 10 minutes and make it visible to all players.
4. **Initial Hands**: Players do not look at their cards until the timer starts.
5. **Good Faith Tokens** (GFT): if you are playing with GFTs, distribute them evenly among all players (each player should have at least 2-3 tokens)

## **Gameplay**

**Start the Timer**: When the timer begins, players may look at their cards.

**Trading**: Players may freely trade their cards but only with their immediate neighbors to their left and right. Specifically, there are two types of trades:
- **Swap**: Exchange the same number of cards between players.
- **Loan**: Exchange different number of cards, but the debtor must return the same number by the end of the game. The loaner may "call in" their loan at any time, in which case the debtor must return the same number of cards before making further swaps. However, debtors may choose what cards to return.

A trade may only be completed if both parties agree to it.

GFTs may also freely be traded (for example, as additional incentives).

## **Scoring**
1. **End of Timer**: When the timer reaches 0, trading stops, and each player must have the same number of cards they started with (so all loans must be repaid immediately). (GFTs are not returned)

2. **Polymers**
   - each player reveals the longest polymer they formed where a polymer is a set of cards comprised of partially overlapping "Sequences" and "groups" of 3 cards each:

     - **Sequences**: All cards in a sequence must have the **same suit** with sequentially changing ranks, where looping back around from K → A → 2 **is** allowed.
     - **Groups**: All cards in a group must have the **same rank with all different suits**.

   - For a polymer to be valid, each card in the polymer must form a valid sequence or group with each of its adjacent cards. Note that the all adjacent cards need not be part of the same pattern (see example 3)

   - Some examples of valid polymers are:
     1. 2♠, 3♠, 4♠, 5♠ - a sequence of 4, equivalent to two overlapping sequences.
     2. 6♠, 6♥, 6♦, 6♣ - a group of 4, equivalent to two overlapping groups.
     3. K♠, A♠, 2♠, 3♠ - a sequence of 4, equivalent to two overlapping sequences (note that K → A → 2 is allowed).
     4. 4♠, 5♠, 6♠, 6♥, 6♦ - an overlapping sequence and a group.
     5. 6♠, 5♠, 4♠, 5♠, 6♠ - two overlapping sequences of 3
     6. 7♠, 7♥, 7♦, 7♠ - eventhough there are two 7♠, they are part of different groups (7♠, 7♦, 7♠) and (7♠, 7♥, 7♠).
     7. 8♠, 8♦, 8♣, 8♠, 8♦ - a group of 5, equivalent to two overlapping groups.
     8. K♠, Q♠, J♠, J♥, J♦, Q♦, K♦ - two sequences with a group in the middle (compare this to the invalid example 3)

   - Some examples of invalid polymers are:
     1. 7♠, 7♦, 7♠ - the two 7♠ are part of the same group, so this is invalid.
     2. 7♠, 7♥, 7♠, 7♦ - the two 7♠ are part of the same group (the first in the polymer), so this is invalid. Note that the only difference to valid example 4 above is the order of the cards, so order matters!
     3. K♠, Q♠, J♠, J♦, Q♦, K♦ - the two sequences are not overlapping (specifically the J♠, J♦ don't form a valid pattern with any adjacent cards), but if you separate them into two independent sequences (remember once cards are face up, they can freely be rearranged), the two sequences are valid.

3. **Score Calculation**
   - Your final score = (Length of your polymer) × (Sum of the lengths of your neighbors' polymers).
   
4. **Example**
   - Your polymer has length 4
   - Neighbors have a polymer of length 5 and 6.
   - Your score: \( 4 × (5 + 6) = 44 \).

5. **Tiebreakers**
   - If you are playing with GFTs, then the player with the most GFTs at the end of them wins the first tiebreaker.
   - Otherwise, the player with the most face cards (K, Q, J) in their hand
   - The final tiebreaker is the total number of face cards in the hands of your two immediate neighbors.

It is generally recommended to player several rounds and then average the scores of each player over all rounds.

## Handicaps

If there are extra cards remaining after dealing each player their initial hand cards, you may give some players a handicap by dealing them extra cards. (All players should still end up with the same number of cards as they started with).

## Variant: Cosmic Rays

This variant requires some jokers to be included into the deck before shuffling (select any number of jokers, but 2-4 is recommended). For each joker that is added, remove one regular card at random and place these cards in the middle of the table face down.

Once the timer has started, players may "play" a joker from their hand at any time during the game by revealing it on the table and taking either of these actions: 
- **collide** - Select one of your immediate neighbors as targets. The target must immediately present their hand, and you may take one of their hand cards at random (without looking). After that the target gets to add the joker that was just played to their hand. (Optionally you can play with the rule that cosmic rays cannot change directions around the table)
- **absorb** - Draw one of the face down cards in the middle of the table, then the joker card is left face up on the table for the remainder of the game.

## Commentary

The main game dynamic is to conduct a, often somewhat chaotic, flurry of trades as players demand and offer various cards to lengthen their polymers. One additional dynamic that emerges almost immediately as a result is the formation of "long distance" trade routes, as you overhear some more distant neighbor suggesting a lucrative trade. Provided all the links in the chain (i.e. the players between you and the other party of the trade) permit the trade, the long distance trade is successful. Otherwise, it may be possible to sweeten the deal for any hesitating links, or perhaps, in extreme cases, you may even be able to go the other way around the table.

Since each player's score is partially dependent on their immediate neighbors success, generally it is advisable to permit trades even if you do not directly benefit from it. However, there is another layer to the strategy, which may suggest more careful consideration before signing off on all the goods that pass between you. Although it is in your interest for your immediate neighbors to build longer polymers, usually your own length is a larger factor. Additionally, the polymers of the neighbors of your neighbors (not including yourself, call them the 2nd degree neighbors), only benefit your neighbors not you. Thus, it is best for you if your 2nd degree neighbors fail, thereby ensuring that your neighbors don't outshine you.

If we consider clusters of players with long polymers as a distinct phase "long-chained" (LC) compared to a cluster of players with "short" polymers (SC), then the strategy can be expressed as: in additional to trying to be in the LC phase, it's important to avoid a phase boundary occuring between you and one of your neighbors. With everyone working towards the same goal, games can frequently end with everyone in an LC phase, or a few successful clusters with some often frustrated players in between. The crucial moment is when a player (often) suddenly decides to severely curtail or even halt trading, which can be very dangerous to their neighbors.

Strategies to avoid becoming a boundary:

- don't reveal your plans/cards - the more your neighbors (and their neighbors) know about what you are collecting and what cards you have, the easier it is for them to identify how long they can make advantageous trades. consequently loans are relatively expensive.
- form a monopoly - if you can try to collect as many cards of a single rank as possible to (at least regionally) have a long-term bargaining chip.
- keep your options open - rather than greedily trading for cards that will help you in the short term, consider building shorter polymers which either can be connected at some point or traded away for even greater prizes. notably this strategy can be very high risk (a little like a hot potato), as you may ruin their scores if they refuse to trade with you when you only have a few disconnected stumps, but if they do trade with you, you may be able to outsource the damage beyond your immediate neighbors 


<!-- end-content-flag -->
