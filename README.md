# my_class

# Parent Class
class Smartphone:
    def __init__(self, brand, model, battery_life):
        self.brand = brand
        self.model = model
        self._battery_level = battery_life  # Encapsulated attribute

    def turn_on(self):
        if self._battery_level > 0:
            print(f"{self.brand} {self.model} is now ON.")
        else:
            print(f"{self.brand} {self.model} has no battery. Please charge it!")

    def turn_off(self):
        print(f"{self.brand} {self.model} is now OFF.")

    def charge_battery(self, amount):
        self._battery_level += amount
        print(f"{self.brand} {self.model} charged to {self._battery_level}%.")

# Child Class (Inheritance)
class GamingPhone(Smartphone):
    def __init__(self, brand, model, battery_life, gpu):
        super().__init__(brand, model, battery_life)
        self.gpu = gpu  # New attribute

    def enable_gaming_mode(self):
        print(f"Gaming mode enabled on {self.brand} {self.model} using {self.gpu} GPU!")

# Creating objects
phone1 = Smartphone("Apple", "iPhone 15", 80)
gaming_phone = GamingPhone("Asus", "ROG Phone 7", 90, "Adreno 740")

phone1.turn_on()
gaming_phone.turn_on()
gaming_phone.enable_gaming_mode()

#Activity 2 "Polymorphism"
# Parent Class
class Vehicle:
    def move(self):
        pass  # To be overridden by subclasses

# Car Class
class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

# Plane Class
class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

# Boat Class
class Boat(Vehicle):
    def move(self):
        print("Sailing 🚢")

vehicles = [Car(), Plane(), Boat()]

for vehicle in vehicles:
    vehicle.move()  # Each class has a different move() implementation


