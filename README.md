

# **AuraMind - AI Mental Health Companion**  
**Project Overview**:  
A therapeutic chatbot that combines **journaling**, **context-aware conversation**, and **mental health support** using Gemini AI's advanced capabilities.

## **Key Features**  

### **1. Personalized Journaling System**  
- **ChromaDB Vector Database**: Stores journal entries with semantic search  
- **Smart Chunking**: Splits entries into meaningful paragraphs for better context  
- **Embedding Generation**: Uses Gemini's `text-embedding-004` model  

### **2. Context-Aware Therapy Chat**  
- **Persona**: Empathetic virtual therapist ("AuraMind")  
- **RAG (Retrieval-Augmented Generation)**:  
  ```python
  def rag_chat(user_message):
      # 1. Retrieve relevant journal entries
      # 2. Augment prompt with personal context
      # 3. Generate grounded responses
  ```
- **Example Interaction**:  
  > **User**: "I'm stressed about work"  
  > **AuraMind**: "I understand. Remember how your walk by Ram Ganga river helped last time? Maybe try that again."

### **3. Response Evaluation System**  
Automatically scores AI responses on:  
- **Empathy** (1-5)  
- **Helpfulness** (1-5)  
- **Grounding in Context** (1-5)  
- **Safety** (1-5)  

```python
{
  "helpfulness": 5,
  "empathy": 4,
  "grounding": 5,
  "safety": 5,
  "reasoning": "Response correctly referenced journal entry about walks reducing stress"
}
```

### **4. Mental Health Techniques**  
- **Breathing Exercise Guide**:  
  ```python
  if "breathing exercise" in query:
      return "Try 4-7-8: Inhale 4s, hold 7s, exhale 8s"
  ```
- **Positive Reinforcement**:  
  ```python
  if user_feeling == "stressed":
      recall_positive_journal_entries()
  ```

---

## **Technical Implementation**  

### **Core Components**  
| Component | Purpose | Technology |
|-----------|---------|------------|
| **Journal Storage** | Store/retrieve personal entries | ChromaDB |
| **Semantic Search** | Find relevant past entries | Gemini Embeddings |
| **Therapeutic Chat** | Context-aware responses | `gemini-2.0-flash` |
| **Evaluation** | Ensure quality/safety | Custom LLM grader |

### **Code Highlights**  
1. **Journal Processing**:  
   ```python
   add_journal_entry_chunked("Felt calm walking by the river today")
   # → Splits into embeddable chunks
   ```

2. **RAG Workflow**:  
   ```python
   relevant_entries = find_relevant_entries("stress relief")
   # → Returns: ["Walking by river helped me relax last week"]
   ```

3. **Safety System**:  
   ```python
   if "suicidal" in message:
       return "Please contact a professional at 1-800-XXX-XXXX"
   ```

---

## **How to Use**  
1. **Start Journaling**:  
   ```python
   add_journal_entry("Today I felt anxious during the meeting")
   ```

2. **Chat with AuraMind**:  
   ```python
   send_message_with_rag("How can I reduce anxiety?")
   # Output: 
   # "Based on your journal, tea breaks helped before. 
   # Try that and deep breathing."
   ```

3. **Review Insights**:  
   ```python
   evaluate_aura_response() 
   # → Returns quality metrics
   ```

---

## **Why This Matters**  
- **Personalized Therapy**: Remembers user's history  
- **Proactive Mental Care**: Suggests techniques based on past successes  
- **Safe AI**: Built-in evaluation prevents harmful responses  

**Example Therapeutic Exchange**:  
> **User**: "I'm feeling overwhelmed..."  
> **AuraMind**: "I hear you. On May 20th you wrote that listing tasks helped. Want to try that together now?"  

This transforms generic chatbots into **true AI companions** for mental well-being. Would you like me to elaborate on any specific part?
