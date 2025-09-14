# 🍅 Pomodoro Timer (Day 28 of Python Bootcamp)

Hello Community! 👋
This is my **28th day of the Python Bootcamp**, and today I built a
**Pomodoro Timer App** ⏰ using **Python's Tkinter GUI library**.

The **Pomodoro Technique** is a time management method that breaks work
into intervals (usually 25 minutes), separated by short breaks. After
several cycles, you take a longer break. This app helps you stay
productive and focused! 💪

------------------------------------------------------------------------

## 📝 Features

-   ✅ **Work sessions** of 25 minutes.
-   ✅ **Short breaks** of 5 minutes after every work session.
-   ✅ **Long break** of 20 minutes after 4 work sessions.
-   ✅ **Start** and **Reset** buttons for control.
-   ✅ A ✅ checkmark appears for every completed work session.
-   ✅ Beautiful **Tomato Theme** 🍅 (using `tomato.png`).

------------------------------------------------------------------------

## ⚙️ How the Code Works

### 1. 🎨 Constants

``` python
PINK = "#e2979c"
RED = "#e7305b"
GREEN = "#9bdeac"
YELLOW = "#f7f5dd"
FONT_NAME = "Courier"
WORK_MIN = 25
SHORT_BREAK_MIN = 5
LONG_BREAK_MIN = 20
```

-   Defined colors 🎨 and font styles for UI.
-   Set Pomodoro intervals: **25 min work**, **5 min short break**, **20
    min long break**.

------------------------------------------------------------------------

### 2. 🔄 Reset Timer

``` python
def reset_timer():
    window.after_cancel(timer)
    canvas.itemconfig(timer_text, text="00:00")
    timer_label.config(text="Timer")
    check_label.config(text="")
    global reps
    reps = 0
```

-   Stops the timer ⛔
-   Resets label, time, and checkmarks ✔

------------------------------------------------------------------------

### 3. ▶️ Start Timer

``` python
def start_timer():
    global reps
    ...
```

-   Increments `reps` (to track sessions).
-   Alternates between **Work → Short Break → Long Break** based on
    session number.

------------------------------------------------------------------------

### 4. ⏳ Countdown Mechanism

``` python
def count_down(count):
    ...
    if count > 0:
        timer = window.after(1000, count_down, count-1)
    else:
        start_timer()
        ...
```

-   Updates the timer text ⏱
-   Recursively calls itself every second using `after()`
-   When the timer hits **0**, it automatically starts the next session.

------------------------------------------------------------------------

### 5. 🖥 UI Setup

-   **Window** with yellow background 🌻
-   **Canvas** showing a tomato image 🍅
-   **Timer Label**, **Start Button**, **Reset Button**
-   **Check Label** for progress tracking ✔

------------------------------------------------------------------------
## 📚 What I Learned

-   Tkinter basics (`Label`, `Button`, `Canvas`).
-   Using `after()` for scheduling functions in Tkinter.
-   Managing **global variables** (`reps`, `timer`).
-   Implementing the **Pomodoro Technique** in code.

