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
].

def add_hotel(hotels):
    hotelNum = int(input("Hotel Number: "))
    name = input("Hotel Name: ")
    city = input("Hotel City: ")
    room = []
    numRoom = int(input("how many rooms? : "))
    for i in range(numRoom):
        print(f"for room {i+1}")
        roomNum = int(input("Room Number: "))
        status = input("Room Status:available/occupied")
        while status not in ["available", "occupied"]:
            status = input("please enter 'available' or 'occupied'")
        roomType = input("Room Type: single/double ")
        while roomType not in ["single", "double"]:
            roomType = input("please enter 'single' or 'double'")
        room.append(( roomNum, status, roomType))
    newHotel = (hotelNum, name, city , room)
    hotels.append(newHotel)
    print("Hotel added successfully")

def add_room_type(hotels):
    hotelNum = int(input("Hotel Number: "))
    for hotel in hotels:
        if hotels[hotel]==hotelNum:
            roomNum = int(input("Enter New Room Number: "))
            while roomNum in hotels[hotel]:
                roomNum = int(input("This room number already exists, please enter new Room Number: "))
            roomTyp = input("Room Type: single/double ")
            while roomTyp not in ["single", "double"]:
                roomTyp = input("please enter 'single' or 'double'")
            status = "available"
            room = (roomNum, roomTyp, status)
            hotels[hotel].append(room)
            print(f"Room {roomNum} added successfully")

def show_hotels(hotels):
    print(hotels)




