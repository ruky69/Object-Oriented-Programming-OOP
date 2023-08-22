## Object-Oriented Programming (OOP) in Blackjack Game

The provided code showcases the application of Object-Oriented Programming (OOP) principles to model various components of a Blackjack game:

### Classes

1. **Card:** Represents individual playing cards with attributes for suit and rank. It includes methods for retrieving suit and rank, drawing the card, and a `__str__` method for string representation.

2. **Hand:** Represents a player's or dealer's hand of cards. It tracks the hand's cards, value, and the presence of an Ace. It offers methods for adding cards, calculating the hand's value, drawing cards, and a `__str__` method for string representation.

3. **Deck:** Models a deck of playing cards. It features methods for shuffling the deck, dealing cards, and a `__str__` method for string representation.

### Object Instantiation

- Objects of these classes are instantiated during program execution. For instance, `player_hand = Hand()` creates a player's hand, and `deck = Deck()` creates a deck of cards.

### Encapsulation

- Each class encapsulates both data and functionality pertinent to its specific component. For instance, the `Hand` class encapsulates logic for calculating hand values, managing cards, and drawing cards.

### Abstraction

- The classes abstract the underlying implementation details from the main program. For example, the `Deck` class manages card shuffling and dealing without exposing the intricate mechanisms.

### Inheritance

- While explicit inheritance isn't directly demonstrated, all classes implicitly inherit from the base Python object class. In more complex scenarios, explicit inheritance could be used to create specialized subclasses with shared behaviors. In the context of the Blackjack game, creating subclasses for different types of players (e.g. amateur or professional) that inherit from a common base class ('Player') is one way of applying inheritance to the project.

```class Player: 
    def __init__(self):
        self.hand = Hand()


class AmateurPlayer(Player):
    def __init__(self):
        super().__init__()


class ProfessionalPlayer(Player):
    def __init__(self):
        super().__init__()```


### Polymorphism

- Though not explicitly shown, the code can be extended to include polymorphism. By creating different classes with shared methods but distinct implementations, it becomes feasible to introduce game variations or additional features. In the context of the game, polymorphism can be used to call common methods on different objects, regardless of whether they are amateurs or professional players.


def player_turn(player):
    print(f"{player.__class__.__name__}'s turn:")
    choice = input("Hit or stand? ").lower()
    if choice == "hit":
        player.hand.card_add(deck.deal())
    elif choice == "stand":
        pass  # Player chooses to stand
    else:
        print("Invalid choice")
# Usage

beginner = AmateurPlayer()
pro = ProfessionalPlayer()
player_turn(beginner)
player_turn(pro)


### Class Interaction

- The classes interact harmoniously throughout the program. The `Deck` class initializes and shuffles the deck. The `Hand` class manages both player and dealer hands, handling card addition, value calculation, and drawing.

This code exemplifies the application of OOP concepts to create a functional Blackjack game with modular and organized code structure.
