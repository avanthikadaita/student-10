---
toc: false
comments: false
layout: post
title: Fitness Planner
description: A plannr that tracks your fitness progress
type: ccc
courses: { csp: {week: 20} }
---

class FitnessPlanner:
    def __init__(self):
        self.user_data = {}

    def add_user(self, username):
        self.user_data[username] = {'workouts': [], 'goals': {}}

    def add_workout(self, username, workout_name, duration, date):
        workout = {'name': workout_name, 'duration': duration, 'date': date}
        self.user_data[username]['workouts'].append(workout)

    def set_goal(self, username, goal_type, goal_value):
        self.user_data[username]['goals'][goal_type] = goal_value

    def display_user_data(self, username):
        user_info = self.user_data.get(username)
        if user_info:
            print(f"Fitness Planner for {username}")
            print("Workouts:")
            for workout in user_info['workouts']:
                print(f"- {workout['name']}, {workout['duration']} minutes, {workout['date']}")
            
            print("\nGoals:")
            for goal_type, goal_value in user_info['goals'].items():
                print(f"- {goal_type}: {goal_value}")
        else:
            print(f"User {username} not found.")

# Example usage:
fitness_planner = FitnessPlanner()

# Add user
fitness_planner.add_user("JohnDoe")

# Add workouts
fitness_planner.add_workout("JohnDoe", "Cardio", 30, "2024-02-05")
fitness_planner.add_workout("JohnDoe", "Strength Training", 45, "2024-02-06")

# Set goals
fitness_planner.set_goal("JohnDoe", "Weight Loss", "Lose 5 lbs")
fitness_planner.set_goal("JohnDoe", "Run Distance", "10 miles per week")

# Display user data
fitness_planner.display_user_data("JohnDoe")





# Virtual Fitness Planner

## Page 1: Welcome
Welcome to your Virtual Fitness Planner! Click the "Next" button to begin your fitness journey.

[Next](#page-2)

---

## Page 2: User Creation
To get started, enter your username in the text box below and click "Create User."

[Username Input]

[Create User](#page-3)

---

## Page 3: Record Workouts
Great! Now you can record your workouts. Enter the workout details in the text box below and click "Add Workout."

[Workout Input]

[Add Workout](#page-4)

---

## Page 4: Set Goals
Awesome workouts! Let's set some fitness goals. Enter your goal details below and click "Set Goal."

[Goal Input]

[Set Goal](#page-5)

---

## Page 5: View Progress
Fantastic! You can now view your progress. Click "Next" to flip through your fitness journey.

[Next](#page-6)

---

## Page 6: Fitness Data
Here's a summary of your fitness journey:

Username: [Your Username]

### Workouts:
- Cardio, 30 minutes, 2024-02-05
- Strength Training, 45 minutes, 2024-02-06

### Goals:
- Weight Loss: Lose 5 lbs
- Run Distance: 10 miles per week

[Next](#page-7)

---

## Page 7: Record Progress
Keep it up! Click on this page to record your latest progress.

[Progress Input]

[Record Progress](#page-8)

---

## Page 8: Conclusion
Congratulations on your fitness journey! You've reached the end of your virtual planner.

[The End]
