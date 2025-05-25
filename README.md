# courseapp
# 📘 CourseApp – Dive Log & Statistics

A responsive Flutter web / mobile application for recreational divers to keep
track of their dives, tanks, and key gas-use metrics.

* **Log dives** with date, tank, duration, depth and pressures  
* **Automatic statistics** – total dives, average duration, SAC/RMV, deepest dive  
* **Tank manager** – add or retire tanks; prevents deletion when a tank is still referenced  
* **Edit / delete with swipe gestures**  
* **Light / dark theme** toggle, remembered across sessions  
* **Adaptive layout**  
  * Mobile: tabbed navigation, 2-column stat grid  
  * Wide / desktop: split-pane dashboard and list  
  * Max-width clamp (1200 px) so the UI never stretches too far

---

## 🌐 Live demo

👉 **<https://teppis88.github.io/divingApp/>**  

---

## 🕹 How to use

| Task | Mobile gesture / click | Wide / desktop |
|------|------------------------|----------------|
| **Add a dive** | Tap **Dives → ➕** | Same, form appears in right pane |
| **Delete a dive** | Swipe **left** on the card → *Delete* | Same |
| **Edit a dive** | Swipe **right** on the card → *Edit* | Same |
| **Toggle dark mode** | Moon / sun icon in the AppBar | Same |
| **Manage tanks** | *Settings → Tanks* – add or delete (delete disabled if tank is in use) | Same |
| **Resize / rotate** | Layout switches automatically | Layout adapts – stats sidebar collapses |

---

## 🗄 Persistent storage

* Uses **Hive** boxes named `dives` and `tanks`, stored in the browser’s IndexedDB (web) or the app’s document directory (mobile/desktop).  
* On first launch the app seeds those boxes with sample data from `/lib/data/mockdata.dart` so you can explore immediately.  
* All add/edit/delete actions go through `DataService`, which keeps Hive storage and the in-memory `RxList`s in sync.

## 🧩 Key packages

| Package               | Purpose                                   |
|-----------------------|-------------------------------------------|
| `get`                 | Lightweight state-management, DI, routing |
| `hive_flutter`        | Local NoSQL persistence (IndexedDB / file)|
| `flutter_form_builder`| Declarative form widgets + validation     |
| `intl`                | Date & number formatting                  |
| `path_provider`       | Locate platform-specific storage dirs     |
---

## 📝 License

MIT License

Copyright (c) 2025 Teemu Kaikkonen