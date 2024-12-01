

# Mystic Dialogue

<!-- begin-content-flag -->

## Game Rules

### Overview

**Mystic Dialogue** is a cooperative game for two players, inspired by _Mysterium_. It emphasizes abstract communication through dream cards to convey information without direct verbal or non-verbal cues. The game can be played in person or over a chat interface (e.g. I have implemented the game through a [Discord bot](https://github.com/felixludos/ludos/blob/figged/ludos/games/mysterium/dialogue.py)).

### Required Materials

- A deck of **Mysterium** dream cards (or **Dixit** cards).
- A set of character cards from **Mysterium** (or similar).
- A set of location cards from **Mysterium** (or similar).

Note that it's not strictly necessary for the cards to be from **Mysterium**; any set of abstract dream-like images can work. See the figures [below](#example-cards-from-mysterium) for reference.

### Setup

**Select Roles**: 
- One player is the **Detective**. The detective starts out with a single target character card, and a set of location cards. Their goal is to identify the location paired with the target character.
- The other player is the **Ghost**. The ghost starts out with a set of character cards each paired with a location card. Their goal is to convey to the Detective the location card that is paired with the target character. Crucially, the Ghost starts out not knowing the target character, only the character-location pairs.

**Character and Location Cards**:
- Setup the character and location cards such that the Ghost can only see **six** randomly selected character cards each paired with a randomly selected location card.
- Meanwhile, the Detective can only see a subset of **four** candidate location cards that are part of the Ghost's set, as well as one randomly selected target character card out of the six available to the Ghost. Crucially, the target character must be paired with one of the four candidate locations. 
- Important: The Detective should not know the character-location pairs, and the Ghost should not know the target character or which locations are the candidate locations.

**Dream Cards**:
- Shuffle the dream cards and deal each player **seven** cards.

### Gameplay

**Turns**:
- Players take turns sending messages to each other.
- A message consists of **zero to seven** dream cards. If a player sends **zero** cards, they **pass**.
- After sending a message, players draw enough cards to replenish their hand back to seven. The cards that were sent are discarded. When the deck runs out, shuffle the discard pile to form a new deck.

**Communication Rules**:
- No verbal or non-verbal communication is allowed outside of the messages.
- Players should not see each other's play areas.

**Ending the Game**:
- The Detective can end the game at any time by announcing a chosen candidate location.
- If the selected location matches the one paired with the target character, both players win. If not, both players lose.
- The team's score is the **total number of dream cards** sent between both players during the game. As a tiebreaker, the total number of turns back and forth should also be recorded.
- A **lower score** reflects more efficient communication and better performance.

### Example Cards from Mysterium

<figure style="display: flex; flex-direction: column; align-items: center; max-width: 400px; margin: auto;">
  <img src="https://cf.geekdo-images.com/3l731kKlOAui_qhL9OeEmQ__imagepage/img/iIf5iZE3M4pwIiYeBvog2MY84LQ=/fit-in/900x600/filters:no_upscale():strip_icc()/pic2046185.jpg" alt="Mysterium dream cards" style="max-width: 100%; height: auto;"/>
  <figcaption>Figure 1: Example dream cards from Mysterium for reference</figcaption>
  <p></p>
</figure>
<figure style="display: flex; flex-direction: column; align-items: center; max-width: 400px; margin: auto;">
    <img src="https://cf.geekdo-images.com/z9wPY2tQ7wF_CAIBiTSZkA__imagepage/img/mX0QsIZLv4XpNrxVLh_KLVNlaIY=/fit-in/900x600/filters:no_upscale():strip_icc()/pic2046188.jpg" alt="Example Character Card" style="max-width: 100%; height: auto;"/>
    <figcaption>Figure 2: Example character cards</figcaption>
    <p></p>
</figure>
<figure style="display: flex; flex-direction: column; align-items: center; max-width: 400px; margin: auto;">
    <img src="https://cf.geekdo-images.com/p6ycy9AvoAgLqkPPBgBUXQ__imagepage/img/vAWabP_rev2RRFXYfQbrJBMWa50=/fit-in/900x600/filters:no_upscale():strip_icc()/pic2046182.jpg" alt="Example Location Card" style="max-width: 100%; height: auto;"/>
    <figcaption>Figure 3: Example location cards</figcaption>
    <p></p>
</figure>


---


## Strategic Analysis

### Developing an Implicit Language

In **Mystic Dialogue**, players face a communication challenge that relies on abstract reasoning and deduction. Without direct verbal or non-verbal cues, players must precisely convey complex ideas (the target character and location cards) using only dream cards—vivid, surreal images rich in symbolism and ambiguity (see [figures](#example-cards-from-mysterium) for examples). Here I will discuss how an effective communication strategy can be deduced from the game's mechanics alone, without the need for pre-established agreements or, of course, external communication.

The dream cards permit a variety of weak, subjective, and often ambiguous associations, resulting in a very noisy communication channel. In particular, since the deck of dream cards is quite large relative to the players' hands, it is generally unlikely that players will have any card that matches the target character or location especially well.
Consequently, players should base their messages on suspected (but obviously not pre-arranged - that would violate the point of the game) shared associatations to gradually converge on a shared understanding over many turns.

Since both players must communicate a specific card to the other (i.e. the Detective must communicate the target character, and the Ghost must communicate the corresponding location), the first deduction is to realize that the game naturally divides into two phases. It doesn't make sense for the Ghost to send any information about a location until they are reasonably confident they have identified the target character. Consequently, the game naturally divides into two separate phrases: (1) where the Detective sends clues to identify the target character, with the Ghost inferring the best match and verifying their hypothesis with their messages. Once both players are confident the target character is common knowledge, (2) the Ghost sends clues to identify the corresponding location, with the Detective probing/confirming their guesses.

### The Importance of Passing

One particularly challenging aspect is that not only do players have to communicate the target cards, but they must also communicate their degree of confidence in their understanding of the other player's messages to know when to transition to the next phase or end the game. This is where the strategic use of passing (i.e. sending zero card messages) becomes crucial. Naively we might think that a player only passes when they don't have any good cards to send, but that doesn't make sense as passing doesn't help the player draw new cards. Instead, passing can be interpretted as the player saying they have nothing more to say, thereby expressing they are ready to move on.

However, a single pass is obviously not enough to signal a phase transition. The other player might not be ready, or the pass might read as hesitation rather than confidence. Consequently, if I pass, and you send a message after, it would be a mistake for me to infer that we are not in the next phase. Instead, I should wait until you also pass, thereby signalling that you, being aware that I am ready to move on, agree. Even two consecutive passes do not necessarily suffice to infer consensus, as the initial pass might have been meant as a question or hesitation (e.g. something like "I may have some useful cards, but I'm not confident enough to send anything, please give me more information first"). However, a second consecutive pass can unambiguously be interpretted as agreement, so a third consecutive pass confirms that both players are ready to move on. Admittedly, this "3-pass-rule" might not strictly be necessary, but I contend that, without any pre-arranged communication protocol, a third consecutive pass is the most efficient unambiguous signal to transition to the next phase.

### Efficient and Effective Messages

Efficiency is paramount in **Mystic Dialogue**, as the team's score is determined by the total number of dream cards exchanged. Players are incentivized to communicate their messages using as few cards as possible while maintaining clarity. Obviously, players should strive to send cards that have strong, unambiguous associations with the intended character or location to rapidly reach consensus. However, given limited selection and the abstract nature of the dream cards, this can be challenging.

Inevitably, players will have cards in their hand that seem irrelevant or less useful, so-called "garbage" cards. Since the only way to get rid of these cards is to send them in a message, players need to make sure the "garbage" cards don't unintentionally mislead the other player. To derive a natural solution, let's consider how we would reasonably interpret a message of all seven cards from our partner. It seems exceedingly unlikely that all cards in our partner's hand match with the intended target, so instead we can infer that our partner is trying to get rid of garbage. In general, we might interpret any large number of cards in a message as a signal that the cards are not good matches with our target. 

Conversely, sending a single card is likely to be a strong signal that our partner thinks the card is a strong unambiguous match. However, when it comes to a small number of cards greater than one, there may be many interpretations. For example, perhaps we are meant to consider the commonalities between the cards, or perhaps the sender is trying to emphasize that each card is individually relevant, but perhaps in different ways. In any case, no matter how exactly we interpret the message, generally shorter messages can reasonably be interpreted as positive signals, while longer messages can be interpreted as negative signals.

Note that sending large messages is relatively expensive in terms of the team's score, so it is generally advisable to avoid sending large messages unless necessary. Rather than greedily discarding all garbage cards right away, only to later perhaps realize that one of them might actually be useful after all, it is better to cautiously send several messages with partially relevant information. 

### Advanced Strategies

For further optimization of when and how to balance clarity and efficiency of the communication it maybe useful to agree to a general strategy beforehand, beyond this strategy that follows from the game's mechanics alone assuming no pre-arranged protocol.
Here are a few potential ideas for more sophisticated strategies:

- **Contrastive Messaging**: Paying attention to which cards are not sent (or sent as garbage dumps) can be as informative as those that are. Players can deduce possible meanings based on the absence of certain cards.
- **Response Patterns**: Players might develop patterns in their messaging, in particular based on the number of cards sent. For example, following a single-card message with a pass to emphasize its importance or defining a two-card message as a question of some kind.
- **Dynamic Interpretation**: Adjusting interpretations based on the evolving context of the game, considering not just the cards themselves but the sequence and timing of messages.

However, it's important to note that overly complex strategies can backfire - especially when playing with new/other partners. I would suggest treating the setting where the players plan out a strategy beforehand as a separate variant - let's call it the "Intelligent Design" variant.

---


## Commentary

Our initial forays into **Mystic Dialogue** largely ended unsuccessfully because, without prior discussion on strategy, we frequently misinterpreted each other's messages and generally struggled to identify a reliable communication protocol. Over time, however, we noticed patterns emerging:

- **Positive vs Negative Signals:** The length of messages and the number of cards sent quickly became indicators of confidence or uncertainty, including the ability to "dump" garbage cards. A crucial element is being able to discriminate between multiple candidate characters or locations, however since the Detective only sees a single character, and only a subset of the locations, the Ghost cannot solely rely on negative signals.
- **Phases Were Essential:** Breaking down the task into a strict sequence enabled focusing on one objective at a time—first the character, then the location—thereby reducing confusion considerably.
- **Passing Became Meaningful:** We began to see passes not just as skips but as signals of confidence or requests to proceed.
- **Efficiency Improved Scores:** Being mindful of the number of cards exchanged we began experimenting with sequences of "partially relevant" clues, instead of costly discards.

These strategies emerged largely based on discussions of past games, but over time we realized that the protocol largely follows from the rules alone, rather than being arbitrary choices that have to be established by partners beforehand. As we became more familiar with the dynamics of the game, we were still only successfully about half the time, and our scores were generally around 50-80.
Doubtlessly, the strategy can be significantly improved by more advanced tactics if you do carefully design conventions beforehand, but even without conventions, the game is surprisingly deep and engaging.

### Reflections on Game Dynamics

The balance between success and failure in **Mystic Dialogue** is delicate. The game's reliance on abstract imagery and implicit communication means that even with solid strategies, success isn't guaranteed. Luck plays a role, particularly in the cards drawn and how well they can be associated with the target character or location.

We observed that our scores improved as we became more adept at utilizing our cards effectively. Instead of discarding "garbage" cards, we looked for creative ways to incorporate them into our messages. This not only reduced our total card count but also added depth to our communication.

### Further Ideas and Variants

There are numerous ways to expand the game both stylistically and mechanically. Most importantly, we noticed an issue where over time certain associations between dream cards and characters or locations became increasingly fixed in our group. This issue is largely shared with _Mysterium_ and _Dixit_, and can also be addressed in similar ways: simply by introducing new dream/character/location cards. 

However, I think it would be particularly interesting to use generative AI to create new dream cards - perhaps even on-the-fly. Specifically, we could use an unconditional generative model or by carefully tuning the parameters to produce rich, complex, and highly diverse dream-like images (reminiscient of Rorschach tests and Greebles). Additionally the targets can be replaced with dynamically generated photos of people (such as with [Style-GAN](https://thispersondoesnotexist.com/)), or even other modalities like audio snippets or words/phrases/poems.

Alternatively, the communication task can be made more complex by adding more layers or objectives. In particular, I would be interested in a question-answering-like setting where the Ghost is given a question but without any answers, and the Detective only sees multiple candidate answers. The goal is for the Detective to select the correct answer (without ever seeing the question). This would require a more complex communication protocol, enabling the Ghost to either (1) convey the question, if they can't answer it themselves, or (2) convey the answer directly (of course since the Ghost doesn't know the candidate answers, it may be difficult to discriminate between similar options).

## Conclusion

**Mystic Dialogue** presents a unique and challenging experience that pushes players to think creatively and collaboratively. The necessity of developing an implicit language elevates the game beyond simple deduction, requiring a blend of strategic thinking and intuitive understanding.

Our journey with the game highlighted both its strengths and areas for potential growth. By embracing the challenges and exploring new ideas, we found that **Mystic Dialogue** offers rich opportunities for engagement and enjoyment. Whether through incorporating new technologies like generative AI or refining our communication strategies, the game continues to evolve, promising fresh experiences with each playthrough.



<!-- end-content-flag -->
