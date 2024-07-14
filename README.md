- 👋 Hi, I’m @DJFINE
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
DJFINE/DJFINE is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import random

# Základní nastavení hry
planets = ["Mars", "Venus", "Jupiter", "Saturn", "Neptune"]
artifacts = ["Golden Guitar", "Silver Saxophone", "Platinum Piano", "Emerald Violin", "Crystal Drum"]
found_artifacts = []

# Funkce pro přivítání hráče
def welcome():
    print("Vítej ve hře Vesmírná Hudba!")
    print("Tvým úkolem je cestovat po planetách a najít všechny hudební artefakty.")
    print("Šťastnou cestu!\n")

# Funkce pro výběr planety
def choose_planet():
    print("Kam chceš cestovat?")
    for i, planet in enumerate(planets):
        print(f"{i + 1}. {planet}")
    choice = int(input("Vyber číslo planety: ")) - 1
    return planets[choice]

# Funkce pro prozkoumání planety
def explore_planet(planet):
    print(f"Prozkoumáváš planetu {planet}...")
    if random.random() > 0.5:  # 50% šance na nalezení artefaktu
        artifact = random.choice(artifacts)
        if artifact not in found_artifacts:
            found_artifacts.append(artifact)
            print(f"Našel jsi {artifact}!")
        else:
            print("Bohužel jsi zde již všechno našel.")
    else:
        print("Nenašel jsi žádný artefakt.")
    print()

# Funkce pro kontrolu, zda hráč vyhrál
def check_win():
    if len(found_artifacts) == len(artifacts):
        print("Gratulujeme! Našel jsi všechny hudební artefakty a vyhrál jsi hru!")
        return True
    return False

# Hlavní funkce hry
def main():
    welcome()
    while True:
        planet = choose_planet()
        explore_planet(planet)
        if check_win():
            break

if __name__ == "__main__":
    main()
