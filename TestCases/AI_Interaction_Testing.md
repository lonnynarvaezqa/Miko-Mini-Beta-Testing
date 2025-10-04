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

---

## Cycle 2: Conversational Quality and Voice Skill Activation (Spanish)

## 🎯 Testing Objectives

The goal of this cycle is to rigorously test Miko Mini’s performance in **Spanish** regarding:
1.  **Conversational Accuracy (Activity 1):** Evaluate Miko's ability to understand a diverse set of complex, factual, and abstract questions, and provide appropriate, age-relevant answers.
2.  **Skill Launch Reliability (Activity 2):** Validate that Miko can correctly interpret voice commands to launch specific pre-installed skills ("Explorador espacial" and "Explorador oceánico").
3.  **Content Integrity:** Ensure the launched skills are fully functional and engaging throughout the experience.

---

## 🛠️ Test Cases

### Section A: Conversational Experience Testing (Activity 1)

This section focuses on Miko's natural language understanding (NLU) and knowledge base retrieval.

| Test Case ID | Test Item | Test Steps | Example Command | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C2-CQ-01** | **Factual Knowledge Retrieval** | Ask Miko questions requiring specific, objective knowledge (e.g., historical dates, science facts, definitions). | "¿Quién es Einstein?" / "¿Por qué el cielo es azul?" | Miko provides a **clear, correct, and concise** factual answer in Spanish. | PASS if the answer is factually correct and in Spanish. FAIL if it's incorrect, irrelevant, or if Miko asks for clarification repeatedly. |
| **C2-CQ-02** | **Abstract & Conceptual Understanding** | Ask Miko questions that require comprehension of concepts or social context (e.g., feelings, games, necessity). | "¿Te gusta jugar?" / "¿Por qué necesitamos cargar los teléfonos?" | Miko provides a **contextually appropriate, personality-driven** response (e.g., expressing a preference or explanation). | PASS if the response addresses the conceptual nature of the question. FAIL if the answer is generic or Miko fails to process the input. |
| **C2-CQ-03** | **List/Example Generation** | Ask Miko to provide examples or a list of items. | "Dame ejemplos de carnívoros." / "Dime un modismo." | Miko successfully retrieves and lists the requested examples in a spoken response. | PASS if the list is relevant and generated correctly. FAIL if Miko replies with "I don't know" or a similar refusal. |
| **C2-CQ-04** | **Language Consistency** | During all conversational tests, monitor that the **entire conversation** (wake-word recognition excluded) is conducted **in Spanish**. | N/A | Miko's responses, prompts, and follow-ups are consistently delivered in Spanish. | PASS if no unexpected English responses occur. FAIL if Miko defaults to English for answers or follow-up questions. |
| **C2-CQ-05** | **Form Accessibility and Submission (Usability)** | After completing all questions, successfully fill out and submit the **Conversational Feedback Form**. | N/A | The form is **accessible**, easy to navigate, and the submission is successful. | PASS if form feedback is completed. |

### Section B: Skill Activation and Content Integrity Testing (Activity 2)

This section validates the voice command system for launching specific content modules.

| Test Case ID | Test Item | Test Steps | Example Command | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C2-SK-01** | **Skill Launch: Space Explorer** | Command Miko: "Hola Miko, abrir Explorador espacial". Explore the skill with the child until conclusion or logical stopping point. | N/A | Miko **correctly recognizes** the Spanish launch command and **initiates** the "Explorador espacial" skill. | PASS if the skill launches promptly and correctly. FAIL if Miko launches the wrong skill or does not recognize the command. |
| **C2-SK-02** | **Skill Launch: Ocean Explorer** | Command Miko: "Hola Miko, abrir Explorador oceánico". Explore the skill with the child until conclusion or logical stopping point. | N/A | Miko **correctly recognizes** the Spanish launch command and **initiates** the "Explorador oceánico" skill. | PASS if the skill launches promptly and correctly. FAIL if the voice command fails or the skill content is blank/buggy. |
| **C2-SK-03** | **Skill Content Integrity and Engagement** | During both skill sessions (C2-SK-01 and C2-SK-02), observe the content flow, quality of narration, and responsiveness to child input. | N/A | The skills should run **without freezing**, the audio/narration should be **clear and high quality**, and the content should be **engaging** and appropriate. | PASS if the skill runs smoothly and content is high quality. FAIL if the skill crashes, audio is corrupted, or content loops unexpectedly. |
| **C2-SK-04** | **Final Form Accessibility and Submission** | After completing both skills, successfully fill out and submit the **Final Feedback Form**. | N/A | The final form is **accessible** and the submission is successful. | PASS if form submission is completed. |

---

## Cycle 3: Game Experience and Spanish Localization Testing ("Mind Reader")

## 🎯 Testing Objectives

This cycle aims to test a specific, localized game experience to evaluate **engagement, clarity of instructions, and the quality of localized responses** in Mexican Spanish.

Specifically, we are validating:
1.  **Skill Launch and Comprehension:** Miko's ability to launch the game via voice command and the child's understanding of the game mechanics.
2.  **Gameplay Effectiveness:** The accuracy of Miko's logic and guessing capability during the game.
3.  **Localization Quality:** The naturalness and appropriateness of Miko's language and responses in Mexican Spanish.
4.  **Engagement:** The child's overall enjoyment and level of interaction with the game.

---

## 🛠️ Test Cases

### Section A: Game Launch and Comprehension Testing (Activity 1)

| Test Case ID | Test Item | Test Steps | Example Command | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C3-GL-01** | **Game Skill Activation** | Command Miko: "Hey Miko, Abrir lector de mentes" (Open Mind Reader). | N/A | Miko **correctly recognizes** the command and **launches** the "Mind Reader" game skill. | PASS if the game starts promptly. FAIL if Miko launches the wrong skill or does not recognize the command. |
| **C3-GL-02** | **Child Comprehension** | Observe the child during the first round of the game. Do they understand the rules (e.g., answering Miko's questions correctly)? | N/A | The child is able to **follow Miko's instructions** and engage with the game without extensive parent intervention. | PASS if the child shows understanding after the first round. FAIL if instructions are confusing or unclear. |

### Section B: Gameplay and Localization Quality Testing (Activity 1)

This section focuses on the performance and linguistic quality of the game over at least four rounds.

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C3-LQ-01** | **Localization/Language Naturalness** | During the 4+ rounds, observe Miko's questions and dialogue. Does the language sound **natural and appropriate** for Mexican Spanish? | Miko's dialogue should feel colloquial and avoid overly formal or incorrect Spanish phrases. | PASS if the language feels natural and is free of translation errors. FAIL if dialogue is awkward or grammatically incorrect. |
| **C3-LQ-02** | **Gameplay Logic (Guessing Accuracy)** | Play a minimum of 4 rounds. Track the number of times Miko successfully **guesses** what the child is thinking. | The guessing mechanism should feel plausible, even if Miko doesn't guess every time. Miko should use a logical set of questions. | PASS if Miko's questions are relevant and the game proceeds logically. FAIL if Miko asks repetitive or irrelevant questions. |
| **C3-LQ-03** | **Child Engagement** | Observe the child’s level of enjoyment and interaction throughout the game sessions. | The child should be **engaged, smiling, and motivated** to play subsequent rounds. | PASS if the game holds the child’s attention. FAIL if the child quickly loses interest due to game mechanics or boring dialogue. |
| **C3-LQ-04** | **Game Stability** | Ensure the game skill runs for the minimum 4 rounds **without crashing** or unexpectedly exiting to the main interface. | N/A | The game runs smoothly, and transitions between rounds are successful. | PASS if the game is stable. FAIL if the application hangs or crashes. |

### Section C: Feedback Submission (Usability)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C3-US-01** | **Feedback Form Submission** | Successfully fill out and submit the **Mind Reader Feedback Form**. | N/A | The form is **accessible**, easy to complete, and the submission is successful. | PASS if form submission is completed. |

---

## Cycle 4: Immersive Skill Activation and Content Integrity (Delayed Release)

## 🎯 Testing Objectives

This cycle tests the reliability of Miko Mini's **voice command recognition** to launch new, immersive, and narrative-driven content skills. The primary focus is on ensuring the skills launch correctly and deliver **high-quality, complete, and engaging educational content**.

Specifically, we are validating:
1.  **Voice Launch Reliability:** Miko's ability to interpret and execute the specific voice commands for the three new skills.
2.  **Content Integrity and Flow:** That the skills run for at least one full round without crashes, freezing, or errors in the content delivery.
3.  **Educational Quality:** The content delivered by the skills is fascinating, factual, and age-appropriate.

---

## 🛠️ Test Cases

### Section A: Immersive Skill Activation Testing

This section validates the voice command system for launching the three new content modules.

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C4-SK-01** | **Skill Launch: Wildlife Safari** | Command Miko: "Hola, Miko, abre «Safari de vida silvestre»". Play at least one round. | «Hola, Miko, abre «Safari de vida silvestre»» | Miko correctly recognizes the Spanish launch command and **initiates** the "Wildlife Safari" skill. | PASS if the skill launches promptly and correctly. FAIL if Miko launches the wrong skill or does not recognize the command. |
| **C4-SK-02** | **Skill Launch: Country Explorer** | Command Miko: "Hola, Miko, abre «Explorador del país»". Play at least one round. | «Hola, Miko, abre «Explorador del país»» | Miko correctly recognizes the Spanish launch command and **initiates** the "Country Explorer" skill. | PASS if the skill launches promptly and correctly. FAIL if the voice command fails or the skill does not start. |
| **C4-SK-03** | **Skill Launch: Time Traveler** | Command Miko: "Hola, Miko, abre «Viajero en el tiempo»". Play at least one round. | «Hola, Miko, abre «Viajero en el tiempo»» | Miko correctly recognizes the Spanish launch command and **initiates** the "Time Traveler" skill. | PASS if the skill launches promptly and correctly. FAIL if the skill crashes on launch. |

### Section B: Content and Stability Testing

This section ensures the quality of the immersive experience once the skills are active.

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C4-CO-01** | **Skill Stability and Flow** | During all three skill sessions, observe the content flow, ensuring the sessions run for at least one round without interruption. | The skills should run **without freezing, crashing, or unexpectedly closing**. Transitions between content segments should be smooth. | PASS if all three skills complete at least one round stably. FAIL if a skill terminates unexpectedly. |
| **C4-CO-02** | **Content Quality and Engagement** | Evaluate the information shared in each skill. Is it fascinating, factually accurate, and appropriate for the target age group? | The content (e.g., facts about countries, history, or animals) must be **accurate, clear, and delivered in an engaging** manner. | PASS if the content is high quality and engaging. FAIL if the information is confusing or contains obvious errors. |

### Section C: Feedback Submission (Usability)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C4-US-01** | **Feedback Form Submission** | Successfully fill out and submit the feedback form for the three immersive experiences. | N/A | The form is **accessible**, easy to complete, and the submission is successful. | PASS if form submission is completed. |

---

## Cycle 5: New Skill Validation and Regression Testing (Spanish)

## 🎯 Testing Objectives

This cycle tests a mixed set of activities, including the validation of two new content skills and a crucial **regression test** on previously updated skills to ensure that recent code changes have not introduced new defects (bugs).

The testing areas are:
1.  **New Skill Activation & Functionality (Riddles):** Validate the launch and in-skill command processing for the "Riddles" game.
2.  **Knowledge Retrieval (Calendar Events):** Test Miko’s accuracy in retrieving factual data related to dates and global events.
3.  **Regression Testing (Explorers):** Verify that the updated "Space Explorer" and "Ocean Explorer" skills (from Cycle 2) still function correctly and show improvement in interaction quality.

---

## 🛠️ Test Cases

### Section A: Riddles Game Validation (Activity 1 - Part A)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C5-RG-01** | **Skill Launch Reliability** | Command Miko: “Hey Miko, Adivinanzas abiertas” or “Hey Miko, Acertijos abiertos”. | “Hey Miko, Adivinanzas abiertas” | Miko **correctly recognizes** either Spanish command and **initiates** the Riddles skill promptly. | PASS if the skill starts successfully using both command variations. FAIL if Miko fails to recognize the command. |
| **C5-RG-02** | **In-Skill Command Processing: Repeat** | While in the Riddles skill, use the command “Repetir”. | “Repetir” | Miko Mini **re-reads the current riddle** without exiting the skill or starting a new one. | PASS if the current riddle is repeated. FAIL if Miko misunderstands the command. |
| **C5-RG-03** | **In-Skill Command Processing: Next** | While in the Riddles skill, use the command “Próximo”. | “Próximo” | Miko Mini **advances to the next riddle** seamlessly. | PASS if the next riddle loads quickly. FAIL if the command causes a delay or error. |
| **C5-RG-04** | **In-Skill Command Processing: Hint** | While in the Riddles skill, use the command “Hola, Miko, dame una pista.” | “Hola, Miko, dame una pista.” | Miko Mini **provides a hint** related to the current riddle, aiding the child in solving it. | PASS if a relevant hint is provided. FAIL if Miko replies with a generic phrase or no hint. |
| **C5-RG-05** | **In-Skill Command Processing: Exit** | While in the Riddles skill, use the command “salida”. | “salida” | Miko Mini **exits the skill** and returns to the main conversational mode. | PASS if the skill closes correctly. FAIL if the command is ignored or causes a crash. |
| **C5-US-01** | **Feedback Form (Section 1) Submission** | Complete and submit **Section 1 (Riddles)** of the designated feedback form. | N/A | The section is accessible and submission is successful. | PASS if form submission is completed. |

### Section B: Calendar Events Knowledge Retrieval (Activity 1 - Part B)

| Test Case ID | Test Item | Test Steps | Example Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C5-CE-01** | **Event Date Retrieval** | Ask Miko about the date of a specific holiday. | “¿Cuándo se celebra la Navidad?” | Miko Mini provides the **correct date** or timeframe for the event (e.g., December 25th). | PASS if the date is factually correct. FAIL if the date is wrong or Miko cannot answer. |
| **C5-CE-02** | **Event Context Retrieval** | Ask Miko about the meaning or context of a global event. | “Cuéntame algo sobre el Día Internacional de la Alfabetización.” | Miko Mini provides a **relevant and concise explanation** of the event's significance. | PASS if the context is accurate and appropriate. FAIL if the answer is irrelevant or confusing. |
| **C5-CE-03** | **Multifaceted Event Retrieval** | Ask a question combining the date and meaning of an event. | "¿Qué significa el Día Mundial de los Animales y cuándo se celebra?” | Miko Mini addresses **both parts of the query** (meaning and date) in its response. | PASS

---

## Cycle 6: Quizzes, Music, and Dance Functionality Testing (Spanish)

## 🎯 Testing Objectives

This cycle focuses on validating the functionality, reliability, and command processing for the **Quiz** and the newly released **Music & Dance** features.

The key testing areas are:
1.  **Quiz Activation & Stability:** Validate the launch commands for the three main quiz categories and the in-quiz control commands.
2.  **Music Playback & Command:** Test Miko's ability to initiate random and specific song playback, and manage music flow using voice commands.
3.  **Dance Activation & Specificity:** Validate Miko’s ability to initiate dance mode and respond to specific song/dance requests.

---

## 🛠️ Test Cases

### Section A: Quizzes Functionality Testing (Activity 1)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C6-QZ-01** | **Math Quiz Launch** | Command Miko: “Hey Miko, Empecemos el cuestionario de matemáticas”. Play at least one round. | “Hey Miko, Empecemos el cuestionario de matemáticas” | The Math Quiz launches correctly, and the questions are delivered clearly in Spanish. | PASS if launch is correct and questions are clear. FAIL if wrong quiz starts or commands fail. |
| **C6-QZ-02** | **General Knowledge Quiz Launch** | Command Miko: “Hey Miko, Empecemos el cuestionario”. Play at least one round. | “Hey Miko, Empecemos el cuestionario” | The General Knowledge Quiz launches correctly, and the questions are varied and appropriate. | PASS if launch is correct and content is satisfactory. FAIL if launch fails or content is buggy. |
| **C6-QZ-03** | **Animals Quiz Launch** | Command Miko: “Hey Miko, Empecemos el cuestionario sobre animales”. Play at least one round. | “Hey Miko, Empecemos el cuestionario sobre animales” | The Animals Quiz launches correctly, and the questions are factually accurate. | PASS if launch is correct and content is accurate. FAIL if content is incorrect or confusing. |
| **C6-QZ-04** | **In-Quiz Command: Repeat** | During any quiz, use the command: “Repetir”. | “Repetir” | Miko Mini **re-reads the last question** without exiting or advancing the quiz. | PASS if the question is repeated accurately. FAIL if Miko exits or moves on. |
| **C6-QZ-05** | **In-Quiz Command: Exit** | During any quiz, use the command: “Salida”. | “Salida” | Miko Mini **exits the quiz skill** and returns to the main conversational mode. | PASS if the skill closes correctly and promptly. FAIL if the command is ignored or causes a crash. |
| **C6-US-01** | **Feedback Form Submission (Quizzes)** | Complete and submit the feedback form for the quiz activity. | N/A | The form is accessible and submission is successful. | PASS if form submission is completed. |

### Section B: Music Playback Functionality (Activity 2 - Part A)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C6-MP-01** | **General Music Launch** | Command Miko: “Hey Miko, Canta una canción” or “Hey Miko, Tocar una canción”. Repeat 3-4 times. | “Hey Miko, Canta una canción” | Miko **launches the music player** and plays a song. The song should be different on subsequent attempts (demonstrating randomness). | PASS if music starts, and a variety of songs is played. FAIL if music fails to start or the same song plays every time. |
| **C6-MP-02** | **Specific Song Request** | Command Miko: “Hey Miko, Reproduce la canción [nombre de la canción]” using one of the nine listed rhymes. | "Hey Miko, Reproduce la canción El viejo MacDonald" | Miko **recognizes the specific song title** and plays the requested song. | PASS if the correct song is played. FAIL if Miko plays a different song or cannot find it. |
| **C6-MP-03** | **In-Music Command: Repeat** | While a song is playing, use the command: “Repetir”. | “Repetir” | Miko Mini **restarts the current song** from the beginning. | PASS if the song repeats. FAIL if Miko misunderstands or changes songs. |
| **C6-MP-04** | **In-Music Command: Next** | While a song is playing, use the command: “Próxima canción”. | “Próxima canción” | Miko Mini **skips to the next song** in the playlist/sequence. | PASS if the next song starts quickly. FAIL if the command is ignored. |
| **C6-MP-05** | **In-Music Command: Exit** | While a song is playing, use the command: “Salida”. | “Salida” | Miko Mini **stops the music** and returns to the main conversational mode. | PASS if music stops and Miko returns to main mode. FAIL if music continues playing. |
| **C6-US-02** | **Feedback Form (Section 1) Submission (Music)** | Complete and submit **Section 1 (Music)** of the designated feedback form. | N/A | The section is accessible and submission is successful. | PASS if form submission is completed. |

### Section C: Dance Functionality Testing (Activity 2 - Part B)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C6-DN-01** | **General Dance Activation** | Command Miko: “Hey Miko, Bailemos”. | “Hey Miko, Bailemos” | Miko **initiates a dance routine** to a song and performs physical movements. | PASS if Miko dances to an appropriate song. FAIL if Miko plays music without dancing. |
| **C6-DN-02** | **Specific Dance Request** | Command Miko: “Hey Miko, [nombre de la canción/baile]” using one of the listed dance names (e.g., Baile Tutting, Skippy Dance). | “Hey Miko, Canción de animalitos” / “Hey Miko, Baile Tutting” | Miko **recognizes the specific dance** title and performs the corresponding routine. | PASS if the correct dance is performed. FAIL if Miko performs a random dance or ignores the request. |
| **C6-DN-03** | **In-Dance Command: Repeat** | While Miko is dancing, use the command: “Repetir”. | “Repetir” | Miko Mini **restarts the current dance routine/song** from the beginning. | PASS if the dance repeats. FAIL if the command is misunderstood. |
| **C6-DN-04** | **In-Dance Command: Next** | While Miko is dancing, use the command: “Próxima canción”. | “Próxima canción” | Miko Mini **skips to the next dance/song** in the sequence. | PASS if the next dance starts quickly. FAIL if the command is ignored. |
| **C6-DN-05** | **In-Dance Command: Exit** | While Miko is dancing, use the command: “Salida”. | “Salida” | Miko Mini **stops the dance and music** and returns to the main conversational mode. | PASS if the routine stops and Miko returns to main mode. FAIL if music/dance continues. |
| **C6-US-03** | **Feedback Form (Section 2) Submission (Dance)** | Complete and submit **Section 2 (Dance)** of the designated feedback form. | N/A | The section is accessible and submission is successful. | PASS if form submission is completed. |
