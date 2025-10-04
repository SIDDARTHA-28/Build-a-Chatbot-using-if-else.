# Build-a-Chatbot-using-if-else.
Create a rule-based chatbot
# Simple Rule-Based Chatbot in Python
# Objective: Demonstrate basic NLP structure via if-else pattern matching

def get_response(user_input):
    """
    Core function using if-else to match user input and generate responses.
    Basic NLP: Keyword matching for intent recognition.
    """
    user_input = user_input.lower().strip()  # Normalize input (basic preprocessing)
    
    # Greeting intents
    if any(word in user_input for word in ['hello', 'hi', 'hey', 'greetings']):
        return "Hello! Welcome to the Bookstore Chatbot. How can I help you today?"
    
    # Book query intents
    elif any(word in user_input for word in ['book', 'recommend', 'suggest']):
        return "I recommend 'The Hitchhiker's Guide to the Galaxy' by Douglas Adams. It's a fun sci-fi classic! What genre do you like?"
    
    # Price or availability intents
    elif any(word in user_input for word in ['price', 'cost', 'buy', 'available']):
        return "Most books are $15-25. Check our website for current stock: www.bookstore.com"
    
    # Farewell intents
    elif any(word in user_input for word in ['bye', 'goodbye', 'exit', 'quit']):
        return "Thanks for chatting! Come back soon. Goodbye!"
    
    # Default fallback
    else:
        return "I'm not sure how to help with that. Try asking about books, recommendations, or prices."

def chatbot_simulation():
    """
    Main loop to simulate the chatbot conversation.
    Runs until user says goodbye.
    """
    print("Bot: Hello! I'm the Bookstore Assistant. Type 'bye' to exit.")
    
    while True:
        user_input = input("You: ")
        if user_input.lower().strip() == 'bye':
            print("Bot: Goodbye!")
            break
        
        response = get_response(user_input)
        print(f"Bot: {response}")

# Run the simulation
if __name__ == "__main__":
    chatbot_simulation()
