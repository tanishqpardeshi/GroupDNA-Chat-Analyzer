# GroupDNA: WhatsApp Chat Analyzer 🧬

> A behavioral analytics tool that parses raw, unstructured WhatsApp chat exports into a beautifully formatted, terminal-based dashboard. 

**Author:** Tanishq Pardeshi  
**Domain:** Data Science / Core Python Engineering  

![GroupDNA Output Screenshot](https://1drv.ms/i/c/edbb5b3f016ec8dc/IQA7GddCONqfQ5-1DzQjbdkhAUiKbJq-4E8CSFQiukjClwg?e=c5u96i    )  
*(Terminal output analyzing 60 days of chat data)*

---

## 📖 Project Overview
GroupDNA processes messy, real-world text data to generate actionable insights about messaging habits, peak activity hours, and user vocabulary. The system automatically detects data edge-cases (omitted media, system messages, deleted texts) and uses a custom quantitative rules engine to assign exclusive behavioral "archetypes" to each group member.

When run on a 3,000+ message dataset, the engine successfully mapped unique archetypes, identifying the late-night coder, the group mom, the ghost, and the serial spammer.

## 🛠️ The Engineering Constraint (Why this matters)
This project was built to demonstrate rigorous proficiency in Python fundamentals and data structures. To prove data manipulation capabilities without relying on high-level abstractions, this project adheres to a strict "forbidden list":

* **❌ NO `pandas`:** File I/O and data structuring are handled via native Python lists, dictionaries, and hash maps, achieving $O(N)$ time complexity in a single parsing pass.
* **❌ NO `matplotlib` / `seaborn`:** All visualizations (including the activity heatmap and frequency bar charts) are mathematically normalized and rendered natively in the terminal using ASCII block characters.
* **❌ NO `re` (Regex):** String parsing and complex timestamp extraction rely entirely on heuristic string methods and exception handling.
* **❌ NO `collections.Counter`:** Frequency counting logic is built manually using native dictionary methods.

**Allowed Stack:** Native Python, `NumPy` (for the 2D activity matrix), `datetime`, and `string`.

## ✨ Core Features
1. **Robust Data Parser:** Cleans and structures raw WhatsApp `.txt` exports, safely appending fragmented multi-line texts.
2. **Activity Heatmap:** A 2D NumPy matrix `(Users x 24 Hours)` mapping participants to their daily activity cycles.
3. **Response & Streak Analytics:** Calculates average response latency and longest streaks of absolute consecutive silence.
4. **Vocabulary Extraction:** Identifies top group-specific words, filtering out common stop words and punctuation.
5. **Archetype Assignment Engine:** Assigns specific behavioral profiles based on dynamic mathematical thresholds. Includes a custom archetype, **🔗 The Linker**, which detects users who frequently share external URLs (like GitHub or LeetCode).

## 🚀 Run Instructions

### Prerequisites
Ensure you have Python 3.x and NumPy installed on your machine.
```bash
pip install numpy
