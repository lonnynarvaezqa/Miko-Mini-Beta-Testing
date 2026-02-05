# Miko Mini Beta Program: Test Cases Log

## Introduction

This log serves as the official documentation for all **Quality Assurance (QA) test cases** executed during my participation in the Miko Mini Beta Program. The testing activities are directly derived from the weekly challenges and objectives provided by the Miko Beta Team via Slack.

The primary focus of these tests is to validate Miko Mini's core functionality, with a strong emphasis on **Artificial Intelligence (AI) interactions**, **voice recognition**, **multilingual command processing**, and **usability**.

All cycles are documented sequentially below, including the test objectives, detailed steps, expected results, and measurable criteria for success.

---

## Cycle 0: Initial Setup, Charging Protocol, and Language Activation

##  Testing Objectives

This cycle validates the fundamental hardware setup and configuration steps, which must be successfully completed before any functional or AI testing (Cycle 1 and beyond) can commence.

The primary objectives were to:
1.  Verify the correct **device charging protocol**.
2.  Ensure successful **software update** installation.
3.  Confirm **Spanish language activation** for all subsequent testing.

---

##  Test Cases

### Section A: Hardware and Charging Protocol Validation

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C0-HW-01** | **Correct Charging Protocol** | Attempt to charge the Miko Mini while it is **powered OFF**. | The device must **not charge** when powered off, validating the specific protocol communicated by the Miko Team. | PASS if the device does not charge when OFF. FAIL if the device charges unexpectedly. |
| **C0-HW-02** | **Charge Indicator Check** | Turn Miko ON, then connect the charger. Leave plugged in overnight. | The device must **maintain or increase** its battery charge. | PASS if the charge is maintained/increased. FAIL if the battery status shows a drain or zero charge. |

### Section B: Language Localization and Software Update

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **C0-SW-01** | **Update Confirmation** | Verify Wi-Fi connection and ensure the remote Spanish update is pushed and downloaded. | Miko Mini must successfully complete the **latest software update** without freezing or crashing. | PASS if the update completes successfully. FAIL if the device hangs during the update process. |
| **C0-SW-02** | **Language Default Check** | After the remote update, prompt Miko with a simple question. | Miko Mini should **automatically respond in Spanish** (the target language). | PASS if Spanish is the default language. FAIL if the device remains in English or another language. |
| **C0-SW-03** | **Manual Language Activation (Troubleshooting)** | If C0-SW-02 fails, command Miko: **"Hey Miko, can you speak in Spanish?"** | Miko must successfully and permanently switch to **Spanish** and begin responding fully in the target language. | PASS if the language switches fully and remains. FAIL if the switch is temporary or limited. |

---

## Cycle 1: Voice Recognition and Multilingual Command Testing
##  Testing Objectives

This cycle's primary objective is to evaluate Miko Mini's **voice detection, keyword recognition, and language switching capabilities** across different users (child/parent) and accents (natural, non-standard English/Spanish).

The test specifically targets Miko’s ability to reliably:
1.  **Wake Up:** Recognize the "Hey Miko" wake word from different speakers (child and adult) under various acoustic conditions (natural accent, short pauses).
2.  **Process Multilingual Input:** Accept a command that seamlessly switches from an English trigger ("Hey Miko") to a Spanish request (`¿cuál es...?`).
3.  **Ensure Appropriate Response (Secondary):** Confirm that Miko attempts to process the command and responds, even if the answer is not yet fully implemented in Spanish.

---

##  Test Cases

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

##  Testing Objectives

The goal of this cycle is to rigorously test Miko Mini’s performance in **Spanish** regarding:
1.  **Conversational Accuracy (Activity 1):** Evaluate Miko's ability to understand a diverse set of complex, factual, and abstract questions, and provide appropriate, age-relevant answers.
2.  **Skill Launch Reliability (Activity 2):** Validate that Miko can correctly interpret voice commands to launch specific pre-installed skills ("Explorador espacial" and "Explorador oceánico").
3.  **Content Integrity:** Ensure the launched skills are fully functional and engaging throughout the experience.

---

##  Test Cases

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

##  Testing Objectives

This cycle aims to test a specific, localized game experience to evaluate **engagement, clarity of instructions, and the quality of localized responses** in Mexican Spanish.

Specifically, we are validating:
1.  **Skill Launch and Comprehension:** Miko's ability to launch the game via voice command and the child's understanding of the game mechanics.
2.  **Gameplay Effectiveness:** The accuracy of Miko's logic and guessing capability during the game.
3.  **Localization Quality:** The naturalness and appropriateness of Miko's language and responses in Mexican Spanish.
4.  **Engagement:** The child's overall enjoyment and level of interaction with the game.

---

##  Test Cases

### Section A: Game Launch and Comprehension Testing (Activity 1)

| Test Case ID | Test Item | Test Steps | Example Command | Expected Result | Pass/Fail Criteria |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **C3-GL-01** | **Game Skill Activation** | Command Miko: "Hey Miko, Abrir lector de mentes" (Open Mind Reader). | N/A | Miko **correctly recognizes** the command and **launches** the "Mind Reader" game skill. | PASS if the game starts promptly. FAIL if Miko launches the wrong skill or does not recognize the command. |
| **C3-GL-02** | **Child Comprehension** | Observe the child during the first round of the game. Do they understand the rules (e.g., answering Miko's questions correctly)? | N/A | The child is able to **follow Miko's instructions** and engage with the game without extensive parent intervention. | PASS if the child shows understanding after the first round. FAIL if instructions are confusing or unclear. |

### Section B: Gameplay and Localization Quality Testing (Activity 1)

This section focuses on the performance and linguistic quality of the game over at least four rounds.

This section focuses on the performance and linguistic quality of the game over at least four rounds.

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|--------------|-----------|------------|----------------|--------------------|
| C3-LQ-01 | Localization/Language Naturalness | During the 4+ rounds, observe Miko's questions and dialogue. Does the language sound natural and appropriate for Mexican Spanish? | Miko's dialogue should feel colloquial and avoid overly formal or incorrect Spanish phrases. | PASS if the language feels natural and is free of translation errors. FAIL if dialogue is awkward or grammatically incorrect. |
| C3-LQ-02 | Gameplay Logic (Guessing Accuracy) | Play a minimum of 4 rounds. Track the number of times Miko successfully guesses what the child is thinking. | The guessing mechanism should feel plausible, even if Miko doesn't guess every time. Miko should use a logical set of questions. | PASS if Miko's questions are relevant and the game proceeds logically. FAIL if Miko asks repetitive or irrelevant questions. |
| C3-LQ-03 | Child Engagement | Observe the child’s level of enjoyment and interaction throughout the game sessions. | The child should be engaged, smiling, and motivated to play subsequent rounds. | PASS if the game holds the child’s attention. FAIL if the child quickly loses interest due to game mechanics or boring dialogue. |
| C3-LQ-04 | Game Stability | Ensure the game skill runs for the minimum 4 rounds without crashing or unexpectedly exiting to the main interface. | The game runs smoothly, and transitions between rounds are successful. | PASS if the game is stable. FAIL if the application hangs or crashes. |

---

### Section C: Feedback Submission (Usability)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|--------------|-----------|------------|----------------|--------------------|
| C3-US-01 | Feedback Form Submission | Successfully fill out and submit the Mind Reader Feedback Form. | The form is accessible, easy to complete, and the submission is successful. | PASS if form submission is completed. |


---

## Cycle 4: Immersive Skill Activation and Content Integrity (Delayed Release)

##  Testing Objectives

This cycle tests the reliability of Miko Mini's **voice command recognition** to launch new, immersive, and narrative-driven content skills. The primary focus is on ensuring the skills launch correctly and deliver **high-quality, complete, and engaging educational content**.

Specifically, we are validating:
1.  **Voice Launch Reliability:** Miko's ability to interpret and execute the specific voice commands for the three new skills.
2.  **Content Integrity and Flow:** That the skills run for at least one full round without crashes, freezing, or errors in the content delivery.
3.  **Educational Quality:** The content delivered by the skills is fascinating, factual, and age-appropriate.

---

##  Test Cases

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

##  Testing Objectives

This cycle tests a mixed set of activities, including the validation of two new content skills and a crucial **regression test** on previously updated skills to ensure that recent code changes have not introduced new defects (bugs).

The testing areas are:
1.  **New Skill Activation & Functionality (Riddles):** Validate the launch and in-skill command processing for the "Riddles" game.
2.  **Knowledge Retrieval (Calendar Events):** Test Miko’s accuracy in retrieving factual data related to dates and global events.
3.  **Regression Testing (Explorers):** Verify that the updated "Space Explorer" and "Ocean Explorer" skills (from Cycle 2) still function correctly and show improvement in interaction quality.

---

##  Test Cases

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

##  Testing Objectives

This cycle focuses on validating the functionality, reliability, and command processing for the **Quiz** and the newly released **Music & Dance** features.

The key testing areas are:
1.  **Quiz Activation & Stability:** Validate the launch commands for the three main quiz categories and the in-quiz control commands.
2.  **Music Playback & Command:** Test Miko's ability to initiate random and specific song playback, and manage music flow using voice commands.
3.  **Dance Activation & Specificity:** Validate Miko’s ability to initiate dance mode and respond to specific song/dance requests.

---

##  Test Cases

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

# Cycle 7: Story Time & Child Interaction Experience Testing (English)

## Testing Objectives
This cycle focuses on validating the **Story Time functionality** and capturing **real child–Miko interaction experiences** across multiple skills, including storytelling, creativity, exploration, quizzes, music, and dance.

### Key Testing Areas
- Story Time activation and story recognition
- In-story voice command handling
- Child engagement across multiple Miko skills
- Feedback form accessibility and submission

---

## Section A: Story Time Functionality Testing (Activity 1)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|--------------------------|-----------------|-------------------|
| C7-ST-01 | General Story Time Launch | Command Miko to start Story Time using a general command. | “Hey Miko, Cuéntame una historia” | Story Time launches successfully and Miko starts or prompts a story. | PASS if Story Time launches correctly. FAIL if skill does not open. |
| C7-ST-02 | Alternate Story Time Launch | Launch Story Time using an alternate supported command. | “Hey Miko, Hora del cuento abierta” | Story Time opens successfully using the alternate phrase. | PASS if skill launches correctly. FAIL if command is not recognized. |
| C7-ST-03 | Specific Story Launch: Hansel and Gretel | Request the story by name and listen for at least 1–2 minutes. | “Hey Miko, Hansel y Gretel” | Correct story plays with clear narration. | PASS if correct story plays. FAIL if wrong story starts. |
| C7-ST-04 | Specific Story Launch: The Hare and the Tortoise | Request the story by name and verify narration accuracy. | “Hey Miko, La liebre y la tortuga” | The correct story launches with accurate narration. | PASS if story is correct. FAIL if incorrect content plays. |
| C7-ST-05 | Specific Story Launch: Jack and the Beanstalk | Request the story by name. | “Hey Miko, Juan y las habichuelas mágicas” | Miko recognizes and plays the requested story. | PASS if correct story plays. FAIL if recognition fails. |
| C7-ST-06 | Specific Story Launch: Peter and the Wolf | Launch the story and verify audio clarity. | “Hey Miko, Pedro y el lobo” | Story plays smoothly with clear audio. | PASS if narration is clear. FAIL if audio or content issues occur. |
| C7-ST-07 | Specific Story Launch: The Fox and the Stork | Request the story by name. | “Hey Miko, El zorro y la cigüeña” | Correct story launches and flows properly. | PASS if correct story plays. FAIL if wrong content appears. |
| C7-ST-08 | Specific Story Launch: The Lazy Donkey | Request the story by name. | “Hey Miko, El burrito flojo” | Miko plays the correct story without interruption. | PASS if correct story plays. FAIL if story fails to load. |
| C7-ST-09 | In-Story Command: Next | While a story is playing, say the navigation command. | “Siguiente” | Miko advances to the next story segment. | PASS if story advances correctly. FAIL if command is ignored. |
| C7-ST-10 | In-Story Command: Repeat | While a story is playing, issue the repeat command. | “Repetir” | Miko repeats the last story segment accurately. | PASS if repetition works. FAIL if story resets incorrectly. |
| C7-ST-11 | In-Story Command: Exit | While a story is playing, exit Story Time. | “Salir” | Miko exits Story Time and returns to main mode. | PASS if skill exits cleanly. FAIL if audio continues. |
| C7-US-01 | Feedback Form Submission (Story Time) | Complete and submit the Story Time feedback form. | N/A | Feedback form is accessible and submission succeeds. | PASS if form is submitted successfully. |

---

## Section B: Child Interaction Video Recording (Activity 2)

### Objective
Capture authentic videos of a child interacting naturally with Miko across multiple skills to demonstrate real family usage.

### Required Coverage
- At least **2–3 different Miko features**
- Ideally includes:
  - StoryMaker
  - Dance Master
  - At least one Explorer skill or a Quiz

---

### Test Cases

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C7-VID-01 | StoryMaker Interaction Recording | Record a video of the child using StoryMaker to create a story. | Child engages with Miko and responds to prompts naturally. | PASS if interaction is visible and audible. |
| C7-VID-02 | Dance Master Interaction Recording | Record the child activating Dance Master and reacting to Miko’s movements. | Miko performs a dance and child interaction is clear. | PASS if dance and interaction are visible. |
| C7-VID-03 | Explorer Skill Interaction Recording | Record the child using one Explorer skill (Space, Ocean, Countries, Time Travel, or Wildlife Safari). | Miko responds correctly to explorer prompts. | PASS if skill launches and interaction is shown. |
| C7-VID-04 | Quiz Interaction Recording | Record the child playing a quiz (Math, General Knowledge, or Animals). | Child answers questions and Miko responds correctly. | PASS if quiz interaction is clear. |
| C7-VID-05 | ODQA Questions Interaction | Record the child asking at least five fun questions to Miko/Neko. | Miko answers clearly and engagingly. | PASS if answers are appropriate. |
| C7-VID-06 | Riddles or Mind Reader Game Recording | Record the child interacting with riddles or the Mind Reader game. | Miko responds correctly and maintains engagement. | PASS if gameplay is functional and visible. |

---
# Cycle 8: Advanced Recommendation (Reco) Flow Testing

## Testing Objectives
This cycle focuses on validating **Miko’s advanced recommendation (Reco) flows**, ensuring that Miko correctly suggests next activities based on user interaction and responds appropriately to affirmative or negative confirmations.

### Key Testing Areas
- Recommendation trigger accuracy
- Voice confirmation handling (“Yes” / “No”)
- Skill launch reliability after recommendation
- Context-aware suggestions at different interaction stages

---

## Section A: Recommendation Flow Testing – “Let’s Play” (Flow 1)

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|--------------------------|-----------------|-------------------|
| C8-RC-01 | Recommendation Trigger via “Let’s Play” | Ask the child to say the command to Miko. | “Hey Miko, vamos a jugar” | Miko responds by suggesting a playable activity or skill. | PASS if Miko suggests a valid activity. FAIL if no suggestion is given. |
| C8-RC-02 | Accept Recommendation | After Miko suggests an activity, respond with confirmation. | “Sí” | Miko opens the suggested skill successfully. | PASS if suggested skill opens correctly. FAIL if nothing happens or wrong skill opens. |
| C8-RC-03 | Play Suggested Skill | Play at least one round of the opened activity. | N/A | The skill functions correctly and is playable. | PASS if gameplay works without issues. |
| C8-RC-04 | Reject Recommendation | Repeat the command and reject the suggestion. | “Hey Miko, vamos a jugar” → “No” | Miko does not open the suggested activity and remains idle or offers an alternative response. | PASS if skill does not open. FAIL if skill opens despite rejection. |

---

## Section B: Recommendation After Multiple Questions (Flow 2)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C8-RC-05 | Ask Random Questions | Ask Miko five random, unrelated questions. | Miko answers all questions appropriately. | PASS if Miko answers all questions. FAIL if responses stop prematurely. |
| C8-RC-06 | Recommendation Trigger After Questions | Observe Miko’s behavior after the fifth question. | Miko suggests another skill or activity. | PASS if a recommendation is triggered. FAIL if no suggestion appears. |
| C8-RC-07 | Accept Post-Question Recommendation | Respond “Yes” to the suggested activity. | Miko launches the recommended skill successfully. | PASS if skill opens correctly. FAIL if launch fails. |

---

## Section C: End-of-Skill Recommendation Flow (Flow 3)

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C8-RC-08 | Complete Any Skill | Open any Miko skill and play it until completion. | Skill completes normally without interruption. | PASS if skill completes successfully. |
| C8-RC-09 | Recommendation at Skill End | Observe Miko’s behavior after the skill finishes. | Miko suggests another relevant skill or activity. | PASS if recommendation is given. FAIL if interaction ends abruptly. |
| C8-RC-10 | Accept End-of-Skill Recommendation | Respond “Yes” to the suggested activity. | Miko opens the recommended skill smoothly. | PASS if skill launches correctly. FAIL if recommendation fails to launch. |

---

## Section D: User Feedback Submission

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C8-US-01 | Recommendation Flow Feedback Submission | Complete and submit the feedback form for Reco testing. | Feedback form is accessible and submission is su

# Cycle 9: Santa Time Skill Testing

## Testing Objectives
This cycle focuses on validating the **Santa Time seasonal skill**, where Miko transforms into Santa Claus and shares Christmas-related stories, traditions, and fun holiday facts. The goal is to evaluate **skill activation, conversational flow, child engagement, and overall experience quality**.

### Key Testing Areas
- Skill launch reliability using supported voice commands
- Content relevance and holiday theme accuracy
- Conversational flow and child engagement
- Overall user experience and feedback collection

---

## Section A: Santa Time Skill Launch & Interaction

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|--------------------------|-----------------|-------------------|
| C9-ST-01 | Santa Time Skill Launch (Primary Command) | Ask the child to open the Santa Time skill using the primary command. | “Hey Miko, abre Santa Time” | Santa Time skill launches successfully and Miko enters Santa persona. | PASS if skill opens correctly. FAIL if skill does not launch. |
| C9-ST-02 | Santa Time Skill Launch (Alternate Command) | Launch the skill using an alternate supported phrase. | “Hey Miko, abrir Santa Time” | Santa Time skill opens correctly using the alternate command. | PASS if skill launches. FAIL if command is not recognized. |
| C9-ST-03 | Santa Persona Confirmation | Observe Miko’s behavior after the skill launches. | N/A | Miko speaks as Santa and references Christmas or holiday themes. | PASS if Santa persona is clear. FAIL if persona is not activated. |
| C9-ST-04 | Holiday Content Validation | Listen to Miko’s responses about Christmas traditions and fun facts. | N/A | Content is age-appropriate, festive, and holiday-themed. | PASS if content is relevant and engaging. FAIL if content is off-topic. |
| C9-ST-05 | Child Engagement Observation | Allow the child to interact naturally with Santa Miko. | N/A | Child remains engaged and Miko responds appropriately. | PASS if interaction feels natural and engaging. |
| C9-ST-06 | Exit Santa Time Skill | Ask Miko to exit the Santa Time skill. | “Salir” | Miko exits Santa Time and returns to main conversational mode. | PASS if skill exits cleanly. FAIL if Santa persona continues. |

---

## Section B: User Feedback Submission

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C9-US-01 | Santa Time Feedback Submission | Complete and submit the Santa Time feedback form. | Feedback form is accessible and submission is successful. | PASS if form is submitted successfully. |

---

## Notes & Observations
- Verify that Santa-themed responses remain consistent throughout the session.
- Observe child reactions to festive content (excitement, curiosity, laughter).
- Note any repetition, content gaps, or unexpected responses.
- Assess whether the skill feels special and seasonal.

# Cycle 10: Expanded Story Time Content Testing

## Testing Objectives
This cycle focuses on validating the **newly added Story Time content**, which includes approximately **50 new stories** across multiple genres and themes. The objective is to assess **story discovery, narration quality, command handling, and overall child experience**.

### Key Testing Areas
- Story Time skill launch reliability
- Specific story recognition and selection
- In-story navigation command handling
- Content variety, quality, and engagement
- Overall user experience feedback

---

## Section A: Story Time Skill Launch

| Test Case ID | Test Item | Test Steps | Launch Command (Spanish) | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|--------------------------|-----------------|-------------------|
| C10-ST-01 | Story Time Launch (Primary Command) | Ask the child to open Story Time using the primary command. | “Hola, Miko, cuéntame un cuento” | Story Time skill launches successfully and prompts story selection or starts a story. | PASS if Story Time launches correctly. FAIL if skill does not open. |
| C10-ST-02 | Story Time Launch (Alternate Command) | Launch Story Time using an alternate supported command. | “Hola, Miko, abre Story Time” | Story Time opens successfully using the alternate command. | PASS if skill launches correctly. FAIL if command is not recognized. |

---

## Section B: Specific Story Selection & Content Validation

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C10-ST-03 | Specific Story Launch by Name | Request a specific story by saying its title. | Miko recognizes the story name and starts narration. | PASS if correct story plays. FAIL if wrong story or no response. |
| C10-ST-04 | Story Genre & Theme Validation | Listen to the story content for at least 1–2 minutes. | Story aligns with an identifiable genre or theme and is age-appropriate. | PASS if content is appropriate and coherent. FAIL if content feels incorrect or unsuitable. |
| C10-ST-05 | Narration Quality Check | Observe narration clarity, pacing, and audio quality. | Narration is clear, engaging, and easy to understand. | PASS if narration quality is good. FAIL if audio issues occur. |

---

## Section C: In-Story Voice Command Handling

| Test Case ID | Test Item | Test Steps | Voice Command | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|--------------|-----------------|-------------------|
| C10-ST-06 | In-Story Command: Next | While a story is playing, issue the next command. | “Siguiente” | Miko advances to the next story segment smoothly. | PASS if story advances correctly. FAIL if command is ignored. |
| C10-ST-07 | In-Story Command: Repeat | While a story is playing, issue the repeat command. | “Repetir” | Miko repeats the last story segment accurately. | PASS if repetition works. FAIL if incorrect segment plays. |
| C10-ST-08 | In-Story Command: Exit | While a story is playing, exit Story Time. | “Salir” | Miko exits Story Time and returns to main conversational mode. | PASS if skill exits cleanly. FAIL if audio continues playing. |

---

## Section D: Child Engagement & Experience Observation

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C10-ST-09 | Child Engagement Observation | Allow the child to listen and interact naturally with multiple stories. | Child shows interest and Miko responds appropriately. | PASS if engagement is observed. |
| C10-ST-10 | Story Variety Exploration | Test multiple stories from different genres or themes. | Stories feel diverse and not repetitive. | PASS if variety is noticeable. FAIL if stories feel duplicated. |

---

## Notes & Observations
- Evaluate how easy it is to discover and launch specific stories.
- Observe if story recommendations feel relevant and varied.
- Note any repetition, missing stories, or recognition failures.
- Assess overall satisfaction with the expanded Story Time library.

# Cycle 11: Final App Exploration – Experience & Usability Validation

## Testing Objectives
This cycle focuses on validating the **final version of the Miko mobile application**, ensuring that the overall experience is **stable, intuitive, and ready for release**. The goal is to evaluate the **end-to-end setup flow**, navigation clarity, and usability across both **Child Zone** and **Parent Section**.

### Key Testing Areas
- App installation and reinstallation flow
- Login reliability using existing test credentials
- Onboarding and setup experience
- Child Zone navigation and content accessibility
- Parent Section usability, controls, and navigation flow
- Overall app stability and intuitiveness

---

## Section A: App Reinstallation & Login Flow

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C11-APP-01 | App Uninstallation | Uninstall the current Miko app from the device. | App is completely removed from the device. | PASS if app is fully uninstalled. FAIL if remnants remain. |
| C11-APP-02 | App Reinstallation | Download and install the latest Miko app version from the App Store or Google Play Store. | App installs successfully without errors. | PASS if installation completes successfully. FAIL if installation fails. |
| C11-APP-03 | App Login with Existing Account | Log in using the same email address used during previous testing. | Login succeeds and user is authenticated correctly. | PASS if login works correctly. FAIL if login fails or errors appear. |

---

## Section B: Onboarding & Setup Flow

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C11-APP-04 | Initial App Setup | Follow the full onboarding and setup process after login. | Setup completes smoothly with clear instructions. | PASS if setup is intuitive and completes successfully. FAIL if setup is confusing or broken. |
| C11-APP-05 | Setup Flow Clarity | Observe instructions, prompts, and transitions during setup. | Instructions are clear and easy to follow. | PASS if flow is understandable. FAIL if steps are unclear or misleading. |

---

## Section C: Child Zone Exploration

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C11-APP-06 | Child Zone Access | Navigate to the Child Zone after setup. | Child Zone opens without delay or errors. | PASS if zone opens correctly. FAIL if access fails. |
| C11-APP-07 | Child Zone Navigation | Explore available content and menus within the Child Zone. | Navigation feels intuitive and content is easy to access. | PASS if navigation is smooth. FAIL if navigation is confusing. |
| C11-APP-08 | Child Content Accessibility | Open multiple activities or content items from the Child Zone. | Content loads correctly and functions as expected. | PASS if content opens successfully. FAIL if content fails to load. |

---

## Section D: Parent Section Exploration

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C11-APP-09 | Parent Section Access | Navigate to the Parent Section of the app. | Parent Section opens successfully. | PASS if section opens correctly. FAIL if access fails. |
| C11-APP-10 | Parental Controls Review | Explore parental controls and available settings. | Controls are easy to understand and configurable. | PASS if controls work correctly. FAIL if settings are unclear or broken. |
| C11-APP-11 | Parent Navigation Flow | Navigate through different screens within the Parent Section. | Navigation is logical and consistent. | PASS if navigation is intuitive. FAIL if flow feels disorganized. |

---

## Section E: Overall Experience & Stability

| Test Case ID | Test Item | Test Steps | Expected Result | Pass/Fail Criteria |
|-------------|----------|------------|-----------------|-------------------|
| C11-APP-12 | App Stability Check | Use the app for several minutes across different sections. | App remains stable with no crashes or freezes. | PASS if app is stable. FAIL if crashes occur. |
| C11-APP-13 | Overall Usability Assessment | Evaluate overall ease of use and user experience. | App feels polished, intuitive, and ready for release. | PASS if experience is positive and smooth. |

---

## Notes & Observations
- Note any friction points during setup or navigation.
- Observe loading times and responsiveness.
- Identify any confusing labels, flows, or missing feedback.
- Provide overall impressions of readiness and usability.

