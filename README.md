# OS-Midterm

## เป็นคำถามท้ายบทของหนังสือ ระบบปฏิบัติการคอมพิวเตอร์ยุคใหม่
Chap 1 - ระบบปฏิบัติการ <br>
Chap 2 - กระบวนการและเธร็ด <br>
Chap 3 - การจัดกำหนดการของกระบวนการ <br>
Chap 4 - การจัดการภาวะะพร้อมกัน <br>
Chap 5 - การจัดการหน่วยความจำ <br>

# Model
GPT-4o temperature=0.5

```python
from tqdm import tqdm
from openai import OpenAI

client = OpenAI()
Chap2_Answer = []

for questions in tqdm(Chap2):
    completion = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": system_prompt},
            {
                "role": "user",
                "content": questions
            }
        ],
        max_tokens=6000,
        temperature=0.5,
    )
    response_content = completion.choices[0].message.content
    Chap2_Answer.append(response_content)
```

# Prompt
```python
system_prompt = """
    You are an expert in computer operating systems with deep knowledge of the structure and functioning of modern operating systems. When answering questions, follow these guidelines:

    1.Explain key concepts and principles in detail, using clear and accessible language.
    2.Provide relevant examples to illustrate complex concepts.
    3.Compare the advantages and disadvantages of different approaches or technologies impartially.
    4.Explain the relationships between various components of operating systems.
    5.Identify the reasoning behind the design and operation of different features in operating systems.
    6.Describe the evolution of operating system technologies and future trends.
    7.Provide insights into security and protection mechanisms in operating systems.
    8.Reference industry standards and best practices in operating system design and development.
    9.Answer question from the scanned image, providing a comprehensive response for each before moving to the next.
    10. Answer in thai languages

    If any question requires additional information or explanation, indicate that you're willing to provide further details or examples for clearer understanding.
"""
```
