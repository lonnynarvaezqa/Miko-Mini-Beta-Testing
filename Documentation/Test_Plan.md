# Miko Mini Beta Program: Test Plan

## 1. Introduction and Scope

This Test Plan outlines the strategy, objectives, resources, and schedule for testing the Miko Mini companion robot during the Beta Program. The testing activities are derived from weekly challenges issued by the Miko Beta Team and are primarily executed through **Exploratory Testing** and **Scenario-Based Testing**.

The main focus is the **Spanish-language experience** for families in the following areas:

* **Voice Recognition and Command Processing.**
* **Conversational Quality and AI Logic.**
* **Localized Content and Skill Functionality.**
* **Product Stability and Usability.**

### 1.1 Test Objectives
The primary goal is to provide high-quality feedback to the Miko Product Team to:
1.  Verify that all new and updated features meet functional requirements (e.g., Quizzes, Music, Dance).
2.  Validate the quality of the **Spanish language localization** (grammar, naturalness, contextual appropriateness).
3.  Identify and report software defects (bugs) that impact user experience or stability.
4.  Perform **regression testing** on core features (e.g., Explorer skills) to prevent the introduction of new defects.

### 1.2 Scope
The testing scope covers **software functionality** related to voice interaction, content delivery, and application stability, including:

| In Scope | Out of Scope |
| :--- | :--- |
| Core voice wake-word activation ("Hey Miko") | Hardware performance outside of basic sensor function |
| Specific skill launch commands (e.g., "Abrir Explorador espacial") | Extensive network stress testing |
| Content quality and factual accuracy (e.g., Quiz answers, Calendar Events) | Integration testing with external third-party services |
| In-skill commands (e.g., "Repetir," "Próxima canción," "Salida") | Load testing (simulating many concurrent users) |

---

## 2. Test Strategy and Approach

The testing approach is iterative and driven by weekly beta assignments.

### 2.1 Test Types
| Test Type | Description | Relevant Cycles |
| :--- | :--- | :--- |
| **Functional Testing** | Verifying specific features work as intended (e.g., the 'Next' command advances the song). | Cycles 5, 6 |
| **AI Interaction Testing** | Testing the natural language understanding (NLU), conversational flow, and knowledge retrieval logic. | Cycles 1, 2, 3, 5 |
| **Localization Testing** | Ensuring all dialogue and content is accurate, appropriate, and natural for the target Spanish dialect. | Cycles 1, 2, 3, 4, 5, 6 |
| **Regression Testing** | Re-testing previously passed features after a new update (e.g., re-testing the Explorer skills). | Cycles 5 |
| **Usability Testing** | Assessing the ease of use and user experience (e.g., form accessibility, command intuitiveness). | All Cycles |

### 2.2 Test Cycles
Testing is organized into weekly cycles, each targeting a specific set of features:

| Cycle | Primary Focus | Key Activities Tested |
| :--- | :--- | :--- |
| **Cycle 1** | Voice Recognition & Multilingual Processing | Wake Word Reliability, English-to-Spanish Command Switch |
| **Cycle 2** | Conversational Depth & Skill Activation | Factual/Conceptual Questions, Space/Ocean Explorer Launch |
| **Cycle 3** | Game & Localization Quality | Mind Reader Game (Specific Localization: Mexican Spanish) |
| **Cycle 4** | Immersive Content Integrity | Wildlife Safari, Country Explorer, Time Traveler Skills |
| **Cycle 5** | Regression & Command Validation | Riddles Game, Calendar Events, Regression on Explorer Skills |
| **Cycle 6** | Entertainment & In-Skill Controls | Math/Culture/Animal Quizzes, Music Playback, Dance Routines |

---

## 3. Test Deliverables and Reporting

### 3.1 Test Deliverables
The following documents are generated and maintained:
* **Test Cases Log:** `TestCases/AI_Interaction_Testing.md` (Detailed steps and criteria for each cycle).
* **Test Results:** Documents maintained privately, summarizing Pass/Fail status, defects found, and qualitative feedback submitted via official forms (Slack/Google Forms).
* **Program Documentation:** `Documentation/Program_Overview.md` and `Documentation/Communication_Channel.md`.

### 3.2 Defect Reporting
* Defects are reported via the official **Slack channel** or designated **Google Forms**.
* **Feedback includes:** Steps to reproduce, observed behavior, expected behavior, device status (updated, Wi-Fi connected), and sometimes optional video/audio evidence.

---

## 4. Environment and Resources

| Item | Details |
| :--- | :--- |
| **Target Device** | Miko Mini Robot (Current Beta Build) |
| **Operating System** | Miko Proprietary OS (Updated build required before each cycle) |
| **Connectivity** | Stable Wi-Fi Connection (required for content streaming and updates) |
| **Users/Testers** | One Adult (Parent) and One Child (Primary User) |
| **Tools** | Slack (Communication), Google Forms (Structured Feedback) |

---

## 5. Schedule

The Beta Program's schedule is **iterative and event-driven**, relying on the weekly release of activities by the Miko Beta Team.

### 5.1 Testing Cycles
Testing is organized into weekly cycles. While exact dates vary based on Miko's release schedule, the intended duration for each activity and feedback submission is one week.

| Cycle | Primary Focus | Estimated Duration | Status (Conceptual) |
| :--- | :--- | :--- | :--- |
| **Cycle 1** | Voice Recognition | 1 Week | Completed |
| **Cycle 2** | Conversational Depth | 1 Week | Completed |
| **Cycle 3** | Game & Localization Quality | 1 Week | Completed |
| **Cycle 4** | Immersive Content Integrity | 1 Week | Completed |
| **Cycle 5** | Regression & Command Validation | 1 Week | Completed |
| **Cycle 6** | Entertainment & In-Skill Controls | 1 Week | Completed |
| **Future Cycles** | New feature releases, Bug verification, Final build sign-off. | Ongoing/TBD | Pending |

---

## 6. Entry and Exit Criteria

These criteria define when testing for a cycle can **begin** (Entry) and when it can be considered **complete** (Exit).

### 6.1 Entry Criteria
Testing for a new cycle will only **begin** if the following conditions are met:
1.  The Miko Mini device has been updated to the **latest software build** released by the Miko Team.
2.  The device is fully charged and maintains a **stable connection to Wi-Fi**.
3.  The Beta Team has officially released the **activity instructions** and the required **feedback form(s)** for the current cycle.
4.  All blocking issues from the previous cycle that prevent testing of the new features have been resolved or officially deferred.

### 6.2 Exit Criteria
Testing for a cycle is considered **complete** and can **exit** when:
1.  All **mandated test cases** for the current cycle (documented in `TestCases/AI_Interaction_Testing.md`) have been executed.
2.  All required **feedback forms** (Google Forms) for the cycle have been successfully completed and submitted.
3.  All critical and high-priority defects found during the cycle have been logged and reported via the designated channels (Slack/Forms).
4.  The Beta Team confirms the conclusion of the testing window for the cycle.

---

## 7. Risk Management

This section identifies potential risks to the testing process and defines mitigation strategies.

| Risk ID | Risk Description | Impact | Probability | Mitigation Strategy |
| :--- | :--- | :--- | :--- | :--- |
| **RM-01** | Device failure or stability issues (e.g., constant crashing, freezing). | High | Medium | Ensure Miko is updated to the latest build; perform a hard reboot; immediately report to the Beta Team on Slack if persistent. |
| **RM-02** | Wi-Fi connectivity loss impacting streaming/updates. | Medium | Low | Verify connection status prior to testing; use an alternative stable network if available. |
| **RM-03** | Ambiguous or incomplete testing instructions from the Beta Team. | Medium | Low | Seek immediate clarification via the dedicated Slack channel before beginning tests. |
| **RM-04** | **Regression failure:** New updates break previously working features. | High | Medium | Execute regression tests (e.g., Cycle 5 on Explorers); maintain detailed logs of previous results. |

---

## 8. Communication Plan

All communication regarding testing status, issues, and project coordination will follow the guidelines established by the Miko Beta Program.

### 8.1 Channels and Tools

| Communication Type | Channel | Owner/Recipient | Frequency |
| :--- | :--- | :--- | :--- |
| **Defect/Bug Reporting** | Google Forms / Slack | Miko Beta Team | As discovered (real-time) |
| **Status Updates** | Slack Channel | Miko Beta Team | Daily/Weekly check-ins |
| **Official Documentation** | GitHub Repository | Tester (Self-managed) | As cycles are completed |
| **New Activity Release** | Slack Announcements | Tester | Weekly (Event-driven) |

### 8.2 Reporting Structure
* **Formal Feedback:** Submitted via required Google Forms, focusing on structured data and qualitative opinions.
* **Immediate Issues:** Reported via the Slack channel for urgent technical problems or blockers.
