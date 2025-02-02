# Google Sheets Auto Timestamp & Expiry Checker

This Google Apps Script automates the process of adding timestamps and checking for expiry in Google Sheets. It dynamically tracks user input and updates specific columns based on defined conditions.

## 🚀 Features
- ✅ **Auto Timestamp:** When a user types `"success"` in column **A**, a timestamp (current time + 15 minutes) is added to column **B** in the same row.
- ✅ **Auto Expiry Check:** Every minute, the script checks if the timestamp in column **B** has expired. If expired, column **C** is updated with `"extended"`.
- ✅ **Automatic Trigger Setup:** Runs automatically every minute after initial setup.

## 🔧 How It Works
1. **User Input:** When `"success"` is entered in **column A**, the script adds a timestamp in **column B**.
2. **Time-Based Trigger:** The script runs every minute to check if the timestamp in **column B** has passed.
3. **Update Status:** If the timestamp is expired, `"extended"` is added to **column C**.

## 📌 Installation & Setup
1. Open **Google Sheets** and go to `Extensions` → `Apps Script`.
2. Copy and paste the script into the editor.
3. Click **Save** and then manually run `createTrigger()` **once** to activate automatic time-based execution.

## 📝 Code Explanation
### 1️⃣ `onEdit(e)` – Detects User Input in Column A
- Listens for changes in column A.
- If the value is `"success"`, it calculates **current time + 15 minutes** and stores it in column B.

### 2️⃣ `checkTime()` – Checks Expiry Every Minute
- Iterates through column B to see if any timestamp has expired.
- If expired, updates column C with `"extended"`.

### 3️⃣ `createTrigger()` – Sets Up Auto Execution
- Creates a trigger to run `checkTime()` every 1 minute.
- Ensures only one trigger is active to avoid duplication.

## 📊 Usage Example

| A (User Input) | B (Timestamp +15 min) | C (Status) |
|---------------|---------------------|----------|
| success       | 12:30 PM            |          |
|               | 12:15 PM            | extended |

---

### 🔗 License & Contributions
Feel free to use, modify, and contribute! 🚀
