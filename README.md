# MAST-Part-3

# 🍽️ Chef’s Menu Manager  
**Portfolio of Evidence – Part 3: Polishing and Final Features**  
**Student:** Bayanda Moabelo  
**Module:** Application Development using TypeScript  
**Marks:** 100  

---

## 📘 Overview
Chef’s Menu Manager is a React and TypeScript application that allows chefs to efficiently manage restaurant menu items and allows guests to view, filter, and explore the menu. The app supports multiple screens for better code organization and separation of user roles.

---

## 🧠 Learning Outcomes Demonstrated
- Use of `for`, `while`, and `for...in` loops in TypeScript  
- Creation and use of functions for modular code organization  
- Implementation of global variables to share data between components  
- Managing arrays for storing and displaying menu items  
- Creating multiple screens and navigation using React Navigation  
- Applying refactoring principles for cleaner, modular TypeScript code  

---

## 🧩 Features Implemented (Final PoE)

### 1. Home Screen (Guest View)
- Displays **all menu items** from the shared array.  
- Shows **average price per course** (e.g., Starters, Main, Dessert).  
- Uses a `for...in` loop and a function to calculate averages dynamically.  
- Data updates in real-time when items are added or removed from the global list.

### 2. Add Menu Screen (Chef View)
- A new **AddMenuScreen.tsx** was created.  
- Chefs can **add new menu items** (name, description, course, price).  
- Chefs can **remove existing menu items** from the shared array.  
- Uses a `for` loop for input validation and a function to handle menu updates.  
- The added items are stored in a global array that updates the Home screen automatically.

### 3. Filter Screen (Guest Filter View)
- Guests can filter menu items by **course type** (e.g., Starters, Mains, Desserts).  
- Implements a `while` loop to loop through items and display only matching courses.  
- Uses dropdown or button selection to trigger filtering.  
- Shows only the selected course menu items on screen.

---

## ⚙️ Technical Implementation

- **Tech Stack:** React Native + TypeScript  
- **Navigation:** React Navigation (Stack Navigator)  
- **Data Storage:** In-memory global array  
- **Reusable Functions:**  
  - `calculateAveragePrice()` – Computes average price per course  
  - `addMenuItem()` – Adds new items to the global array  
  - `removeMenuItem()` – Removes items by ID  
  - `filterByCourse()` – Returns filtered menu list  

---

## 🧱 Code Refactoring Improvements

| Refactoring Step | Description |
|------------------|-------------|
| **Modularization** | Split app into multiple files: `HomeScreen.tsx`, `AddMenuScreen.tsx`, `FilterScreen.tsx`, and `App.tsx` for navigation. |
| **Global Data Handling** | Introduced a global `menuItems` array to share data between screens. |
| **Reusable Functions** | Moved repetitive logic (adding, removing, filtering, average calculation) into separate functions. |
| **Code Readability** | Added descriptive comments and TypeScript interfaces. |
| **Loop Usage** | Replaced repetitive array iteration code with `for`, `while`, and `for...in` loops. |
| **Improved UI Flow** | Separated chef and guest functionality for better user experience. |

---

## 🧾 Change Log

### 🟢 Changes from **Part 2 → Part 3**

| No | Change Description | Reason / Outcome |
|----|--------------------|------------------|
| 1 | Moved “Add Menu Item” form from HomeScreen to a new **AddMenuScreen.tsx** | Improves separation of chef and guest functionality |
| 2 | Implemented **average price display by course** on the Home screen | Required feature for Part 3 |
| 3 | Added **FilterScreen.tsx** where guests can filter by course | Allows guests to view only specific menu sections |
| 4 | Created **global array `menuItems`** to share data between screens | Ensures real-time updates across screens |
| 5 | Added **for, while, and for...in** loops | Meets assessment criteria for loop usage |
| 6 | Refactored repeated code into helper functions | Improves reusability and readability |
| 7 | Updated **README.md** to include final changelog | Required for submission |
| 8 | Improved variable names and TypeScript typings | Enhances maintainability |
| 9 | Added UI elements for average price display | Improves visual feedback for users |
| 10 | Recorded demo video showing app features | Required for final PoE submission |

---

## 🧮 Example of Loops in Code

```typescript
function calculateAveragePrice(menuItems: MenuItem[]) {
  let courseTotals: { [key: string]: number } = {};
  let courseCounts: { [key: string]: number } = {};

  for (let item of menuItems) {
    if (!courseTotals[item.course]) {
      courseTotals[item.course] = 0;
      courseCounts[item.course] = 0;
    }
    courseTotals[item.course] += item.price;
    courseCounts[item.course]++;
  }

  let averages: { [key: string]: number } = {};
  for (let course in courseTotals) {
    averages[course] = courseTotals[course] / courseCounts[course];
  }

  return averages;
}
```

---

## 🎥 Demo Video
A screen recording with voice-over showcasing all app features has been provided.

**Video Link:** 
**GitHub Repository:** https://github.com/Bayanda-Moabelo/MAST-Part-3/edit/main/README.md

---

## 📚 References (Harvard Style)

- Mozilla Developer Network (MDN). (2024). *Loops and iteration*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration  
- TypeScript Documentation. (2024). *Functions*. Available at: https://www.typescriptlang.org/docs/handbook/functions.html  
- React Native Documentation. (2024). *React Navigation Guide*. Available at: https://reactnavigation.org/docs/getting-started/  
- W3Schools. (2024). *TypeScript Loops*. Available at: https://www.w3schools.com/typescript/typescript_loops.php  
