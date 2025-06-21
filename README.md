def chatbot_response(user_input):
    user_input = user_input.lower()

    if "hello" in user_input:
        return "Hi!"
    elif "how are you" in user_input:
        return "I'm fine, thanks!"
    elif "bye" in user_input or "goodbye" in user_input:
        return "Goodbye!"
    elif "name" in user_input:
        return "I'm a simple chatbot made using Python."
    else:
        return "I'm not sure how to respond to that."

print("Welcome to the Basic Chatbot! (Type 'bye' to exit)\n")

while True:
    user_input = input("You: ")
    response = chatbot_response(user_input)
    print("Bot:", response)
    
    if "bye" in user_input.lower():
        break
