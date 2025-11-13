    
        pokemon_list = []
        battle_history = []

        while True:
            print("""
    ================= 🌟 POKEMON MENU 🌟 =================
    1️⃣  הוסף פוקימון חדש
    2️⃣  הצג את כל הפוקימונים
    3️⃣  עדכן רמות (Upgrade)
    4️⃣  סטטיסטיקות כלליות
    5️⃣  קרב בין פוקימונים
    6️⃣  הצג היסטוריית קרבות
    7️⃣  יציאה
    =======================================================
    """)

            choice = input("בחר אפשרות (1-7): ").strip()

            if choice == "1":
                name = input("שם הפוקימון: ")
                p_type = input("סוג הפוקימון: ")
                attack = int(input("ערך התקפה: "))
                defense = int(input("ערך הגנה: "))
                add_pokemon(pokemon_list, name, p_type, attack, defense)
                print(f"✅ {name} נוסף בהצלחה!\n")

            elif choice == "2":
                show_pokemons(pokemon_list)

            elif choice == "3":
                name = input("הכנס את שם הפוקימון לעדכון: ")
                if update_pokemon(pokemon_list, name):
                    print("✨ הפוקימון עודכן בהצלחה!")
                else:
                    print("❌ לא ניתן לעדכן את הפוקימון (אין נצחונות או לא נמצא).")

            elif choice == "4":
                if pokemon_list:
                    stats = show_statistics(pokemon_list)
                    print("\n📊 סטטיסטיקות:")
                    for key, value in stats.items():
                        print(f"{key}: {value}")
                else:
                    print("אין פוקימונים לחישוב סטטיסטיקות.")

            elif choice == "5":
                name1 = input("פוקימון ראשון: ")
                name2 = input("פוקימון שני: ")
                result = battle(pokemon_list, name1, name2)
                if result:
                    battle_history.append(result)

            elif choice == "6":
                show_battle_history(battle_history)

            elif choice == "7":
                print("👋 להתראות מאסטר פוקימון!")
                break

            else:
                print("❌ בחירה לא תקינה, נסה שוב.")

main()


