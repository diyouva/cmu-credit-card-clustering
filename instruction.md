# Clustering Credit Card Customers

In this case, we will be comparing clustering methods to identify customer grouping for a credit card company. We will be using the same dataset and driving questions that we discussed in our breakout groups in our live class session on clustering.

> **Note:** You do not need to reference the in-class discussion or address any discussion questions from the in-class discussion of clustering credit card customers.

Now that we have thought through the initial analysis factors and have some working hypotheses around what clustering approaches to try, we will get hands on with clustering in Python.

For this assignment, you will be evaluated on how you use the clustering techniques to come up with **data-driven recommendations**. Be sure to spend your time on both:
- The **technical portions** (choosing the number of clusters, for example)
- Considering how they relate to the **organizational strategy**

Additional information about how credit card companies earn revenue can be found in the [class discussion document](https://docs.google.com/document/d/1Qi8bK23ANJjoZA6_hC14wnAXHlzdGKxn33aIiyjlQ00/edit?usp=sharing).

---

## Questions to Address

### Question 1: Segment Customers with K-Means

Using the available data, explore building customer segments using K-Means. This will involve typically three steps:

1. **Choosing the columns to include in the cluster**
   - This is often an iterative and trial-and-error approach that involves using your hypotheses and visualizing the clustering results.
   - Remember, for K-Means **every column you add will be weighted the same when forming the clusters**. So if you include five columns, each of them will contribute equally to how the clusters are formed.

2. **Use at least two methods for determining optimal cluster size**
   - Note that the optimal number of clusters changes depending on the variables in the model.
   - You may find that as you add additional clustering variables the optimal number of clusters changes.

3. **Explore the clusters visually and/or with summary tables**
   - Look for key differences between clusters.
   - Once you have formed the clusters, you can break down the average number of transactions, or average revolving balance for example of each cluster.
   - How are your clusters meaningfully different?
   - Examples of this can be found in our [clustering mall customers exercise](https://colab.research.google.com/drive/1BEWfaVqPvm17B1mFSjjmcFOWor58o4nh?usp=sharing).

---

### Question 2: Segment Customers with Hierarchical Clustering or DBSCAN

Using example code from our in-class content on mall customers, develop customer segments using either **Hierarchical Clustering** or **DBSCAN**.

> **Note:** You do not need to do both.

Consider the following:
- How are the clusters different?
- How might these different approaches impact your clusters?
- What challenges did you come across when using these clustering methods?

---

### Question 3: Recommendations

Write up a description of your best customer clusters (either K-Means, Hierarchical, or DBSCAN) along with recommendations for:
- **Product improvements**
- **Marketing initiatives**

Describe how the clusters are different from each other using key metrics from the dataset.

> 💡 **Tip:** Having descriptive names for each cluster is helpful here. For example, rather than "Cluster 1, Cluster 2", call a cluster "High Spenders" or "No Revolving Balance" or some other catchy marketing name that describes the customers in this cluster.

---

## Deliverables

Please create a **zip file** with these three files for your final deliverables:

| # | Deliverable | Format |
|---|-------------|--------|
| 1 | A **written 5-10 page report** addressing the questions above including visuals. You may include additional visuals in an appendix if you would like. | PDF/Word |
| 2 | A **Python Notebook** file with all the code you used to analyze the data to address the questions and complete the lab. We will be looking at your code to see if the code generates the results. | `.ipynb` |
| 3 | If you use Generative AI to produce code, submit a file with the transcript of your chat session. | Word/Text |

> ⚠️ **Important:** Please **do not use** Generative AI to create text for the report.

---

## Groups

You may work on this assignment in groups of **up to three people**.

- Please do not share code or findings with anyone not in your group.
- [Create a group with all of your group members](https://canvas.cmu.edu/courses/52229/groups#tab-20501) on Canvas **prior to submitting your assignment**.

---

## Generative AI Policy

You may use Generative AI such as ChatGPT or GitHub's Copilot to help you on the **technical portion** of this assignment.

ChatGPT, Gemini, and Claude can be particularly helpful for:
- Explaining a small block of code you are having trouble with
- Resolving error messages you may come across

---

## Rubric

**Total Points: 30**

### 1. Feature Selection and Problem Framing (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Clear, thoughtful explanation of why selected variables are appropriate for customer segmentation. Demonstrates understanding of equal weighting in K-Means. Shows some iteration or comparison across feature sets. |
| **4** | Strong | Reasonable variable choices with basic justification. Limited discussion of tradeoffs or iteration. |
| **3** | Adequate | Variables selected but justification is limited or mostly descriptive. Weak connection to clustering mechanics or business context. |
| **2** | Weak | Minimal explanation of why variables were chosen. Choices appear arbitrary or copied without reasoning. |
| **1** | Poor | Variables poorly chosen or unjustified. |
| **0** | Missing | No meaningful discussion of feature choice. |

---

### 2. K-Means Implementation and Cluster Selection (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Correct K-Means implementation. Uses at least two methods to select k. Clear, well-reasoned justification for final k. |
| **4** | Strong | Correct implementation with two methods shown. Explanation of k selection is brief or slightly unclear. |
| **3** | Adequate | K-Means implemented correctly. Only one method used or interpretation is weak. |
| **2** | Weak | Cluster selection methods used incorrectly or superficially. |
| **1** | Poor | Major issues in implementation or interpretation. |
| **0** | Missing | K-Means not meaningfully applied. |

---

### 3. Alternative Clustering Method - Hierarchical or DBSCAN (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Correct implementation of Hierarchical or DBSCAN. Thoughtful discussion of parameters and challenges. Clear comparison to K-Means results. |
| **4** | Strong | Correct implementation with some comparison to K-Means. Limited discussion of tradeoffs. |
| **3** | Adequate | Alternative method applied but interpretation is shallow. |
| **2** | Weak | Method used mechanically with little explanation. |
| **1** | Poor | Incorrect or poorly explained implementation. |
| **0** | Missing | No alternative clustering method included. |

---

### 4. Cluster Interpretation and Descriptive Analysis (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Clusters clearly described using key metrics. Meaningful differences highlighted with tables and/or visuals. Interpretation goes beyond surface-level description. |
| **4** | Strong | Clear descriptions with relevant metrics. Some insights but limited depth. |
| **3** | Adequate | Basic cluster descriptions with minimal comparison. |
| **2** | Weak | Vague or repetitive descriptions. |
| **1** | Poor | Little understanding of cluster differences. |
| **0** | Missing | No meaningful interpretation provided. |

---

### 5. Recommendations and Organizational Strategy Alignment (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Clear, actionable recommendations tied directly to clusters. Strong connection to credit card business model. Descriptive and intuitive cluster names used. |
| **4** | Strong | Good recommendations with reasonable business logic. Minor gaps in specificity or metric linkage. |
| **3** | Adequate | General recommendations loosely tied to clusters. |
| **2** | Weak | Recommendations are generic or poorly supported. |
| **1** | Poor | Recommendations are unclear or unrealistic. |
| **0** | Missing | No meaningful recommendations provided. |

---

### 6. Deliverables, Code Quality, and Communication (5 pts)

| Points | Rating | Description |
|--------|--------|-------------|
| **5** | Excellent | Report is clear, well organized, and complete. Notebook runs cleanly and reproduces results. AI transcript included when required and used appropriately. |
| **4** | Strong | Minor issues with clarity, formatting, or organization. |
| **3** | Adequate | Understandable but uneven or incomplete presentation. |
| **2** | Weak | Significant clarity, organization, or reproducibility issues. |
| **1** | Poor | Major problems with required deliverables. |
| **0** | Missing | Required components missing or unusable. |
