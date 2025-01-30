**OpenAI Claims DeepSeek Plagiarized its Plagiarism Machine**

---

**Hey, everyone!** Today, we’re diving into the latest drama in the AI world—OpenAI is mad. Like, really mad. And why? Because DeepSeek, a Chinese AI company, allegedly "distilled" ChatGPT’s knowledge to build its own chatbot. But wait—didn’t OpenAI train ChatGPT on, well… all of the internet? It’s irony at its finest. Let’s break it down.

---

## **The Accusation**

So, here’s the deal: OpenAI and Microsoft claim DeepSeek copied them using a technique called **distillation**. Distillation is when a smaller AI model "learns" from a bigger AI model by asking it a ton of questions, analyzing the responses, and essentially **mimicking** how the bigger model thinks. OpenAI alleges that DeepSeek siphoned ChatGPT’s reasoning, allowing it to build a competitive LLM **at a fraction of the cost**.

Now, OpenAI hasn’t provided direct evidence, but they say Microsoft’s security team noticed **suspicious API activity**—basically, an unusual number of queries hitting ChatGPT, which may have been DeepSeek gathering data. If true, this might violate OpenAI’s Terms of Service. But let’s be honest—how enforceable is that when OpenAI itself built its empire off massive amounts of freely available (and often copyrighted) data?

---

## **How DeepSeek Actually Works**

Before we pass judgment, let’s talk about what makes DeepSeek-R1 unique. Unlike ChatGPT, which relies heavily on **Supervised Fine-Tuning (SFT)**, DeepSeek-R1 does something different—it learns **purely through Reinforcement Learning (RL)**. This means it’s not just memorizing data—it’s figuring things out on its own.

### **Humans Learn in Baby Steps—So Does DeepSeek**
Humans don’t go from zero to expert overnight. We improve **step by step**, gradually getting better over time. Whether it’s learning to walk, mastering a new language, or picking up a musical instrument, our brains rely on incremental progress. We try, fail, adjust, and try again. 

SFT, focuses on **matching a final goal**—it tells the AI exactly what the correct answer is and expects it to learn by mimicking that outcome. This is like handing a student a list of answers without teaching them how to solve the problems.

RL, on the other hand, focuses on **matching steps toward a goal**—the AI isn’t given the final answer but is instead rewarded for improving its reasoning along the way. It’s like teaching a student how to solve a problem by giving them feedback on each step of their work. This allows DeepSeek to develop reasoning skills rather than just memorizing responses.

### **Chain of Thought: Thinking Like a Human**
DeepSeek uses a technique called **Chain of Thought (CoT) prompting**, where it breaks down problems step by step, just like you would when solving a math problem. But CoT doesn’t just ask for the final answer—it demands that the model **show its work**. By explicitly outlining its reasoning process, DeepSeek can make its thought process transparent. 

This is crucial because if the model makes a mistake, it can **self-correct** and re-evaluate where it went wrong. It’s the AI equivalent of a student realizing they miscalculated a step in a math problem and going back to fix it. This iterative reasoning is one of the reasons why DeepSeek performs so well on complex tasks like mathematics and coding.

### **Reinforcement Learning: The Baby Learning to Walk**
Instead of being spoon-fed correct answers, DeepSeek learns by trial and error—kind of like how a baby learns to walk. It stumbles, makes mistakes, and figures out what works best. This is why its reasoning gets sharper over time.

### **Group Relative Policy Optimization: Smarter Learning**
DeepSeek refines its learning through an algorithm called **Group Relative Policy Optimization (GRPO)**, which is just a fancy way of saying it improves itself **without needing an enormous separate AI to judge its answers**. That makes its training process **way more efficient** than OpenAI’s methods.

The **Group Relative Policy Optimization (GRPO)** equation in the image appears to be:

\[
GRPO(\theta) = \mathbb{E}_{q \in Q, o_i \in \Pi_{old}} \left[ \frac{1}{G} \sum_{i=1}^{G} \min \left( \frac{\Pi_{\theta}(o_i | q)}{\Pi_{old}(o_i | q)}, 1 + \epsilon \right) A_i \right] - \beta D_{KL} (\Pi_{\theta} || \Pi_{ref})
\]

Now, let's break this down into **5 simple parts**, explaining it like you're a teenager who loves video games:

---

### **1️⃣ The Expectation Term** \(\mathbb{E}_{q \in Q, o_i \in \Pi_{old}} \)
🔍 **What it means:**  
This just means **"on average"** over all the data we have.  

🎮 **Game Example:**  
Imagine you’re playing a game and trying to find the best way to win. You look at all the strategies you've used before and see which ones worked best. This expectation part is like averaging how well different strategies performed.

---

### **2️⃣ The Policy Likelihood Ratio** \(\frac{\Pi_{\theta}(o_i | q)}{\Pi_{old}(o_i | q)}\)
🔍 **What it means:**  
This fraction compares **the new way of doing things** (\(\Pi_{\theta}\)) with **the old way** (\(\Pi_{old}\)). It shows how different the new strategy is from the old one.

🎮 **Game Example:**  
Let’s say you used to aim for the head in a shooting game, but now you’re trying to aim for the chest. This ratio tells you **how much your new aiming style has changed compared to the old one**.

---

### **3️⃣ The Clipping Mechanism** \(\min \left( \frac{\Pi_{\theta}(o_i | q)}{\Pi_{old}(o_i | q)}, 1 + \epsilon \right) A_i \)
🔍 **What it means:**  
This prevents the AI from making **huge, reckless changes** to its strategy by limiting how much it can update at a time.

🎮 **Game Example:**  
Imagine if every time you lost a round, you completely changed your playstyle—switching from aggressive to ultra-defensive. That would be chaotic! Instead, this clipping makes sure you **only make small, smart adjustments** so you don’t mess up completely.

---

### **4️⃣ The Advantage Term** \( A_i = R_i - R_{mean} \)
🔍 **What it means:**  
This part measures how much **better or worse** an action is compared to the average.

🎮 **Game Example:**  
If your usual game score is **100 points**, but you just scored **150 points**, then you know this new strategy is working great! If you only scored **80 points**, then you should rethink your approach. This part helps the AI **learn from what works best**.

---

### **5️⃣ KL Divergence Term** \(- \beta D_{KL} (\Pi_{\theta} || \Pi_{ref})\)
🔍 **What it means:**  
This makes sure the AI doesn’t change **too much** and stays similar to what has worked before.

🎮 **Game Example:**  
Imagine you get really good at one game strategy, but suddenly try something totally random that makes no sense. This term **pulls you back** so you don’t drift too far away from what actually works.

--- 

By following these steps, **DeepSeek trains itself in a smart way without needing a big separate AI to judge it**—making it **faster and more efficient** than OpenAI’s older training methods! 🚀

### **Distillation: The Core of OpenAI’s Complaint**
And finally, the controversial part: **distillation**. DeepSeek takes what it learned and distills it into **smaller, more efficient models**—ones that can run on far less computing power. In fact, DeepSeek’s **14B model beats OpenAI’s o1-mini**, showing that distillation isn’t just copying—it’s optimizing. It’s taking knowledge and making it more efficient, accessible, and affordable.

But, of course, OpenAI sees it differently. They claim DeepSeek “stole” from them, despite the fact that distillation is a well-established AI practice. The irony? OpenAI itself has **used distillation techniques** to improve its own models.

---

## **Ethical Dilemma: Who Owns AI Knowledge?**

This whole situation raises a huge ethical question: **Who actually owns AI-generated knowledge?**

- OpenAI built ChatGPT by training it on **publicly available data**—a lot of which was copyrighted.
- DeepSeek allegedly trained its AI by using OpenAI’s AI outputs.
- But if OpenAI didn’t create its knowledge from scratch, **can it really claim ownership over it?**

At the end of the day, AI models are **only as good as their training data**—and if OpenAI’s argument is that DeepSeek copied from them, then by extension, DeepSeek copied from data that **wasn’t even OpenAI’s to begin with**.

---

## **What’s Next? AI Wars Begin**

OpenAI has made it clear they’re not going to let this slide. Insiders say they’re working on methods to **prevent distillation**, which could mean tightening API restrictions or adding noise to outputs to make copying harder. But realistically? **The AI race is global now.**

And guess what? As of right now, **DeepSeek is the #1 AI app on the Apple App Store.** That’s right—despite OpenAI’s complaints, users are voting with their downloads.

So, what do you think? Is this just another case of AI companies playing dirty while pretending they own intelligence itself? Let’s talk about it in the comments!

**Don’t forget to like, subscribe, and hit that bell. Thanks for watching the Bear Brown and Company YouTube Channel.**




