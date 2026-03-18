# Dev Diaries

This document outlines the step-by-step process of uncovering development traces for the `marvenly.com`.

---

## Description

We have just launched a website developed by a freelance developer. The source code was not shared with us, and the developer has since disappeared without handing it over.

Despite this, traces of the development process and earlier versions of the website may still exist online.

You are only given the website's primary domain as a starting point: `marvenly.com`

---

## Task 1: Tracking the Developer

### 1.1 What is the subdomain where the development version of the website is hosted?

**Answer:** `uat-testing.marvenly.com`

**Methodology:**

- I utilized **DNSdumpster** to map the DNS infrastructure of `marvenly.com`.
- By analyzing the Type A records, I discovered the staging environment used for User Acceptance Testing (UAT).

![Q1](dev-diaries/images/q1.png)

---

### 1.2 What is the GitHub username of the developer?

**Answer:** `notvibecoder23`

**Methodology:**

- Conducted a manual audit of the live website's **footer**.
- Identified a developer credit link that redirected to the GitHub profile of the freelancer.

![Q2](dev-diaries/images/q2.png)

---

### 1.3 What is the developer's email address?

**Answer:** `freelancedevbycoder23@gmail.com`

**Methodology:**

- I performed a **Git Patch Analysis**. By navigating to one of the developer's commits and appending `.patch` to the URL, I accessed the raw commit metadata.
- This revealed the `From:` field, which contains the author's real name and email address used for the Git configuration.

![Q3](dev-diaries/images/q3.png)

---

### 1.4 What reason did the developer mention in the commit history for removing the source code?

**Answer:** `The project was marked as abandoned due to a payment dispute`

**Methodology:**

- I inspected the **Commit History** (Commit Log) of the repository.
- Found a specific commit where the codebase was wiped. The commit message explicitly detailed the reason for the removal.

![Q4](dev-diaries/images/q4.png)

---

### 1.5 What is the value of the hidden flag?

**Answer:** `THM{g1t_h1st0ry_n3v3r_f0rg3ts}`

**Methodology:**

- I performed a "Time Travel" investigation by browsing the repository's file tree at a state **prior** to the payment dispute commit.
- Located the flag within the source code files that had been deleted in the final version.

![Q5](dev-diaries/images/q5.png)
