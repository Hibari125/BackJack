import random
shapes = ["kříže", "srdce", "piky", "káry"]
cards = ["E","2","3","4","5","6","7","8","9","10","P","D","K"]
value_cards = {"E": 11,"2": 2,"3": 3,"4": 4,"5": 5,"6": 6,"7": 7,"8": 8,"9": 9,
"10": 10,"P": 10,"D": 10,"K": 10}

def generate_deck():
    deck = []
    for shape in shapes:
        for card in cards:
            deck.append((card, shape))
    random.shuffle(deck)
    return deck
def getcardsvalue(card):
    key = card[0]
    value = value_cards[key]
    return value

def turn(deck, score):
    card = deck.pop(0)
    print(">>", card)
    cardvalue = getcardsvalue(card)
    new_score = score + cardvalue
    return new_score

def playGame():

    deck = generate_deck()
    dealerscore = 0
    playerscore = 0

    print("_________________________________D____________________________________")
    dealerscore = turn(deck, dealerscore);
    dealerscore = turn(deck, dealerscore);
    print("Dealer Score:", dealerscore)

    print("_________________________________P____________________________________")
    playerscore = turn(deck, playerscore);
    playerscore = turn(deck, playerscore);
    print("Tvoje Score:", playerscore)

    print("_______________________________Game Begin___________________________________")
    keeplaying = True
    while keeplaying:
        user_choice = input("Bereš nebo Stojíš:  ")
        if (user_choice == "Bereš"):
            playerscore = turn(deck, playerscore)
            print("Tvoje score:", playerscore)
            print("Dealer score:", dealerscore)
            if playerscore > 21:
                print("Prohrál jsi")
                keeplaying = False
        elif (user_choice == "Stojíš"):
            print("_________________________________D____________________________________")
            dealerscore = turn(deck, dealerscore)
            print("Tvoje score:", playerscore)
            print("Dealer score:", dealerscore)
            if dealerscore > 21:
                print("Dealer to nezvládl, Vyhrál jsi")
            elif dealerscore == playerscore:
                print("Remíza, Máte identické score s Dealerem")
            elif dealerscore > playerscore:
                print("Prohrál jsi, Dealer má více bodů")
            else:
                print("Vyhrál jsi")
            keeplaying = False
        else:
            print("Zvol pouze zobrazené varianty")
playGame()
