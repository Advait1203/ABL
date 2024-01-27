class Athlete:
    def __init__(self, name):
        self.name = name
        self.heart_rate = 0
        self.distance = 0
        self.running_speed = 0
        self.strength = 0
        self.flexibility = 0

    def update_data(self, heart_rate, distance, running_speed, strength, flexibility):
        self.heart_rate = heart_rate
        self.distance = distance
        self.running_speed = running_speed
        self.strength = strength
        self.flexibility = flexibility

    def make_decision(self):
        if 60 <= self.heart_rate <= 100:
            prediction = "\nOptimal heart rate. Keep it up!"
        elif 100 < self.heart_rate <= 120:
            prediction = "\nElevated heart rate. Ensure proper recovery."
        elif self.heart_rate > 120:
            prediction = "\nHigh heart rate. Consider reducing intensity."
        else:
            prediction = "\nLow heart rate. Push yourself a bit more."

        # Additional performance predictions based on running speed, strength, and flexibility
        if self.running_speed >= 10:
            prediction += "\nGreat running speed! Focus on endurance."
        if self.strength >= 80:
            prediction += "\nImpressive strength! Maintain a balanced workout routine."
        if self.flexibility >= 60:
            prediction += "\nGood flexibility! Incorporate stretching for better performance."

        return prediction

    def display_info(self):
        print(f"Hello, {self.name}!")
        print(f"Heart Rate: {self.heart_rate}")
        print(f"Distance: {self.distance} km")
        print(f"Running Speed: {self.running_speed} km/h")
        print(f"Strength: {self.strength}%")
        print(f"Flexibility: {self.flexibility}%")
        print(f"Performance Prediction: {self.make_decision()}")


def main():
    athlete_name = input("Enter Athlete's Name: ")
    athlete = Athlete(name=athlete_name)

    heart_rate = float(input("Enter Heart Rate: "))
    distance = float(input("Enter Distance (km): "))
    running_speed = float(input("Enter Running Speed (km/h): "))
    strength = float(input("Enter Strength (0-100): "))
    flexibility = float(input("Enter Flexibility (0-100): "))

    athlete.update_data(heart_rate, distance, running_speed, strength, flexibility)
    athlete.display_info()


if __name__ == '__main__':
    main()
