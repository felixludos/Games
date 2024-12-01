

# Mystic Dialogue

<!-- begin-content-flag -->

## Game Rules

### Overview

**Mystic Dialogue** is a cooperative game for two players, inspired by _Mysterium_. It emphasizes abstract communication through dream cards to convey information without direct verbal or non-verbal cues. The game can be played in person or over a chat interface (e.g. I have implemented the game through a [Discord bot](https://github.com/felixludos/ludos/blob/figged/ludos/games/mysterium/dialogue.py)).

### Required Materials

- A deck of **Mysterium** dream cards (or **Dixit** cards).
- A set of character cards from **Mysterium** (or similar).
- A set of location cards from **Mysterium** (or similar).

### Setup

**Select Roles**: 
- One player is the **Detective**. The detective starts out with a single target character card, and a set of location cards. Their goal is to identify the location paired with the target character.
- The other player is the **Ghost**. The ghost starts out with a set of character cards each paired with a location card. Their goal is to convey to the Detective the location card that is paired with the target character. Crucially, the Ghost starts out not knowing the target character, only the character-location pairs.

**Character and Location Cards**:
- Setup the character and location cards such that the Ghost can only see **six** randomly selected character cards each paired with a randomly selected location card.
- Meanwhile, the Detective can only see a subset of **four** candidate location cards that are part of the Ghost's set, as well as one randomly selected target character card out of the six available to the Ghost. Crucially, the target character must be paired with one of the four candidate locations. 
- Important: The Detective should not know the character-location pairs, and the Ghost should not know the target character or which locations are the candidate locations.

**Dream Cards**:
- Shuffle and evenly split the dream cards into two decks: one for the Detective and one for the Ghost.
- Each player draws **seven** dream cards from their respective decks.


### Gameplay

**Turns**:
- Players take turns sending messages to each other.
- A message consists of **zero to seven** dream cards. If a player sends **zero** cards, they **pass**.
- After sending a message, players draw enough cards to replenish their hand back to seven (unless they passed).

**Communication Rules**:
  - No verbal or non-verbal communication is allowed outside of the messages.
  - Players should not see each other's play areas.

**Ending the Game**:
  - The Detective can end the game at any time by announcing a chosen candidate location.
  - If the selected location matches the one paired with the target character, both players win. If not, both players lose.
  - The team's score is the **total number of dream cards** sent between both players during the game.
  - A **lower score** reflects more efficient communication and better performance.

---

## Strategic Analysis

### Developing an Implicit Language

Due to the abstract and limited communication channel, players must develop an implicit language to convey information effectively. This involves understanding how to use dream cards and passing strategically.

#### Understanding Dream Cards

- **Dream Cards**: Abstract images rich in symbolism, colors, and objects.
- **Association**: Players must find connections between the dream cards and the characters or locations.

### Communication Strategies

#### Passing as a Signal

- **Passing (Sending Zero Cards)**:
  - Indicates the player has nothing more to communicate at the moment.
  - Can signal confidence or readiness to move to the next phase.
  - Helps in coordinating the transition between phases without explicit communication.

#### Phases and Transition

1. **Phase 1 - Character Communication**:
   - The Detective focuses on sending dream cards associated with the target character.
   - The Ghost interprets these messages to deduce the character.

2. **Transition Between Phases**:
   - A sequence of **three consecutive passes** signals the mutual agreement to move to the next phase.
     - Example:
       - Detective passes (indicating readiness).
       - Ghost passes (confirming understanding).
       - Detective passes again (confirming transition).

3. **Phase 2 - Location Communication**:
   - The Ghost sends dream cards associated with the location paired with the target character.
   - The Detective interprets these messages to identify the correct location.

#### Efficient Use of Cards

- **Minimizing Cards Sent**:
  - Aim to communicate effectively using as few cards as possible to achieve a lower score.
- **Sending Relevant Cards**:
  - Send cards that have a strong and clear association with the intended character or location.
- **Avoiding "Garbage" Cards**:
  - Discarding irrelevant cards by sending them can be costly; it's better to find creative ways to use them if possible.

### Advanced Techniques

#### Interpreting Message Size

- **Single Card Messages**:
  - Often indicate a strong association.
  - Draws the recipient's attention to a specific idea or symbol.

- **Multiple Card Messages**:
  - May dilute the message if not carefully selected.
  - Can be interpreted as discarding irrelevant cards (especially if sending four or more).

#### Collaborative Dialogue

- **Responding to Messages**:
  - Tailor messages based on the partner's previous cards.
  - Engage in a back-and-forth to confirm hypotheses and refine understanding.

#### Signal Reinforcement

- **Repeated Passing**:
  - Passing multiple times after sending a key card emphasizes its importance.
  - Helps reinforce critical messages in a noisy communication channel.

---

# Strategic Analysis

In "Mystic Dialogue," the challenge is to communicate complex information using only dream cards—a medium rich in ambiguity. From the game's rules, we can logically deduce effective strategies and an implicit language that naturally emerges during play.

## Deriving Communication Strategies from Game Mechanics

### The Significance of Passing

Passing, or choosing to send zero cards, isn't just inaction; it's a deliberate signal. Since passing doesn't help a player draw new cards, we can infer that:

- **Passing indicates confidence or completion.** A player passes when they believe they've communicated enough or are ready to proceed.
- **It's a tool for synchronization.** Without the ability to see each other's hands or communicate directly, passing becomes a way to align intentions.

Thus, passing evolves into a strategic element derived from the game's constraints.

### Establishing Phases of Communication

Given the objectives:

1. The Detective must communicate the target character to the Ghost.
2. The Ghost must then communicate the corresponding location back to the Detective.

It's logical to divide the game into two distinct phases to prevent confusion:

- **Phase One:** Focus on the character.
- **Phase Two:** Focus on the location.

This phasing ensures both players concentrate on the same objective, reducing the risk of misinterpretation.

### Transitioning Between Phases

A method to transition smoothly between phases can be deduced:

- **Three Consecutive Passes Signal a Phase Shift:**
  1. **First Pass (Detective):** Indicates readiness to move on.
  2. **Second Pass (Ghost):** Confirms understanding.
  3. **Third Pass (Detective):** Finalizes the transition.

This pattern minimizes ambiguity, allowing both players to deduce that it's time to switch focus without explicit communication.

### Efficient Use of Dream Cards

Since the total number of cards exchanged determines the team's score, it's advantageous to communicate effectively with fewer cards:

- **Single-Card Messages:** Highlight a strong association and draw attention to specific details.
- **Avoid Large Card Dumps:** Sending many cards to discard "garbage" increases the score unnecessarily.
- **Creative Utilization:** Finding ways to make less relevant cards meaningful reduces the need to discard them.

## Emergence of an Implicit Language

These strategies aren't pre-arranged but arise logically from the game's rules:

- **Passing as Communication:** Recognizing passes as signals comes from understanding their impact within the game's mechanics.
- **Phased Focus:** Dividing the game into phases is a natural solution to the challenge of conveying multiple pieces of information sequentially.
- **Card Selection as Language:** The number and content of cards sent become a means of conveying emphasis and intent.

Through logical deduction and shared constraints, players develop an implicit language that enhances their ability to achieve the game's objectives.

---

# Commentary

Playing "Mystic Dialogue" revealed that success depends on deriving strategies directly from the game's mechanics. Initially, without discussing tactics, we struggled. Misinterpretations were common, and games often ended unsuccessfully.

Over time, we noticed patterns emerging:

- **Passing Became Meaningful:** We began to see passes not just as skips but as signals of confidence or requests to proceed.
- **Phases Were Essential:** Focusing on one objective at a time—first the character, then the location—reduced confusion and improved coordination.
- **Efficiency Improved Scores:** Being mindful of the number of cards exchanged led us to find creative ways to use less relevant cards, avoiding costly discards.

These strategies seemed to emerge naturally, guided by the game's rules. While alternative methods might exist, the ones we adopted felt like logical solutions to the challenges presented.

## Further Ideas and Variants

To keep the game fresh and prevent reliance on memorized associations:

- **Dynamic Card Generation:** Introducing new dream cards, perhaps using generative tools, would prevent fixed associations and require continuous adaptation.
- **Complex Communication Tasks:** Adding more layers to what needs to be communicated could encourage the development of new strategies.
- **Adjusting Game Structure:** Experimenting with the number of phases or altering objectives might offer fresh challenges and insights.

"Mystic Dialogue" thrives on the players' ability to adapt and deduce. By embracing the constraints and letting strategies emerge from the rules themselves, each game becomes a unique exploration of collaborative communication.

<!-- end-content-flag -->
