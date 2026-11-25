# 🗓️ Habit Tracker (CLI)

A simple, beginner-friendly command-line habit tracker written in Python. Add habits, mark them done each day, and keep an eye on your current and longest streaks, all from your terminal.

## ✨ Features

- **Add habits** with duplicate detection (case-insensitive) and empty-name validation
- **View all habits** with today's status and total days completed
- **Mark a habit as done today** (prevents marking the same habit twice in one day)
- **Track streaks**: see both your *current streak* and *longest streak* per habit
- **Delete habits** you no longer want to track
- Input validation for invalid menu choices and non-numeric input

## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher (uses `date.fromisoformat`)
- No external libraries needed, only the Python standard library

### Installation

```bash
git clone https://github.com/Th3rdeye-ui/Habit_tracker.git
cd Habit_tracker
```

### Run

```bash
python Habit_tracker.ipynb
```

> Replace `Habit_tracker.ipynb` with whatever your file is named.

## 📖 Usage

When you start the app, you'll see this menu:

```
==== MENU ====
1. Add Habit
2. View Habits
3. Mark Habit as Done Today
4. View Streaks
5. Delete Habit
6. Exit
```

Type the number of your choice and press Enter.

### Example session

```
Welcome to Habit Tracker App

==== MENU ====
Please Enter Your Choice: 1
Enter habit name (e.g. Exercise, Read, Meditate): Exercise

Habit added successfully

Please Enter Your Choice: 3
1. Exercise
Enter habit number to mark as done: 1

Great job! 'Exercise' marked as done for today.

Please Enter Your Choice: 4

==== Streaks ====
Exercise -> Current streak: 1, Longest streak: 1
```

## 🔥 How Streaks Work

- **Current streak**: the number of consecutive days, counting back from today, on which the habit was done. If you haven't done it yet today, the count starts from yesterday, so your streak isn't broken until the day actually ends.
- **Longest streak**: the longest run of consecutive days across the habit's entire history.

## 🧠 How It Works

Each habit is stored as a dictionary inside a list:

```python
{
    "name": "Exercise",
    "dates": ["2026-11-23", "2026-11-24", "2026-11-25"]  # YYYY-MM-DD
}
```

Dates are stored in ISO format, which makes them easy to sort and compare, and ready to be saved as JSON later.

## ⚠️ Known Limitations

- **No data persistence**: habits are stored in memory only, so everything is lost when you exit the program. Streaks can only build up while the app stays running.

## 🛣️ Roadmap

- [ ] Save and load habits from a JSON file so data persists between runs
- [ ] Refactor menu actions into separate functions
- [ ] Add an option to un-mark a habit for today
- [ ] Add reminders or a weekly summary view
- [ ] Add unit tests for the streak logic

## 🤝 Contributing

Suggestions and pull requests are welcome. Feel free to fork the repo and open a PR.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
