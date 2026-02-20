# DATA SCIENCE CASE STUDY
## The Churn Prediction Paradox

---

## Background

You're a data scientist consultant brought into **M-Pesa Alternative** (name changed), a fast-growing Kenyan mobile money platform with 2.5M active users.

Three months ago, they deployed a churn prediction model with impressive metrics:
- **87% accuracy**
- **AUC-ROC of 0.91**
- Built by a reputable ML consultancy

The leadership team was thrilled. The model scores every customer weekly, and anyone with a churn probability >60% gets enrolled in retention campaigns (SMS with offers like cashback, zero-fee periods, or airtime bonuses).

---

## The Problem

**Head of Retention (clearly frustrated)**: "This model is useless. We've contacted 2,700+ customers in the past 3 months. Response rate is terrible—barely 15%. And even when they respond, half of them churn anyway! Meanwhile, we're hemorrhaging customers we never even contacted. Something is fundamentally broken."

**Chief Data Officer**: "The model performed well in testing. 87% accuracy. We followed best practices. Maybe the offers are weak? Or timing is off?"

**Head of Retention**: "Don't blame my team! Your model is targeting the wrong people!"

**CEO**: "I need answers. We're burning budget on these campaigns and our retention metrics haven't improved. Figure out what's wrong and fix it."

---

## Your Mission

You have 7 days to:

1. **Diagnose the problem** - Why is a model with 87% accuracy failing in production?

2. **Propose a better framework** - How should they be using predictions (or should they scrap this approach entirely)?

3. **Build a proof-of-concept improvement** - This could be:
   - A better model
   - A smarter targeting/segmentation strategy
   - A different approach to intervention timing
   - Something else entirely

**Deliverable**: 
- Written analysis (max 3 pages) explaining your diagnosis
- Code/notebook showing your approach
- One clear, actionable recommendation for the retention team

---

## What You're Given

### Files Provided:

1. **customer_features.csv** - Customer characteristics (5,000 customers)
2. **model_predictions.csv** - Model output from 3 months ago
3. **retention_campaigns.csv** - Who was contacted and how they responded
4. **actual_outcomes.csv** - Who actually churned (3 months later)
5. **model_documentation.txt** - How the existing model was built

### Data Dictionary:

**customer_features.csv**
- `customer_id`: Unique identifier
- `account_age_days`: Days since account creation
- `age`: Customer age
- `county`: County of residence (Nairobi, Kiambu, Nakuru, Mombasa, etc.)
- `avg_monthly_transactions`: Average transactions per month
- `avg_transaction_value`: Average transaction amount (KES)
- `wallet_balance`: Current wallet balance (KES)
- `days_since_last_transaction`: Days since most recent activity

**model_predictions.csv**
- `customer_id`: Unique identifier
- `model_churn_probability`: Model's predicted churn probability (0-1)
- `contacted`: Whether customer was contacted by retention team
- `offer_type`: Type of offer sent (if contacted)
- `responded`: Whether customer responded to the campaign

**actual_outcomes.csv**
- `customer_id`: Unique identifier
- `actual_churned`: Whether customer actually churned (True/False)

**retention_campaigns.csv**
- Subset of model_predictions.csv + actual outcomes for contacted customers
- Shows the full picture of campaign performance

---

## Important Context

**Churn Definition**: A customer is considered "churned" if they have no transactions for 90 consecutive days.

**Campaign Approach**: Every Monday, the model scores all customers. Anyone with predicted churn probability >0.6 gets sent an SMS with one of three offers:
- "Get KES 100 cashback on your next transaction!"
- "Zero transaction fees for the next 7 days!"
- "Free KES 50 airtime bonus - claim now!"

**The Frustration**: The retention team feels like they're shooting in the dark. High response rates would be 40-50% in the industry. They're getting 15%. And when customers DO respond, many still churn.

---

## Your Approach

You can take this in multiple directions. Some possibilities:

### Option A: Model Improvement
- Rebuild the predictive model with better features/approach
- Focus on recall for actual churners vs. overall accuracy
- Use different algorithms or ensemble methods

### Option B: Segmentation Strategy
- Maybe not everyone should be treated the same
- Identify subgroups with different churn drivers
- Tailor interventions to specific segments

### Option C: Targeting/Timing Strategy
- Perhaps the model is fine, but they're contacting people at the wrong time
- Or the threshold (0.6) is wrong
- Or they need uplift modeling (who responds to intervention?)

### Option D: Something Else Entirely
- Maybe the whole approach is flawed
- Perhaps there's a better way to think about retention
- Show us your creative solution

**No "right" answer** - we want to see how you think through a messy, real-world problem.

---

## Deliverable Format

### 1. Written Analysis (Max 3 Pages)
Answer these questions:
- What's wrong with the current approach? (Be specific!)
- Why does the model have 87% accuracy but fail in production?
- What insights did you uncover in the data?
- What do you recommend and why?

### 2. Technical Implementation
Provide a Jupyter notebook, R markdown, or well-commented script showing:
- Your exploratory analysis
- Your proof-of-concept solution
- How you validated your approach

### 3. One-Page Recommendation
What should the retention team DO differently starting Monday? Make it actionable.

---

## Evaluation Criteria

1. **Diagnosis & Problem-Solving** (40%)
   - Did you identify the core issue?
   - Did you dig deeper than surface-level metrics?
   - Did you ask good questions of the data?

2. **Technical Approach** (30%)
   - Appropriate methods for the problem
   - Sound validation approach
   - Clean, reproducible code

3. **Communication** (20%)
   - Clear explanation of complex concepts
   - Compelling narrative
   - Actionable insights

4. **Business Impact** (10%)
   - Practical recommendations
   - Consideration of constraints
   - Understanding of real-world implementation

---

## Submission

Please submit:
1. Written analysis (PDF or markdown)
2. Code/notebook with your analysis
3. One-page recommendation for the retention team

**Deadline**: 7 days from receiving this brief

---

## Hints & Considerations

Some things to think about (not exhaustive):

- **Accuracy can be misleading** - especially with imbalanced classes
- **Production ≠ Training** - what works in a notebook might fail in the real world
- **Churn has many flavors** - a new user going dormant ≠ a power user churning
- **Causation matters** - who would have churned anyway vs. who you can save?
- **Constraints are real** - retention teams have limited capacity and budget

**The Best Candidates**: Don't just find the problem - they propose a path forward that the retention team can actually execute.

---

## Questions?

You can make reasonable assumptions, but if something critical is unclear, document your assumptions in your analysis.

We're excited to see your approach. Good luck!

---

## A Note on Tools

Use whatever you're comfortable with - Python, R, SQL, Excel, doesn't matter. We care about your thinking, not your tech stack. That said, we should be able to run/review your code, so please provide:
- Clear setup instructions if needed
- Comments explaining your logic
- Clean, readable code structure

**Most importantly**: Show your work. We want to understand your thought process, not just see a final answer.
