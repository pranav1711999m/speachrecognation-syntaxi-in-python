# speachrecognation-syntaxi-in-python
def takeCommand():
    #it takes microphone input from the user and return string output

    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("listening...")
        r.energy_threshold = 50 #to slow down the speed of our command    
        r.pause_threshold = 1
        audio = r.listen(source)

    try:
        print("Recognizing....") '''to print '''
        query = r.recognize_google(audio, language='en-in')
        print(f"User said: {query}\n")  
    except Exception as e:
        #print(e)

        speak("say that again please") '''exceptional case'''
        return "none"        
    return query
