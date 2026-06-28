# GroupDNA: WhatsApp Chat Analytics Engine

A behavioral analytics and text-mining engine that decodes raw plaintext WhatsApp chat exports to uncover friend group communication patterns, collective activity rhythms, and assign communication personality archetypes. Built completely from scratch using pure Python fundamentals and NumPy under a strict set of programmatic constraints.

---

## 📌 Project Overview
GroupDNA parses messy, real-world conversational data from a WhatsApp Android export (`hostel_bois.txt`). It implements custom algorithmic filters to handle structural edge cases—such as system notifications, media stubs, and deleted messages—without high-level data analysis libraries. By employing multi-dimensional time-series binning via a 6×24 NumPy matrix, the engine computes communication metrics including response latency, consecutive message bursts, and multi-day silent streaks to profile each participant.

---

## 🚫 Technical Constraints & Discipline
To demonstrate algorithmic discipline and mastery of core concepts, this project was built under a strict "no-shortcuts" constraint policy:
* **Allowed:** Pure Python loops, core string methods (`.split()`, `.strip()`, `.lower()`), foundational standard data structures (`list`, `dict`, `set`), text file I/O, the `datetime` module (restricted to `strptime` and `timedelta`), and `NumPy` matrices.
* **Strictly Forbidden:** `pandas` (no DataFrames or CSV parsers allowed for analysis), `matplotlib` / `seaborn` (all visualizations are generated using text-art block layouts), `collections.Counter` / `defaultdict`, and regular expressions (`re`).

---

## 🛠️ Features Implemented
1.  **The Chat Parser:** Robust line-by-line plaintext extraction separating timestamps, sender identities, and raw text payloads while resolving system notification flags, media stubs (`<Media omitted>`), and deleted lines.
2.  **Group Overview:** Executive summary detailing message volumes, participant counts, chronological date spans, and a sorted per-person distribution frequency table.
3.  **Temporal Peak Identification:** Algorithmic detection of the group's single most active date and peak message volume hour.
4.  **NumPy Activity Heatmap:** A 6×24 matrix mapped using printable text blocks (`.`, `░`, `▒`, `▓`, `█`) representing normalized hourly messaging density per user.
5.  **Lexical Tokenization (Top Words):** Strips punctuation, normalizes case, and filters custom stop-words to rank and display the top 10 most repeated group vocabularies with proportional horizontal bar charts.
6.  **Response Latency & Ghost Spotting:** Measures average response time gaps between consecutive speakers and tracks the longest multi-day stretch of silence for each member.
7.  **Exclusive Archetype Detection:** Implements a quantitative rule-based scoring system mapping individuals to distinct profiles: *THE SPAMMER*, *THE GROUP MOM*, *THE NIGHT OWL*, *THE STORYTELLER*, *THE DRAMA QUEEN*, or *THE GHOST*.

---

## 📅 7-Day Build Log
* **Day 1:** Set up file I/O pipelines and built the tokenizer to cleanly filter out messy edge cases.
* **Day 2:** Implemented headline data aggregation and computed the core per-person frequency tracking tables.
* **Day 3:** Built the word-token processing loop, integrated case-normalization, and designed the block-character bar graphs.
* **Day 4:** Initialized the 6x24 NumPy grid and built the normalization layer to map message indices to visual shading blocks.
* **Day 5:** Configured `datetime` delta parsing to track cross-message gaps and consecutive silent calendars.
* **Day 6:** Designed the priority-based archetype classification functions and handled tie-breaking logic.
* **Day 7:** Polished the alignment grid via f-string width padding and ran validation passes across edge-case files.

---

## 🚀 Execution Instructions
1. Clone this repository or download the `.ipynb` notebook.
2. Place your raw chat log named `hostel_bois.txt` in the same working directory (or upload it to your Google Colab session environment).
3. Execute the notebook cells sequentially from top to bottom.
