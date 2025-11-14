---
title: "Critique by Design – High Street Coffee Caffeine Levels"
layout: default
---

# Critique by Design: High Street Coffee Caffeine Levels

## 1. Original data visualization and context

For this critique-by-design assignment, I chose a visualization based on the **Which?** article:

> “Caffeine levels in high street coffees vary significantly, Which? finds”

The original chart compared the caffeine content of cappuccino, espresso and filter coffee across several UK high-street coffee chains (e.g. Costa, Pret, Starbucks). It was part of a public-facing article about how much caffeine customers actually get in a typical drink.

**Original source**

- Article: [Caffeine levels in high street coffees vary significantly, Which? finds](https://www.which.co.uk/news/article/caffeine-levels-in-high-street-coffees-vary-significantly-which-finds-ay7cA4G1zh1S)
- Challenge: [MakeoverMonday](https://www.makeovermonday.co.uk/)

I picked this visualization because:

- It addresses a **clear, relatable question**: *“How much caffeine am I really drinking?”*
- The stakes are non-trivial for people sensitive to caffeine (sleep, anxiety, pregnancy, health guidance).
- The original presentation made it hard to quickly see **distribution** and **risk thresholds**, especially which chains regularly exceed recommended daily limits.

---

## 2. What I found problematic in the original visualization

Using Stephen Few’s **Data Visualization Effectiveness Profile**, I critiqued the original visualization along multiple dimensions. Below is a summary of my key observations from the Google Form.

### 2.1 Purpose and message

- **Strengths**
  - Clear topical focus: high-street coffee caffeine levels.
  - Uses real-world brands that are instantly recognizable.
- **Issues**
  - The main message (“caffeine varies a lot and can be unexpectedly high”) gets diluted.
  - It is not immediately obvious **which drinks are “too high”** relative to a recommended threshold (e.g. 200 mg or 400 mg per day).
  - The visualization feels closer to “interesting table of numbers” than a **strong, memorable takeaway**.

### 2.2 Data and encoding

- **Data**
  - Each record includes: chain, drink type (espresso / cappuccino / filter), and caffeine in mg.
- **Encoding issues**
  - Multiple drink types and chains in one dense display creates **cognitive overload**.
  - It is difficult to compare distributions of caffeine levels **within** a chain and **across** chains at the same time.
  - The design does not highlight **frequency patterns** (e.g. how often drinks fall into “very high caffeine” bins).

### 2.3 Use of color, hierarchy and labeling

- **Positives**
  - Brand logos / names help people quickly locate their favorite chain.
- **Issues**
  - Color is used more for branding than for meaning, which competes with the data story.
  - There is limited visual hierarchy; all bars/values feel equally important.
  - Labels can feel cramped, and numeric values are not always easy to scan.

### 2.4 Audience and accessibility

- **Target audience**
  - General public, coffee drinkers, and potentially people monitoring caffeine intake.
- **Issues**
  - For a non-technical audience, the design asks for too much **mental arithmetic** (e.g. adding up drinks, comparing across chains).
  - The visualization doesn’t explicitly connect caffeine levels to **guidelines** (like 200 mg at a time or 400 mg per day), so it is hard to know what is “too much.”

### 2.5 Comparing critique methods: Few vs Good Charts

- Stephen Few’s **Effectiveness Profile** pushed me to systematically evaluate:
  - Purpose, message and audience.
  - Clarity of encodings and effectiveness of color.
  - Overall usability and decision support.
- The **Good Charts** method emphasizes:
  - Story framing and narrative arc.
  - The “so what?” and how to make charts more persuasive and memorable.

**What Few adds**

- A more **checklist-like, diagnostic view** of the chart’s mechanics.
- A structured way to note specific weaknesses (e.g. labeling, clutter, encoding choices).

**What might be missing**

- Fewer prompts about **emotional resonance** and storytelling.
- Less emphasis on how the visualization fits into a broader narrative or communication flow.

Together, the two methods helped me move from “this feels busy” to concrete design decisions for the redesign.

---

## 3. Step 3 – Sketching and wireframing the redesign

I created low-fidelity sketches before building anything in Tableau. My main design goal was to answer two user questions more directly:

1. **“Where does my favorite chain sit compared to others?”**
2. **“How often are drinks in a range that might be too high for me?”**

### 3.1 Key sketch ideas

1. **Frequency view (overall distribution)**
   - Group drinks into caffeine bins (e.g. 0–100 mg, 100–200 mg, 200–300 mg, 300+ mg).
   - Show a simple **frequency bar chart** counting how many drinks fall into each bin.
   - Highlight bins above a “concern” threshold (e.g. >200 mg).

2. **Conditional frequency by chain**
   - For each chain, show the **percentage of its drinks** that cross a threshold (for example, 200 mg).
   - This helps answer: *“If I pick this chain at random, how likely is it that my drink is very high in caffeine?”*

3. **Design simplifications**
   - Use **one main metric** (caffeine in mg) and **one secondary dimension** at a time.
   - Rely on a **small, consistent color palette** where color encodes meaning (e.g. “high caffeine”) instead of just brand identity.
   - Add a reference line or annotation for guidance like “up to 200 mg is a common single-serving recommendation.”

These sketches helped me see that focusing on **frequency** and **conditional frequency** could tell a clearer, more actionable story than simply plotting raw values by chain and drink type.

---

## 4. Step 4 – Testing the solution with peers

I shared my sketched ideas and early Tableau drafts with peers and captured anonymized feedback.

### 4.1 Participants

- Participant 1: student, mid-20s, data visualization course
- Participant 2: student, early 20s, no prior data viz background

### 4.2 Key questions I asked

- “Can you tell me what you think this chart is about?”
- “What do you find surprising or confusing?”
- “If you cared about your caffeine intake, what decision could you make from this?”
- “Is there anything you’d change or make clearer?”

### 4.3 What I heard

**What worked**

- The idea of **bins** for caffeine levels made the data feel more concrete:
  - Comments like: “I can see that a lot of drinks are above 200 mg” or “the 300+ mg bar looks scary.”
- The conditional frequency view by chain helped surface differences:
  - “So Costa has a much higher share of high-caffeine drinks than Starbucks.”

**What was confusing**

- The initial bin labels were not intuitive (“Bin 1, Bin 2…”).
- One participant did not immediately understand what the **threshold line** meant.
- The legend and annotation for “high caffeine” were separated from the chart, causing extra eye movement.

### 4.4 Changes I made based on feedback

- Renamed bins to more meaningful ranges such as:
  - “Up to 100 mg”, “100–200 mg”, “200–300 mg”, “300+ mg”
- Added a **clear textual annotation** explaining the threshold, for example:
  > “Bars in darker color show drinks above 200 mg of caffeine, which many guidelines consider a high single serving.”
- Moved the legend closer to the chart and tightened the label wording.
- Simplified tooltips to show just:
  - Chain
  - Drink type
  - Caffeine (mg)
  - Whether it crosses the threshold

---

## 5. Step 5 – Final redesigned visualizations (Tableau)

I built the final redesign in Tableau and published it to Tableau Public.

### 5.1 Visualization 1 – Frequency of caffeine levels

**Link:**  
[Frequency of caffeine levels – Tableau Public](https://public.tableau.com/app/profile/vishakha.pathak6304/viz/Book1_17630934455190/Sheet1?publish=yes)

**What it shows**

- A **frequency bar chart** of drinks grouped into caffeine ranges.
- The bins above 200 mg are visually emphasized.
- This view answers:
  - “How many drinks fall into low, medium, and high caffeine ranges?”

**Design choices**

- Single x-axis (caffeine bins) with clear text labels.
- Bars for higher caffeine bins styled consistently so they stand out.
- Simple annotation noting why 200 mg is a meaningful cutoff.

---

### 5.2 Visualization 2 – Conditional frequency by chain

**Link:**  
[Conditional frequency of high-caffeine drinks by chain – Tableau Public](https://public.tableau.com/app/profile/vishakha.pathak6304/viz/Book2_17630947533450/Sheet1?publish=yes)

**What it shows**

- For each chain, the **percentage of its drinks that exceed 200 mg** (or another chosen threshold).
- This reframes the question as:
  - “If I buy a coffee from this chain, how likely is it that my drink is very high in caffeine?”

**Design choices**

- Each bar represents one chain; the bar length encodes the **share of high-caffeine drinks**.
- Chains are sorted from highest to lowest share, so patterns appear quickly.
- Labels show percentages to keep interpretation simple (e.g. “60% of drinks above 200 mg”).

---

## 6. Summary, reflection and what changed

### 6.1 Why this visualization was included

I chose this visualization because:

- It speaks to a topic that many people care about but **often underestimate**: caffeine intake.
- The original chart was informative but did not strongly support **decision-making** about which chains or drinks might be safer choices for people with caffeine limits.
- The MakeoverMonday context encouraged me to think about both **clarity** and **storytelling**, not just replicating the original.

### 6.2 How the critique shaped the redesign

The **Data Visualization Effectiveness Profile** forced me to be specific about:

- Who the audience is (general consumers, not caffeine scientists).
- What decision I want to help them with (choosing chains/drinks with manageable caffeine).
- Which encodings were confusing in the original.

This directly led to:

- Focusing on **frequency** and **conditional frequency**, which better aligns with risk and likelihood.
- Simplifying the number of variables shown at once.
- Using color to flag **risk levels** instead of reinforcing brand identity.

The **Good Charts** lens reminded me to keep asking:

- “What is the **headline** of this chart?”
- “What is the one thing I want someone to remember after looking at it?”

### 6.3 What my redesigned visualization shows

The final redesign emphasizes:

- There is a **wide spread** of caffeine levels in seemingly similar drinks.
- Some chains have a **much higher share** of high-caffeine drinks than others.
- For a consumer, this means that where they buy their coffee can significantly change their caffeine exposure, even for the same type of drink.

Overall, my goal was not just to make the visualization “prettier,” but to make it **more actionable** and aligned with how a reader might think:

> “If I am monitoring my caffeine, which chains and types of drinks should I be more careful with?”

---

## 7. Sources and tools

- Original article and visualization: “Caffeine levels in high street coffees vary significantly, Which? finds” (Which?, 2023).
- Dataset and inspiration: [MakeoverMonday](https://www.makeovermonday.co.uk/).
- Tools:
  - Tableau Public for data exploration and final charts.
  - Pen-and-paper sketches for initial wireframes.

---

## 8. AI usage

I used AI (ChatGPT) to help:

- Draft and organize the written narrative for this portfolio page.
- Refine wording for the critique, user feedback summary and reflections.

All data selection, Tableau work, visual design decisions and final design choices are my own.
