import os
import streamlit as st
from groq import Groq

# Initialize the Groq client with your API key
client = Groq(api_key=os.environ.get("GROQ_API_KEY"))

def get_chat_completion(prompt):
    try:
        # Make the API call with the user-provided prompt
        chat_completion = client.chat.completions.create(
            messages=[
                {"role": "user", "content": prompt}
            ],
            model="llama3-8b-8192"
        )
        
        # Return the response content
        return chat_completion.choices[0].message.content
    
    except Exception as e:
        return f"An error occurred: {str(e)}"

def main():
    st.title("Groq API Chat Interface")
    st.write("Enter your prompt below and press 'Submit'. Type 'exit' to quit.")

    # Text input for the prompt
    prompt = st.text_input("Enter your question:")

    if st.button("Submit"):
        if prompt.lower() == 'exit':
            st.write("Exiting the chat. Goodbye!")
        else:
            # Get response from Groq API
            response = get_chat_completion(prompt)
            if response:
                st.write("Groq API Response:")
                st.write(response)

if __name__ == "__main__":
    main()%                                         
