---
layout: default
title: Elections
parent: Running Meetings
grand_parent: Club Operations & Governance
nav_order: 3 # After Exec Meetings, or 1 if preferred
description: How to run secure hybrid elections
---

# Secure Voting

Running a hybrid AGM (with both in-person and online attendees) presents challenges for fair and secure voting. While in-person voting is straightforward if you go 'old school' with paper ballots issued to attendees by the Returning Officer, online voting runs the risk of being insecure and open to manipulation.
Similarly, hand-counting votes can be time-consuming and error-prone, especially with large numbers of attendees.

One of the most effective and free solutions to both of these problems is to use **randomised one-time codes** distributed only to eligible attendees, combined with a properly configured Google Form for voting.
In this guide, we'll explain how to do it step by step.

See also: [General Meetings](/docs/club-ops-governance/running-meetings/general-meetings.html) for more information about running general meetings, including elections. Here, we focus on the voting process itself.

---

## ✅ Why Use Voting Codes?

Using one-time voting codes ensures:

* Only **eligible members** who are present at the meeting can vote.
* Each person votes **only once**.
* Ballot links can't be forwarded to outsiders.
* You have a simple way to **audit and verify** results.

---

## 🧭 Step-by-Step: How to Run Voting with Codes

### 1. **Determine Voter Eligibility**

Before distributing any codes, decide who is allowed to vote. You can do this by:

* Having attendees **sign in at the door** (for in-person meetings).
* Asking online attendees to **sign in via Zoom chat** with their name and student ID.
* Checking against your **club’s membership register** as you go.

This gives you a list of everyone eligible to vote at the meeting.

---

### 2. **Generate Random Voting Codes**

Use Google Sheets to quickly create unique, hard-to-guess codes.

**Paste this formula into cell A1 of a new Google Sheet and pull down:**

```excel
=ARRAYFORMULA(LEFT(SUBSTITUTE(DEC2HEX(RANDBETWEEN(1048576,16777215)), "0", "X"), 6))
```

It will generate a column of codes like:

```
A1X9FQ  
Z4T2JW  
KD7RXM  
...
```

**Tips:**

* Generate 5–10 extra codes than your expected attendance.
* If you want a printable sheet with names, make a second column to write down who each code was given to.

---

### 3. **Distribute the Codes**

* **In-person attendees**: Print out codes on slips of paper and hand them out after sign-in.
* **Online attendees**: Send each code **via private Zoom message** once they’ve signed in.

> ⚠️ Don’t publish codes in public chats or emails. They must only go to verified attendees.

---

### 4. **Set Up Your Google Voting Form**

You can build a secure ballot using Google Forms. Make sure it includes:

* A required question: “**Enter your unique voting code**”
* Any voting questions (e.g. motions, candidate selections)
* Set to **“Limit to 1 response”**

Other settings to consider, but not strictly necessary:
  * Optionally **collect email addresses** (not essential if codes are anonymous)
  * **response validation** to enforce a 6-character format (e.g. using regex).

#### Example Google Forms Guide:

For setting up preferential voting or more complex ballots using Google Forms, see: [https://www.rankedvote.co/guides/applying-ranked-choice-voting/how-to-calculate-ranked-choice-voting-with-google-forms-and-google-sheets](https://www.rankedvote.co/guides/applying-ranked-choice-voting/how-to-calculate-ranked-choice-voting-with-google-forms-and-google-sheets)

---

### 5. **Voting Process**

* Announce the vote live in the meeting (in-person and online).
* Share the voting form **link only during the meeting**, not in advance.
* Close the form after the vote is complete to prevent late submissions.

---

### 6. **Counting and Verifying Votes**

When votes are submitted:

* Export responses from Google Forms to a Google Sheet.
* Discard any vote that:

  * Has a **missing or invalid code**
  * Has a **duplicate code** (only the first should be accepted)
* If codes were linked to names, you can cross-check further. Otherwise, results stay anonymous.

#### How to Check Valid Codes

To check validity in Google Sheets, suppose that column B contains the voting codes from the form responses, and column F contains the original list of valid codes. 

We first check for missing or invalid codes. Write the following in a new column (e.g. Cell C2):
```excel
=IF(COUNTIF($F$2:$F$100, B2) > 0, "Valid", "INVALID")
```
Drag this down to apply it to all rows. This will mark each code as "Valid" or "INVALID".

Next, to check for duplicates, add another column (e.g column D)
with this formula in Cell D2:
```excel
=IF(COUNTIF($B$2:$B$100, B2) > 1, "DUPLICATE", "")
```
This wil flag every vote using a code that has been used more than once. You'll likely want to count only the first instance of each duplicate as valid and discard the rest manually.

---

## Tips & FAQs

### Can people vote anonymously?

Yes. You don’t have to link codes to names unless you want extra auditability. Anonymous code use still prevents fraud.

### How secure is this?
It's very secure if done correctly. We prevent:
- **Ballot stuffing**: because each person receives only one code and the voting form checks for duplicates, it's very hard to submit multiple votes.
- **Link sharing**: even if a link is shared, others won't be able to vote without a valid code.
- **Non-member interference**: only people recorded as present and eligible to vote receive a code.
- **Voting by absent members**: no code = no vote.

Of course, there are a bunch of issues that can arise, which we outline below, but these are all manageable.



| Potential Issue                                 | Risk   | How to Mitigate                                                              |
| ----------------------------------------------- | ------ | ---------------------------------------------------------------------------- |
| Someone shares their code with a friend         | Low    | Codes should be single-use; duplicates are flagged and extra votes discarded |
| A member joins late and misses the code handout | Medium | Allow returning officers to issue extra codes live (e.g. via DM)             |
| A returning officer mismanages codes            | Medium | Keep a master list of issued codes (especially if codes are linked to names) |
| Codes leaked before the meeting                 | Low    | Don’t generate or distribute codes until the meeting starts                  |

### Can we reuse codes for multiple votes?
One code per person per meeting is fine. Reusing codes across different meetings is not a good idea!
