# py4oop

Code for Part 1 (Design Your Own Class! 🏗️):
# Base class representing a Smartphone
class Smartphone:
    def __init__(self, brand, model, battery_life):
        self.brand = brand
        self.model = model
        self.battery_life = battery_life
        self.is_on = False
    
    def power_on(self):
        self.is_on = True
        print(f"{self.brand} {self.model} is now ON.")
    
    def power_off(self):
        self.is_on = False
        print(f"{self.brand} {self.model} is now OFF.")
    
    def check_battery(self):
        print(f"Battery life remaining: {self.battery_life}%")
    
    def display_info(self):
        print(f"Smartphone Details: Brand: {self.brand}, Model: {self.model}, Battery Life: {self.battery_life}%")


# Inheriting from Smartphone, a specialized Gaming Smartphone class
class GamingSmartphone(Smartphone):
    def __init__(self, brand, model, battery_life, gaming_mode=True):
        super().__init__(brand, model, battery_life)
        self.gaming_mode = gaming_mode
    
    # Overriding the display_info method
    def display_info(self):
        super().display_info()
        if self.gaming_mode:
            print("This phone supports gaming mode!")
        else:
            print("This phone does not have gaming mode.")
    
    def activate_gaming_mode(self):
        self.gaming_mode = True
        print("Gaming mode activated!")
    
    def deactivate_gaming_mode(self):
        self.gaming_mode = False
        print("Gaming mode deactivated.")


# Creating objects and testing the classes
smartphone1 = Smartphone("Apple", "iPhone 15", 90)
smartphone1.display_info()
smartphone1.power_on()
smartphone1.check_battery()

gaming_smartphone = GamingSmartphone("Asus", "ROG Phone 6", 80)
gaming_smartphone.display_info()
gaming_smartphone.activate_gaming_mode()
gaming_smartphone.power_on()
gaming_smartphone.check_battery()



Explanation of Part 1:
Smartphone Class:

Attributes: brand, model, battery_life, is_on.
Methods:
power_on(): Turns the smartphone on.
power_off(): Turns the smartphone off.
check_battery(): Displays the current battery percentage.
display_info(): Displays basic info about the phone.
GamingSmartphone Class (Inherits from Smartphone):

Adds the attribute gaming_mode to toggle gaming mode.
Methods:
display_info(): Overrides the base class's method to include whether the phone supports gaming mode.
activate_gaming_mode() & deactivate_gaming_mode(): Toggles gaming mode on/off.
Code for Part 2 (Polymorphism Challenge! 🎭):
# Base class Animal
class Animal:
    def move(self):
        pass  # Placeholder method for moving, will be overridden in subclasses

# Dog class
class Dog(Animal):
    def move(self):
        print("The dog is running on the ground 🐕‍🦺")

# Bird class
class Bird(Animal):
    def move(self):
        print("The bird is flying in the sky 🦅")

# Fish class
class Fish(Animal):
    def move(self):
        print("The fish is swimming in the water 🐟")

# Creating objects and demonstrating polymorphism
def demonstrate_movement(animal):
    animal.move()

# Instantiate the animals
dog = Dog()
bird = Bird()
fish = Fish()

# Demonstrate polymorphism
demonstrate_movement(dog)   # Output: The dog is running on the ground
demonstrate_movement(bird)  # Output: The bird is flying in the sky
demonstrate_movement(fish)  # Output: The fish is swimming in the water
Explanation of Part 2:
Animal Class:

A base class with a move() method that will be overridden by subclasses.
Dog, Bird, Fish Classes:

These are subclasses of Animal, each implementing the move() method in its own way.
Dog: The dog moves by running.
Bird: The bird moves by flying.
Fish: The fish moves by swimming.
Polymorphism:

We have a function demonstrate_movement() that accepts any Animal and calls its move() method. Depending on the type of the object (whether it is a Dog, Bird, or Fish), the appropriate move() method is called. This is polymorphism, where the same method (move()) behaves differently depending on the object.
Sample Output for Both Parts:
Output for Part 1 (Smartphone Example):

Smartphone Details: Brand: Apple, Model: iPhone 15, Battery Life: 90%
Apple iPhone 15 is now ON.
Battery life remaining: 90%
Smartphone Details: Brand: Asus, Model: ROG Phone 6, Battery Life: 80%
This phone supports gaming mode!
Asus ROG Phone 6 is now ON.
Battery life remaining: 80%
Output for Part 2 (Polymorphism Example):

The dog is running on the ground 🐕‍🦺
The bird is flying in the sky 🦅
The fish is swimming in the water 🐟
