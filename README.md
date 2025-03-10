# Experimenting-with-GEMINI-API-KEY

## Overview  
This repository demonstrates practical usage of Google's Gemini API in Python, showcasing text generation, embeddings, and advanced configuration techniques.  

## Prerequisites  
- Python 3.7+  
- Google Gemini API Key  

## Installation  

1. Install the Gemini API library  
```bash  
pip install -q -U google-genai

Getting Started:

1. Obtain API Key

Visit Google AI Studio (https://aistudio.google.com/apikey)
Generate your unique API key

2. Key Features Demonstrated

Text Generation
Generate text responses using Gemini models:

from google import genai  

client = genai.Client(api_key="YOUR_API_KEY")  
response = client.models.generate_content(  
    model="gemini-2.0-flash",   
    contents="what is the meaning of life?"  
)  
print(response.text)

2.1. Embeddings:

Create semantic vector representations of text:

result = client.models.embed_content(  
    model="text-embedding-004",  
    contents="What is the meaning of life?"  
)  
print(result.embeddings)  

2.2. Streaming Text Generation:

Stream text responses in real-time:

response = client.models.generate_content_stream(  
    model="gemini-2.0-flash",  
    contents=["Explain how human life works"]  
)  
for chunk in response:  
    print(chunk.text, end="")  

2.3. Configurable Text Generation:

Control generation parameters:

response = client.models.generate_content(  
    model="gemini-2.0-flash-lite",  
    contents=["Explain economics"],  
    config=types.GenerateContentConfig(  
        max_output_tokens=500,  
        temperature=0.1  
    )  
)

2.4. Generate text from text-and-image input:

from PIL import Image
from google import genai

client = genai.Client(api_key="YOUR_API_KEY")

image = Image.open("/content/IMG-20250309-WA0037.jpg")
response = client.models.generate_content(
    model="gemini-2.0-flash",
    contents=[image, "Tell me what you understand from this picture"])
print(response.text)

Resources:

https://ai.google.dev/gemini-api/docs/quickstart?lang=python
https://ai.google.dev/

Thank you for exploring this Gemini API demonstration! 🚀

Show Your Support:

If you found these insights helpful:

⭐ Star this repository
🍴 Fork to share with others
💡 Contribute by opening issues or pull requests


THANKU!!!
