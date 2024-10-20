# Psycho-Relief---A-Virtual-Cognitive-Behavioral-Therapist-for-OCD

## Problem Statement:

Many people around the world suffer from Obsessive-Compulsive Disorder (OCD), a condition that can develop due to a variety of factors, including genetics, trauma, stress, or environmental influences. Despite its prevalence, many individuals are reluctant to seek help from a psychiatrist due to family pressures, cultural expectations, or the fear of being judged by society. This hesitation often results in the disorder going untreated, leading to a worsening of symptoms over time.

OCD is characterized by intrusive, unwanted thoughts (obsessions) and repetitive behaviors or mental rituals (compulsions) that individuals feel compelled to perform in an attempt to alleviate anxiety. However, these compulsions often provide only temporary relief, trapping individuals in a cycle of distress. Left untreated, OCD can significantly impair one's ability to function in everyday life, affecting work, relationships, and overall well-being.

In addition to mental health challenges, the stress caused by OCD can lead to physical health issues such as fatigue, headaches, and digestive problems, as well as an increased risk of developing anxiety disorders and depression. Individuals with OCD may find it hard to focus, complete tasks, or enjoy their daily activities, as their minds are frequently preoccupied with obsessive thoughts and compulsive behaviors. This can create a sense of isolation and hopelessness, making it even more difficult for them to seek help.

Addressing OCD requires a comprehensive approach, including professional mental health support, therapy, and sometimes medication, yet societal stigma and lack of awareness often prevent individuals from accessing the care they need. Public education about OCD and the importance of seeking timely psychiatric help can play a key role in breaking down barriers and helping those affected reclaim control over their lives.


## Proposed Solution: 

Our solution to the problem of untreated OCD is Psycho Relief, a virtual cognitive behavioral therapist designed specifically for individuals suffering from OCD. This innovative web app provides comprehensive support through virtual counseling sessions, delivered as engaging videos that guide users in managing and overcoming their symptoms. In addition to these video sessions, Psycho Relief offers structured daily exercises aimed at promoting gradual recovery and helping users regain control over their lives.The app also features an advanced diagnostic tool that identifies the specific type of OCD an individual is experiencing, ensuring that each user receives personalized treatment plans. By tailoring recovery strategies to fit the unique challenges of each type of OCD, Psycho Relief empowers individuals to work toward full recovery. 

## Sample Code:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OCD Chat Interface</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html, body {
            height: 100%;
            width: 100%;
            font-family: 'Arial', sans-serif;
            background-color: #f7f7f7;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        .chat-container {
            width: 100%;
            height: 100%;
            max-width: 1600px; /* Larger max-width for laptop screens */
            max-height: 1000px; /* Max-height to fit larger screens */
            display: flex;
            flex-direction: column;
            background-color: #fff;
            border-radius: 0px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
        }

        /* Updated color to green */
        .chat-header {
            text-align: center;
            padding: 20px;
            background-color: #28a745; /* Green color */
            color: white;
            font-size: 28px;
            font-weight: bold;
            border-radius: 10px 10px 0 0;
        }

        .chat-box {
            flex-grow: 1; /* Allows the chat-box to grow and fill available space */
            padding: 30px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
            background-color: #f0f0f0;
        }

        .messages p {
            margin: 0;
            padding: 20px;
            border-radius: 15px;
            max-width: 70%;
            word-wrap: break-word;
            font-size: 18px;
            transition: all 0.3s ease;
        }

        /* Updated user-message color to green */
        .user-message {
            align-self: flex-end;
            background-color: #28a745; /* Green color */
            color: white;
        }

        .bot-message {
            align-self: flex-start;
            background-color: #e9ecef;
            color: #333;
        }

        .input-container {
            width: 100%;
            display: flex;
            padding: 20px 30px;
            background-color: #fff;
            border-top: 1px solid #ccc;
            justify-content: space-between;
        }

        input[type="text"] {
            flex: 1;
            padding: 15px;
            border-radius: 30px;
            border: 1px solid #ccc;
            font-size: 18px;
            outline: none;
        }

        /* Updated button color to green */
        button {
            padding: 15px 30px;
            margin-left: 20px;
            background-color: #28a745; /* Green color */
            color: white;
            border: none;
            border-radius: 30px;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #218838; /* Darker green on hover */
        }

        /* Smooth scrollbar */
        .chat-box::-webkit-scrollbar {
            width: 10px;
        }

        .chat-box::-webkit-scrollbar-thumb {
            background-color: #cccccc;
            border-radius: 10px;
        }

        .chat-box::-webkit-scrollbar-track {
            background-color: #f1f1f1;
        }

        /* Responsive adjustments for smaller screens */
        @media (max-width: 1200px) {
            .chat-container {
                width: 100%;
                height: 100%;
                border-radius: 0;
            }
            .input-container {
                padding: 15px;
            }
            input[type="text"] {
                padding: 12px;
                font-size: 16px;
            }
            button {
                padding: 12px 25px;
                font-size: 16px;
            }
        }
    </style>
</head>
<body>

<div class="chat-container">
    <!-- Added the heading here -->
    <div class="chat-header">
        Predict Your OCD Type
    </div>
    <div class="chat-box messages" id="messages">
        <!-- Chat messages will be dynamically added here -->
    </div>
    <div class="input-container">
        <input type="text" id="user-input" placeholder="Type your symptoms..." />
        <button onclick="sendMessage()">Send</button>
    </div>
</div>

<script>
// Full dataset of symptoms paragraphs and corresponding OCD types
const data = {
  symptoms: [
    'Fear of contamination, avoidance of dirt, excessive cleaning, washing hands repeatedly, using gloves. Public places may cause anxiety about germs and a need to disinfect everything. Refusing to touch surfaces or using hand sanitizer excessively are common.',
    'Fear of making mistakes, needing to check things repeatedly, such as checking doors, locks, appliances, or emails to ensure tasks were done correctly. Feeling compelled to ask for reassurance or double-check personal belongings.',
    'Need for symmetry and orderliness. Compulsion to arrange objects or items in a particular order, discomfort if things are out of line or not visually pleasing. Constantly counting items or needing balance.',
    'Intrusive, unwanted thoughts about harming others or doing something morally wrong. Replaying disturbing images or violent thoughts. Often involves guilt or second-guessing morality and actions.',
    'Difficulty discarding items or emotional attachment to objects that others might consider worthless. Hoarding behavior involves saving newspapers, magazines, or broken items and feeling distressed when discarding items.'
  ],
  ocdTypes: [
    'Contamination OCD',
    'Checking OCD',
    'Symmetry and Orderliness OCD',
    'Intrusive Thoughts OCD',
    'Hoarding OCD'
  ]
};

// Function to add messages to the chat box
function addMessage(text, sender) {
    const messages = document.getElementById('messages');
    const messageElement = document.createElement('p');
    messageElement.classList.add(sender === 'user' ? 'user-message' : 'bot-message');
    messageElement.textContent = text;
    messages.appendChild(messageElement);
    messages.scrollTop = messages.scrollHeight;  // Scroll to the bottom
}

// Function to handle sending the user message and getting the response
function sendMessage() {
    const userInput = document.getElementById('user-input').value.trim();
    if (userInput === '') return;

    // Add user message to chat
    addMessage(userInput, 'user');

    // Clear the input box
    document.getElementById('user-input').value = '';

    // Get the response (OCD type)
    const ocdType = identifyOCD(userInput);

    // Simulate bot response delay
    setTimeout(() => {
        addMessage(ocdType, 'bot');
    }, 500);  // 500ms delay for bot response
}

// Matching function without fallback, returning "No matching OCD type found"
function identifyOCD(symptomsInput) {
    symptomsInput = symptomsInput.toLowerCase();
    let ocdType = 'No matching OCD type found.';

    // Search for a match by checking if any word in the input is present in the symptoms paragraphs
    for (let i = 0; i < data.symptoms.length; i++) {
        let symptomText = data.symptoms[i].toLowerCase();
        
        // Split user input into words and check each word
        let inputWords = symptomsInput.split(' ');
        let wordMatch = inputWords.some(word => symptomText.includes(word));
        
        if (wordMatch) {
            ocdType = `Predicted OCD Type: ${data.ocdTypes[i]}`;
            break;
        }
    }

    return ocdType;
}

// Add event listener to send message on pressing "Enter"
document.getElementById('user-input').addEventListener('keydown', function(event) {
    if (event.key === 'Enter') {
        sendMessage(); // Call the send message function when "Enter" is pressed
    }
});
</script>

</body>
</html>
```

## Sample Output for Working Model:

![photo-collage png](https://github.com/user-attachments/assets/11ca7ad9-c670-4e78-8ed1-173940ccd012)
![Screenshot 2024-10-19 190256](https://github.com/user-attachments/assets/1952ce02-2ea2-4171-8f46-38678e2a7b98)
![Screenshot 2024-10-19 190111](https://github.com/user-attachments/assets/99069cdc-7f05-4f39-a512-b0e7d52ded86)



