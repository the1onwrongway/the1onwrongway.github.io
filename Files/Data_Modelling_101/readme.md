# Data Modeling 101 Series

A technical education series on dimensional data warehouse design and analytics engineering fundamentals.

Delivered as live sessions with Indian Data Club (IDC). Every session is built on **Ralph Kimball's dimensional modeling framework**—the most battle-tested approach to building analytics systems that work.

---

## Why This Series Exists

Most data warehouse projects fail not because of tools, but because of **bad modeling decisions made early**.

Common failures:
- Unclear grain → metrics don't add up
- Mixed grains in same table → double-counting
- Dimensions with facts in them → bloat and instability
- No declarative process → every model is chaos

This series teaches **the method that prevents these failures**: Kimball's four-step dimensional design process.

The content is:
- **Practical**: Every concept is grounded in real retail sales example
- **Battle-tested**: Based on decades of proven patterns
- **Actionable**: Code-ready. Not theory.
- **Opinionated**: Clear guidance on when to follow rules and when to break them

---

## Session Index

### Session 1: Four-Step Dimensional Design Process
**File:** [📊 Four-Step Dimensional Design Process_Data_Modelling_101](./Four-Step%20Dimensional%20Design%20Process_Data_Modelling_101.pdf)

**Duration:** 45 minutes

**Topics Covered:**
- Why OLTP schemas fail for analytics
- Introduction to Kimball dimensional modeling
- Step 1: Business process selection
- Step 2: Grain declaration (most critical)
- Step 3: Dimension identification
- Step 4: Fact identification
- Complete star schema walkthrough
- Four common modeling mistakes
- Live exercise: schema design

**Learning Outcomes:**
- Write explicit grain statements
- Identify dimensions and facts from business process
- Understand why grain is the foundational decision
- Recognize modeling anti-patterns
- Build transaction-grain fact tables

**Prerequisite Knowledge:**
- Comfortable with SQL
- Understand basic database concepts
- Have written/maintained dashboards or reports

**Use Case:** Retail sales analytics (500 stores, 50K products, incremental weekly transactions)

---

## How to Use These Materials

### If You're Presenting
1. Download the .pptx file
2. Read the speaker notes (provided in separate document)
3. Understand the retail example deeply (you'll be explaining it)
4. Practice pause points for audience interaction
5. Have SQL queries ready to execute live (optional but powerful)
6. Adjust examples to your domain if needed (but keep grain story intact)

### If You're Learning
1. Watch the live session (context and explanation matter)
2. Study the slides after (reference the speaker notes)
3. Build a model in your own domain using the four-step process
4. Test with real queries (does it answer business questions?)
5. Share your design with peers for critique

### If You're Reusing
- Credit Milan Macwan and Ralph Kimball (original framework)
- Keep the retail example or substitute with your own (maintain consistency)
- Don't strip away the reasoning (it's not just definitions)
- Add your own battle scars (real mistakes you've made)

---

## Core Principles

### 1. Grain is Everything
Every dimensional model starts with a crystal-clear grain statement. If you can't state it in one sentence, your model isn't defined.

**Example:** "One row per product sold in one transaction at one store"

Grain determines:
- What dimensions you can add
- What facts are valid
- What business questions you can answer
- Whether metrics will be correct

### 2. Process Over Perfection
Follow the four steps. In order. No shortcuts.

1. **Select the business process** (not the department, not the system)
2. **Declare the grain** (explicit, measurable, agreed upon)
3. **Identify the dimensions** (fall out naturally from grain)
4. **Identify the facts** (numeric, additive, grain-matched)

### 3. Denormalization for Analytics
OLTP is normalized (3NF). OLAP is denormalized (star schema).

- Normalized = fast writes, slow reads
- Denormalized = slow writes, fast reads, business clarity

For analytics, denormalization wins.

### 4. One Grain Per Fact Table
Never mix transaction grain and daily aggregate grain in the same table. Separate fact tables.

Mixed grain = broken metrics. Period.

### 5. Dimensions Describe, Facts Measure
If it's text or categorical → dimension
If it's numeric and additive → fact
Never put facts in dimensions.

---

## Topics Coming (Roadmap)

### Session 2: Slowly Changing Dimensions
- Type 0 (fixed), Type 1 (overwrite), Type 2 (history)
- When to use each
- Implementation patterns
- Handling big/slow changes

### Session 3: Fact Table Patterns
- Transaction facts
- Periodic snapshot facts
- Accumulating snapshot facts
- Factless fact tables
- Degenerate dimensions

### Session 4: Conformed Dimensions & Bus Architecture
- Shared dimensions across fact tables
- The dimensional bus matrix
- Incremental dimensional design
- Enterprise warehouse strategy

### Session 5: Incremental Loading Strategies
- Idempotent pipelines
- SCD Type 2 updates
- Late-arriving facts/dimensions
- Data quality at grain level

---

## Key References

**Essential Reading:**
- *The Data Warehouse Toolkit* by Ralph Kimball & Margy Ross (3rd edition)
  - Chapters 1-3: Dimensional modeling fundamentals
  - Chapters 4-6: Advanced patterns
  - Entire book: Comprehensive reference

**Kimball Group Resources:**
- https://www.kimballgroup.com/ (dimensional modeling guidelines)
- https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/ (free resources)

**This Series:**
- Built by Milan Macwan in collaboration with Indian Data Club
- Designed for data engineers, analytics engineers, SQL developers
- All examples are production-aligned (not Kaggle-style toy projects)

---

## Community & Feedback

This series is developed for **Indian Data Club (IDC)**, an active community of data professionals in India.

**Feedback:** If you're using these materials and find:
- Gaps in explanation
- Examples that don't land
- Topics that need more depth
- Mistakes or clarifications needed

Share it. This series improves through real-world use.

---

## Sessions Delivered

| # | Session | Date | Attendees | Recording |
|---|---------|------|-----------|-----------|
| 1 | Four-Step Dimensional Design | TBD | TBD | TBD |
| 2 | Slowly Changing Dimensions | TBD | TBD | TBD |
| 3 | Fact Table Patterns | TBD | TBD | TBD |

---

## Legal & Attribution

- **Framework:** Ralph Kimball (The Data Warehouse Toolkit)
- **Examples:** Milan Macwan (original retail scenario)
- **Community:** Indian Data Club

This material is educational. Use it. Teach others. Build better data systems.

---

## Contact & Questions

**For IDC Members:**
- Share in Discord #data-engineering channel
- Discuss in live Q&A sessions

**For Feedback:**
- Specific suggestion? Share it.
- Better way to explain something? Suggest it.
- Real-world scenario to add? Contribute it.

---

## Version History

**v1.0** (Current)
- Session 1: Four-Step Dimensional Design (45 min, 35 slides)
- Speaker notes framework established
- Example organization created

---

**Last Updated:** June 2024

---

*"Build focused models. One grain. Clear dimensions. Additive facts. Everything follows from these decisions."* — Based on Kimball principles
