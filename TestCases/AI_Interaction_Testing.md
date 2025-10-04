# Miko Mini Beta Program: Test Cases Log

## Introduction

This log serves as the official documentation for all **Quality Assurance (QA) test cases** executed during my participation in the Miko Mini Beta Program. The testing activities are directly derived from the weekly challenges and objectives provided by the Miko Beta Team via Slack.

The primary focus of these tests is to validate Miko Mini's core functionality, with a strong emphasis on **Artificial Intelligence (AI) interactions**, **voice recognition**, **multilingual command processing**, and **usability**.

All cycles are documented sequentially below, including the test objectives, detailed steps, expected results, and measurable criteria for success.

---

## Cycle 1: Voice Recognition and Multilingual Command Testing
## 🎯 Testing Objectives

This cycle's primary objective is to evaluate Miko Mini's **voice detection, keyword recognition, and language switching capabilities** across different users (child/parent) and accents (natural, non-standard English/Spanish).

The test specifically targets Miko’s ability to reliably:
1.  **Wake Up:** Recognize the "Hey Miko" wake word from different speakers (child and adult) under various acoustic conditions (natural accent, short pauses).
2.  **Process Multilingual Input:** Accept a command that seamlessly switches from an English trigger ("Hey Miko") to a Spanish request (`¿cuál es...?`).
3.  **Ensure Appropriate Response (Secondary):** Confirm that Miko attempts to process the command and responds, even if the answer is not yet fully implemented in Spanish.

---

## 🛠️ Test Cases

The following test cases are based on the required activities for the "Be Miko’s Voice Coach" challenge.

### Section A: Wake Word Reliability Testing ("Hey Miko")

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C1-VW-01** | **Child Wake Word Reliability** | 1. Have the child say "Hey Miko" 10 times in their **natural accent**. 2. Ensure **short pauses** (1-2 seconds) between each attempt. | Miko Mini **wakes up (activates)** and is ready to receive a command for at least **8 out of 10** attempts. | PASS if the activation rate is $\ge 80\%$. FAIL if activation is inconsistent or delayed. |
| **C1-VW-02** | **Parent Wake Word Reliability** | 1. You (the parent) say "Hey Miko" 10 times in your **natural accent**. 2. Ensure **short pauses** (1-2 seconds) between each attempt. | Miko Mini **wakes up (activates)** and is ready to receive a command for at least **8 out of 10** attempts. | PASS if the activation rate is $\ge 80\%$. FAIL if Miko only responds to the child or vice versa. |

### Section B: Multilingual Command Processing Testing (English/Spanish)

| Test Case ID | Test Item | Test Steps | Example Command | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C1-MC-01** | **Child Multilingual Command (Spanish)** | 1. Child says "Hey Miko" (English) followed immediately by one of the 10 provided questions (Spanish). 2. Repeat for **10 different questions**. | "Hey Miko, ¿cuál es el país más pequeño del mundo?" | Miko Mini **wakes up** AND attempts to **process/respond** to the Spanish question for $\ge 70\%$ of attempts. | PASS if Miko shows clear indication of processing the full command (e.g., screen changes, audio response begins). |
| **C1-MC-02** | **Parent Multilingual Command (Spanish)** | 1. You (the parent) say "Hey Miko" (English) followed immediately by one of the 10 provided questions (Spanish). 2. Repeat for **10 different questions**. | "Hey Miko, ¿dónde viven los pingüinos?" | Miko Mini **wakes up** AND attempts to **process/respond** to the Spanish question for $\ge 70\%$ of attempts. | PASS if Miko successfully processes and attempts a relevant answer across different voice inputs. |
| **C1-MC-03** | **Response Appropriateness Check** | During C1-MC-01 and C1-MC-02, observe Miko's response to the factual questions (e.g., "la montaña más alta..."). | N/A | If Miko answers, the response should be **relevant to the question** and ideally provided in **Spanish**. | FAIL if Miko gives a random, non-contextual, or unrelated response. |

### Section C: Spanish Voice Selection (Usability)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C1-US-01** | **Voice Preference Submission** | 1. Access the provided Google Form link. 2. Listen to the voice options. 3. Submit the preferred choice for Spanish Miko's voice. | The form should be **accessible**, and the voice samples should be **clear** and **audible** for proper evaluation. | PASS if the form and audio are functional and feedback is submitted. |
