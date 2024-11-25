# Pokedex Program in Python
import sys

pokedex = [
    {"name": "Pikachu", "type": "Electric", "hp": 35, "attack": 55, "defense": 40},
    {"name": "Charmander", "type": "Fire", "hp": 39, "attack": 52, "defense": 43},
    {"name": "Bulbasaur", "type": "Grass/Poison", "hp": 45, "attack": 49, "defense": 49},
    {"name": "Squirtle", "type": "Water", "hp": 44, "attack": 48, "defense": 65},
    {"name": "Jigglypuff", "type": "Normal/Fairy", "hp": 115, "attack": 45, "defense": 20},
    {"name": "Meowth", "type": "Normal", "hp": 40, "attack": 45, "defense": 35},
    {"name": "Psyduck", "type": "Water", "hp": 50, "attack": 52, "defense": 48},
    {"name": "Machop", "type": "Fighting", "hp": 70, "attack": 80, "defense": 50},
    {"name": "Geodude", "type": "Rock/Ground", "hp": 40, "attack": 80, "defense": 100},
    {"name": "Eevee", "type": "Normal", "hp": 55, "attack": 55, "defense": 50},
    {"name": "Vulpix", "type": "Fire", "hp": 38, "attack": 41, "defense": 40},
    {"name": "Growlithe", "type": "Fire", "hp": 55, "attack": 70, "defense": 45},
    {"name": "Poliwag", "type": "Water", "hp": 40, "attack": 50, "defense": 40},
    {"name": "Abra", "type": "Psychic", "hp": 25, "attack": 20, "defense": 15},
    {"name": "Magnemite", "type": "Electric/Steel", "hp": 25, "attack": 35, "defense": 70},
    {"name": "Diglett", "type": "Ground", "hp": 10, "attack": 55, "defense": 25},
    {"name": "Mankey", "type": "Fighting", "hp": 40, "attack": 80, "defense": 35},
    {"name": "Slowpoke", "type": "Water/Psychic", "hp": 90, "attack": 65, "defense": 65},
    {"name": "Doduo", "type": "Normal/Flying", "hp": 35, "attack": 85, "defense": 45},
    {"name": "Gastly", "type": "Ghost/Poison", "hp": 30, "attack": 35, "defense": 30},
    {"name": "Onix", "type": "Rock/Ground", "hp": 35, "attack": 45, "defense": 160},
    {"name": "Krabby", "type": "Water", "hp": 30, "attack": 105, "defense": 90},
    {"name": "Voltorb", "type": "Electric", "hp": 40, "attack": 30, "defense": 50},
    {"name": "Cubone", "type": "Ground", "hp": 50, "attack": 50, "defense": 95},
    {"name": "Koffing", "type": "Poison", "hp": 40, "attack": 65, "defense": 95},
    {"name": "Rhyhorn", "type": "Ground/Rock", "hp": 80, "attack": 85, "defense": 95},
    {"name": "Horsea", "type": "Water", "hp": 30, "attack": 40, "defense": 70},
    {"name": "Chansey", "type": "Normal", "hp": 250, "attack": 5, "defense": 5},
    {"name": "Tangela", "type": "Grass", "hp": 65, "attack": 55, "defense": 115},
    {"name": "Electabuzz", "type": "Electric", "hp": 65, "attack": 83, "defense": 57},
    {"name": "Magmar", "type": "Fire", "hp": 65, "attack": 95, "defense": 57},
    {"name": "Pinsir", "type": "Bug", "hp": 65, "attack": 125, "defense": 100},
    {"name": "Lapras", "type": "Water/Ice", "hp": 130, "attack": 85, "defense": 80},
    {"name": "Snorlax", "type": "Normal", "hp": 160, "attack": 110, "defense": 65},
    {"name": "Articuno", "type": "Ice/Flying", "hp": 90, "attack": 85, "defense": 100},
    {"name": "Zapdos", "type": "Electric/Flying", "hp": 90, "attack": 90, "defense": 85},
    {"name": "Moltres", "type": "Fire/Flying", "hp": 90, "attack": 100, "defense": 90},
    {"name": "Dragonite", "type": "Dragon/Flying", "hp": 91, "attack": 134, "defense": 95},
    {"name": "Mewtwo", "type": "Psychic", "hp": 106, "attack": 110, "defense": 90},
    {"name": "Mew", "type": "Psychic", "hp": 100, "attack": 100, "defense": 100},
]

# Function to display all Pokémon
def display_pokedex():
    print("\n=== Pokédex ===")
    for idx, pokemon in enumerate(pokedex, start=1):
        print(f"{idx}. {pokemon['name']} (Type: {pokemon['type']}) - HP: {pokemon['hp']}, Attack: {pokemon['attack']}, Defense: {pokemon['defense']}")
    print()

# Function to search for a Pokémon by name
def search_pokemon():
    name = input("Enter the Pokémon name to search: ").capitalize()
    for pokemon in pokedex:
        if pokemon["name"] == name:
            print(f"\nFound: {pokemon['name']} (Type: {pokemon['type']})")
            print(f"HP: {pokemon['hp']}, Attack: {pokemon['attack']}, Defense: {pokemon['defense']}\n")
            return
    print(f"\nPokémon '{name}' not found in the Pokédex.\n")

# Function to add a new Pokémon
def add_pokemon():
    print("\n=== Add a New Pokémon ===")
    name = input("Name: ").capitalize()
    type_ = input("Type: ").capitalize()
    hp = int(input("HP: "))
    attack = int(input("Attack: "))
    defense = int(input("Defense: "))
    
    pokedex.append({"name": name, "type": type_, "hp": hp, "attack": attack, "defense": defense})
    print(f"\nPokémon '{name}' added to the Pokédex!\n")

# Main menu
def main_menu():
    while True:
        print("=== Pokédex Menu ===")
        print("1. View all Pokémon")
        print("2. Search for a Pokémon")
        print("3. Add a new Pokémon")
        print("4. Exit")
        choice = input("Choose an option (1-4): ")
        
        if choice == "1":
            display_pokedex()
        elif choice == "2":
            search_pokemon()
        elif choice == "3":
            add_pokemon()
        elif choice == "4":
            print("Exiting the Pokédex. Goodbye!")
            sys.exit()
        else:
            print("Invalid choice. Please try again.\n")

# Run the program
if __name__ == "__main__":
    main_menu()# Baptiste
