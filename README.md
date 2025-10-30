hotel = list(hotels[0])  # ממיר את ה-tuple לרשימה זמנית כדי שאפשר יהיה לערוך
rooms = hotel[3]  # זו רשימת החדרים

# מחפש את החדר שרוצים לשנות
for i, room in enumerate(rooms):
    if room[0] == 202:
        rooms[i] = (room[0], "Available", room[2])  # יוצר tuple חדש עם הערך המעודכן

hotel[3] = rooms
hotels[0] = tuple(hotel)

print(hotels)

hotels = [
    (
        101, "Hilton", "New York",
        [(201, "Available", "Single"), (202, "Occupied", "Double")],
        [("John Doe", "123456789", "2025-04-10")]
    ),
    (
        102, "Marriott", "Boston",
        [(301, "Available", "Single")],
        [("Jane Smith", "987654321", "2025-05-15"), ("Bob Lee", "555555555", "2025-06-01")]
    )
]
