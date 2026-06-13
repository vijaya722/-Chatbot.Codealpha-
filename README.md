import datetime

def chatbot():
    print("Chatbot: Hello! Type 'bye' to exit.\n")

    # Open file to save chat
    file = open("chat_history.txt", "a")

    while True:
        user = input("You: ")
        
        # Save user input with time
        time = datetime.datetime.now()
        file.write(f"\n[{time}] You: {user}")

        user_lower = user.lower()

        if "hello" in user_lower:
            reply = "Hi!"
        
        elif "how are you" in user_lower:
            reply = "I'm fine, thanks!"

        elif "your name" in user_lower:
            reply = "I'm your Python chatbot!"

        elif "bye" in user_lower:
            reply = "Goodbye!"
            print("Chatbot:", reply)
            file.write(f"\n[{time}] Bot: {reply}")
            break

        else:
            reply = "Sorry, I don't understand that."

        print("Chatbot:", reply)

        # Save bot reply
        file.write(f"\n[{time}] Bot: {reply}")

    file.close()
    print("\n Chat saved in 'chat_history.txt'")

# Run chatbot
chatbot() #-Chatbot.Codealpha-
