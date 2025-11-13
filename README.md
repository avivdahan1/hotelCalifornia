pokemon_list = [
    {"name": "Pikachu", "type": "Electric", "attack": 55, "defense": 40, "level":
5, "wins": 2},
    {"name": "Charmander", "type": "Fire", "attack": 52, "defense": 43, "level":
5, "wins": 3}
]
def update_pokemon(pokemon_list,name):
    #name = pokemon to upgrade
    #pokenmone list = list of pokemon
    #return true if i upgrade if not false
    for pokemon in pokemon_list:
        if pokemon["name"] == name and pokemon["wins"]>0:
           pokemon["level"]+=(pokemon["wins"])
           return True
    return False
def show_statistics(pokemon_list):
    attack = 0
    avg_lvl = 0
    fance = 0
    the_poki = ''
    the_poki_def = ''
    milon = {"strongest pokemon":" "
             ,"weakest pokemon":" ","avg lvl":""}



    for pokemon in pokemon_list: #check who is the strongesrt pokimon
        for pokemon2 in pokemon_list:
            if pokemon["attack"]>attack:
                attack =pokemon["attack"]
                the_poki = pokemon["name"]
    for pokemon3 in pokemon_list:         #ממוצע רמות
        avg_lvl += pokemon3["level"]

    avg_lvl/=len(pokemon_list)

    for pokemon4 in pokemon_list: #weak def
        for pokemon5 in pokemon_list:
            if pokemon4["defense"]<pokemon5["defense"]:
                fance = pokemon4["defense"]
                the_poki_def = pokemon4["name"]

    milon["strongest pokemon"]=the_poki
    milon["weakest pokemon"]=the_poki_def
    milon["avg lvl"]=avg_lvl
    return milon
print(update_pokemon(pokemon_list,"Pikachu"))
print(update_pokemon(pokemon_list,"Charmander"))
print(show_statistics(pokemon_list))

def add_pokemon(pokemon_list: list, name: str, p_type: str, attack: int, defense: int) -> None:
    pass
def find_pokemon(pokemon_list, name, index=0):
    pass
def battle(pokemon_list, name1, name2):
    pass
def show_battle_history(battle_history):
    pass
def show_pokemons(pokemon_list):
    pass
def main():
    name = input("pokemon name: ")
    p_type = input("pokemon type: ")
    attack = int(input("pokemon attack"))
    defense = int(input("pokemon defense"))
