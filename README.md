# 🤖 OpenAI CLI Chatbot

A simple command-line chatbot built using the OpenAI API and Python. Users can interact with GPT models directly from the terminal.

---

## 🚀 Features

* Interactive command-line chatbot
* Powered by OpenAI GPT models
* Easy to understand and modify
* Beginner-friendly project
* Error handling included
* Supports exit commands (`quit`, `q`, `exit`)

---

## 📂 Project Structure

```text
.
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 🛠️ Technologies Used

* Python 3.x
* OpenAI API
* OpenAI Python SDK

---

## 📦 Installation

### Clone the Repository

```bash
git clone https://github.com/abhinavaby/openai-cli-chatbot.git
cd openai-cli-chatbot
```

### Create a Virtual Environment

```bash
python -m venv .venv
```

### Activate the Virtual Environment

#### macOS/Linux

```bash
source .venv/bin/activate
```

#### Windows

```cmd
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Set Up API Key

### macOS/Linux

```bash
export OPENAI_API_KEY="your_api_key_here"
```

### Windows

```cmd
set OPENAI_API_KEY=your_api_key_here
```

---

## ▶️ Run the Application

```bash
python main.py
```

---

## 💻 Example Usage

```text
==================================================
🤖 OpenAI CLI Chatbot
Type 'quit', 'q', or 'exit' to stop
==================================================

You: What is Artificial Intelligence?

Chatbot: Artificial Intelligence (AI) is the simulation of human intelligence in machines that are programmed to think and learn.

You: exit

👋 Goodbye!
```

---

## 📜 Source Code

```python
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.getenv("OPENAI_API_KEY")
)

def chat_with_gpt(prompt):
    try:
        response = client.chat.completions.create(
            model="gpt-4o-mini",
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        return response.choices[0].message.content

    except Exception as e:
        return f"Error: {e}"

def main():
    print("=" * 50)
    print("🤖 OpenAI CLI Chatbot")
    print("Type 'quit', 'q', or 'exit' to stop")
    print("=" * 50)

    while True:
        user_input = input("\nYou: ")

        if user_input.lower() in ["quit", "q", "exit"]:
            print("👋 Goodbye!")
            break

        response = chat_with_gpt(user_input)
        print(f"\nChatbot: {response}")

if __name__ == "__main__":
    main()
```

---

## 📋 Requirements

Create a file named `requirements.txt`:

```text
openai>=1.0.0
```

---

## 🔒 Security Note

Never commit your OpenAI API key to GitHub.

Use environment variables or a `.env` file to store sensitive credentials.

---

## 🚀 Future Enhancements

* Chat history
* Conversation memory
* GUI using Tkinter
* Streamlit web application
* Voice assistant integration
* Multi-model support

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Abhinav Aby**

GitHub: https://github.com/abhinavaby
