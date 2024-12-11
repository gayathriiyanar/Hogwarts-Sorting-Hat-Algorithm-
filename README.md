# Hogwarts-Sorting-Hat-Algorithm-
def get_student_traits():
    """ Ask the student questions to determine their traits. """
    print("Welcome to the Hogwarts Sorting Hat Ceremony!")
    print("Answer these questions to the best of your ability, and I will sort you into a house.")
    
    bravery = input("Do you value bravery and courage? (yes/no): ").lower()
    loyalty = input("Do you value loyalty and hard work? (yes/no): ").lower()
    intelligence = input("Do you value intelligence and creativity? (yes/no): ").lower()
    ambition = input("Do you value ambition and cunning? (yes/no): ").lower()
    
    return bravery, loyalty, intelligence, ambition

def determine_house(bravery, loyalty, intelligence, ambition):
    """ Determine the Hogwarts house based on the student's traits. """
    # Scoring system based on answers
    scores = {'Gryffindor': 0, 'Hufflepuff': 0, 'Ravenclaw': 0, 'Slytherin': 0}
    
    # Gryffindor: bravery and courage
    if bravery == "yes":
        scores['Gryffindor'] += 1
    
    # Hufflepuff: loyalty and hard work
    if loyalty == "yes":
        scores['Hufflepuff'] += 1
        
    # Ravenclaw: intelligence and creativity
    if intelligence == "yes":
        scores['Ravenclaw'] += 1
    
    # Slytherin: ambition and cunning
    if ambition == "yes":
        scores['Slytherin'] += 1
    
    # Find the house with the highest score
    max_score = max(scores.values())
    possible_houses = [house for house, score in scores.items() if score == max_score]
    
    # If there's a tie, choose randomly
    import random
    chosen_house = random.choice(possible_houses)
    
    return chosen_house

def sorting_hat():
    """ Main function to execute the sorting process. """
    bravery, loyalty, intelligence, ambition = get_student_traits()
    house = determine_house(bravery, loyalty, intelligence, ambition)
    print(f"\nThe Sorting Hat has spoken! You are in {house}!")
    
# Execute the Sorting Hat ceremony
sorting_hat()
