# Breadtime Scheduler (Kenyéridő)

Google Sheets + Apps Script tool to plan and track baking (or other timed workflows).  
It calculates task times based on delays, manual overrides, and shows all recipes together in a color-coded summary.

---

## ✨ Features
- Define tasks per recipe with a delay in minutes.
- Add manual start/override times at any point.
- Automatic recalculation of all following tasks.
- Color-coded summary view with tasks sorted by time.
- Localized to Hungarian (but easy to adapt).

---

## 📊 Example

### Input (per recipe sheet)
| Fázis       | Késleltetés (min) | Időpont Megadás / Felülírás | Számolt Időpont |
|-------------|-------------------|-----------------------------|-----------------|
| Dagasztás   | 60                | 15:15                       | 15:15           |
| Laminálás   | 30                |                             | 15:45           |
| Hajtogatás  | 45                |                             | 16:30           |

### Output (Summary sheet)
| Recept | Fázis      | Számolt Időpont | Recept |
|--------|------------|-----------------|--------|
| Kenyér | Dagasztás  | 15:15           | Kenyér |
| Pizza  | Hajtogatás | 16:00           | Pizza  |

---

## 🚀 Installation
1. Create a Google Spreadsheet.
2. Open **Extensions → Apps Script**.
3. Copy code from [`src/Breadtime.gs`](src/Breadtime.gs).
4. Run `setUpTrigger()` once to register the `onEdit` trigger.
5. Create recipe sheets (e.g. `Pizza`, `Kenyér`) and a `Summary` sheet.
6. Use the headers:
   - **Fázis**
   - **Késleltetés (min)**
   - **Időpont Megadás / Felülírás**
   - **Számolt Időpont**

---

## 🧑‍💻 Development
- The main logic is in `onEdit`.
- Summary is recalculated on every edit.
- Colors for recipes are defined in `RECIPE_COLORS`.

---

## 📜 License
[MIT](LICENSE) – free to use, modify, share.
