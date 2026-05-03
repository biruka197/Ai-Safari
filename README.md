Here is the complete solution for your AI Safari assignment, formatting both the Savannah Tracker Report and the open-ended questions into a clean, ready-to-use deliverable. 

***

### 🌍 Savannah Tracker Report: Precision Prompting in Maternal Health

**Introduction**
In rural maternal healthcare, generic AI advice is not just unhelpful—it is actively harmful. Suggesting out-of-reach foods or demanding immediate, costly clinic visits for minor aches erodes trust. Precision prompting forces AI to operate within the specific logistical, economic (M-Pesa), and cultural realities of Kenyan and Ugandan mothers, ensuring advice is safe, actionable, and empathetic.

---

#### **Prompt A: Nutrition Advice**
*Current version:* "Give nutrition tips for pregnant women."

* **Rewritten Prompt:** 
  > **[A/Action & Persona]** Act as a compassionate community health nutritionist in rural Uganda. 
  > **[M/Mission]** Your mission is to provide highly accessible, iron-rich dietary advice for expectant mothers to prevent anemia. 
  > **[A/Audience]** The audience is low-income pregnant women who rely on subsistence farming and local markets, where matooke provides 60% of daily calories.
  > **[I/Information]** Suggest two simple, affordable meals. Base the recommendations on local staples like matooke, groundnuts (g-nuts), and indigenous greens (like *dodo* or *nakati*). Do not mention expensive imports like salmon or kale. 
  > **[M/Mode]** Output this as a warm, encouraging SMS under 160 characters.

* **Key Improvement:** This drastically reduces hallucination risk. By explicitly banning Western imports and anchoring the data to local staples (*matooke*, *dodo*), the AI provides immediately actionable, culturally aligned advice rather than useless, generic health articles.

#### **Prompt B: Appointment Reminders**
*Current version:* "Remind users about doctor visits."

* **Rewritten Prompt:**
  > **[A/Action & Persona]** Act as a logistics-focused Community Health Worker (CHW) coordinator for AfyaTech. 
  > **[M/Mission]** Your mission is to ensure mothers do not miss their prenatal checkups due to logistical surprises. 
  > **[A/Audience]** The audience is rural Kenyan mothers, 70% of whom live >5km from the nearest clinic and rely on boda-bodas (motorcycles) for transport.
  > **[I/Information]** Draft an appointment reminder. Acknowledge the long travel time and advise them to coordinate transport a day early. Remind them to ensure their phone is charged and has M-Pesa balance for the small 150 KES clinic fee.
  > **[M/Mode]** Format as a clear, bulleted SMS message.

* **Key Improvement:** This accounts for the physical and economic constraints of the user. By pre-empting the barriers to entry (travel time and mobile money needs), the prompt turns a simple reminder into a comprehensive logistical aid.

#### **Prompt C: Emergency Triage**
*Current version:* "Tell me what to do if I feel unwell during pregnancy."

* **Rewritten Prompt:**
  > **[Persona/Mission]** You are an AfyaTech emergency triage assistant. Your mission is to provide safe, calm guidance without causing unnecessary panic or financial strain.
  > **[Verifier Pattern]** When a pregnant user reports feeling unwell, **do not immediately generate medical advice.** First, you must ask exactly 3 clarifying questions: 1. What are your exact symptoms? 2. Is there any bleeding or sharp pain? 3. How far are you from your local Community Health Worker? Wait for the user to answer.
  > **[Chain-of-Thought]** Once they reply, reason through the steps: First, determine if the symptoms match WHO danger signs. Second, factor in their distance to help. Third, formulate a specific next step (e.g., resting with fluids vs. calling the CHW immediately). 
  > **[Mode]** Provide the final advice clearly and calmly.

* **Key Improvement:** Applying the Verifier pattern prevents the AI from defaulting to "go to the hospital immediately" for minor issues like morning sickness, which saves the user from undertaking expensive, unnecessary >5km trips to a clinic.

---

**Reflection**
This exercise fundamentally shifts the view of AI in healthcare from a "knowledge retrieval tool" to an "environmental reasoning engine." A medically accurate fact is useless if it is economically or geographically impossible for the user to execute. By strictly defining the audience's constraints—such as M-Pesa reliance and clinic distances—we build AI that acts as a true companion rather than a disconnected textbook, ultimately bridging the gap between global medical standards and local survival.

***

### 🔍 Open-Ended: Reason Beyond the Thicket

**1. The MAP Framework & Local Food Systems**
*   **The Failure:** The AI failed because it lacked a defined **Audience** and **Persona**, operating on Western-centric training data where "kale" is the default leafy green. 
*   **The Redesign:** *Mission:* Provide affordable dietary advice. *Audience:* Mothers in Kakamega County relying on local agriculture. *Persona:* A locally-trained Kenyan nutritionist.
*   **Prompt:** "Act as a nutritionist in Kakamega County. Your audience is local mothers. Do not recommend imported greens like curly kale. Instead, specifically recommend locally abundant, iron-rich indigenous vegetables like *mrenda*, *kunde*, *managu*, or *mito*, and explain how to prepare them."

**2. The Verifier Pattern & Triage Advice**
*   **Application:** The Verifier Pattern forces the AI to stop generating solutions and ask diagnostic questions first.
*   **Prompt:** "When a user reports abdominal pain, do not immediately recommend visiting a doctor. First, ask 3 questions: 1. The exact location and severity of the pain. 2. How long it has been present. 3. The user's ability to afford transport. Wait for the user to answer. Only then provide next steps, factoring in their transport constraints to distinguish between an emergency and home-monitoring."

**3. Chain-of-Thought (CoT) vs. Direct Summarization**
*   **Justification:** Direct summarization creates a "copy-paste" problem, assuming a baseline of infrastructure (reliable electricity, paved roads) that may not exist. CoT forces the AI to reason through the *application* of the guidelines. For example, instead of just stating "Refrigerate vaccines at 2-8°C" (Direct), CoT prompts the AI to reason: *1. Identify standard (2-8°C) -> 2. Analyze local constraint (power outages) -> 3. Determine adaptation (use solar-powered fridges or conditioned ice packs).* This creates practical, life-saving logistics.

**4. The OCEAN Framework & Catching Outdated Statistics**
*   **Application:** AI naturally hallucinates or pulls outdated numbers based on its training cutoff. You catch this using the **Context** and **Nuances (Constraints)** pillars of OCEAN.
*   **Prompt Constraint:** *"Context: The year is 2026. Nuance: You must only use data from 2025 or 2026. For every statistic provided, state the year in parentheses. If you do not have exact data for 2025/2026, you must state 'Current data unavailable' rather than guessing or using pre-2024 data."* This forces the AI to verify the timestamp of the 1.8 figure and reject it.
