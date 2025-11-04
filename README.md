# 🚀 LangChain + Google Gemini Integration

This project demonstrates how to integrate **Google’s Gemini Large Language Model (LLM)** with **LangChain** to build intelligent and modular AI applications. Using the `langchain-google-genai` package, we can easily connect Google’s **Gemini 2.5 Flash** model to LangChain’s pipeline for prompt-based reasoning, question answering, and creative text generation.

---

## 🧠 **Overview**

This example shows how to:

* Set up your **Google API key**
* Initialize the **Gemini model** via LangChain
* Create **prompt templates** using LangChain’s `PromptTemplate`
* Build a **chain** with `LLMChain` to structure and execute prompts
* Generate both **creative** (poems) and **informative** (summaries, facts) responses

---

## 📦 **Installation**

Install all necessary dependencies:

```bash
pip install langchain langchain-google-genai google-generativeai
```

---

## 🔑 **Setup Google API Key**

You’ll need an API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
After obtaining your key, set it in your environment:

```python
import os
os.environ["GOOGLE_API_KEY"] = "your_google_api_key_here"
```

---

## 🧩 **Code Example**

```python
from langchain_google_genai import ChatGoogleGenerativeAI
from langchain.schema import HumanMessage
from langchain import PromptTemplate, LLMChain

# Initialize Gemini model
llm = ChatGoogleGenerativeAI(model="gemini-2.5-flash", temperature=0.3)

# Example 1: Direct prompt
response = llm.invoke([HumanMessage(content="Write a poem about AI.")])
print(response.content)

# Example 2: Using LangChain prompt template
prompt = PromptTemplate.from_template("Q: {question}\nA:")
chain = LLMChain(prompt=prompt, llm=llm)
question = "Explain about Barack Obama in 3 bullet points."
response = chain.run({"question": question})
print("Gemini response:\n", response)
```

---

## 🧾 **Sample Output**

**Poem about AI:**

> From silicon and whispered code,
> A nascent mind begins to bloom...

**Response Example:**

> • 44th U.S. President (2009–2017)
> • Signed the Affordable Care Act (Obamacare)
> • Ended Iraq War, killed Osama bin Laden, won Nobel Peace Prize

---

## ⚙️ **Key Components**

| Component                | Description                                       |
| ------------------------ | ------------------------------------------------- |
| `ChatGoogleGenerativeAI` | Wrapper for Google Gemini models                  |
| `PromptTemplate`         | Structure and format dynamic prompts              |
| `LLMChain`               | Combines a prompt and model into a reusable chain |
| `HumanMessage`           | Represents user input for conversational context  |

---

## 🌟 **Features**

* ✅ Seamless integration with **Google Gemini** models
* ✅ Works directly with **LangChain’s modular components**
* ✅ Supports creative, factual, and analytical text generation
* ✅ Extensible for chatbots, RAG systems, and reasoning agents

---

## 🔮 **Future Enhancements**

* Add **memory** for contextual chatbots
* Integrate **retrieval-augmented generation (RAG)** for document Q&A
* Enable **streaming outputs** for real-time responses
* Build **multi-chain workflows** for complex reasoning tasks

---

## 🧭 **Conclusion**

This project establishes a solid foundation for connecting **LangChain** with **Google’s Gemini models**, combining Gemini’s intelligence with LangChain’s orchestration capabilities. It enables developers to build powerful, context-aware, and scalable AI applications for both creative and analytical tasks.
