<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday! 💖</title>
    <style>
        /* CSS STYLES */
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
            background-color: #ffe4e1; /* Misty Rose / Light Pink Background */
            color: #333;
            text-align: center;
            overflow: hidden; /* Prevent scrollbar from running button */
        }

        .container {
            background-color: #fff0f5; /* Lavender Blush / Slightly lighter pink */
            padding: 40px 60px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            max-width: 90%;
            z-index: 10;
        }

        h1 {
            color: #ff69b4; /* Hot Pink */
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px #fff;
        }

        h2 {
            color: #ffb6c1; /* Light Pink */
            font-size: 1.5em;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 30px;
        }

        .btn {
            padding: 15px 30px;
            font-size: 1.2em;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        #yesBtn {
            background-color: #ff69b4; /* Hot Pink */
            color: white;
        }

        #yesBtn:hover {
            background-color: #ff1493; /* Deep Pink */
            transform: scale(1.1);
        }

        #noBtn {
            background-color: #ffb6c1; /* Light Pink */
            color: #888;
            position: relative; /* Essential for running away */
        }

        #message {
            margin-top: 40px;
            font-size: 2em;
            color: #ff69b4; /* Hot Pink */
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy Birthday KULOTTTTT! 🥳</h1>
        <h2>I have a one question for u hehe</h2>
        <p style="font-size: 1.8em; color: #ff69b4;">**Will you go on a date with me?**</p>

        <div class="buttons">
            <button id="yesBtn" class="btn" onclick="handleYes()">Yes! 💖</button>
            <button id="noBtn" class="btn">No. 😔</button>
        </div>

        <div id="message"></div>
    </div>

    <script>
        // JAVASCRIPT LOGIC

        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const message = document.getElementById('message');
        const container = document.querySelector('.container');

        // Function for when the "No" button is hovered over (it runs away)
        noBtn.addEventListener('mouseover', () => {
            const containerRect = container.getBoundingClientRect();
            const btnRect = noBtn.getBoundingClientRect();

            // Calculate new random position within the container bounds
            const maxX = containerRect.width - btnRect.width;
            const maxY = containerRect.height - btnRect.height;
            
            // Generate random positions (in the range of -50% to 50% of the container)
            // relative to the center, so the button doesn't jump way off screen.
            const newX = Math.random() * (maxX * 0.8) - (maxX * 0.4);
            const newY = Math.random() * (maxY * 0.8) - (maxY * 0.4);

            noBtn.style.position = 'absolute';
            noBtn.style.transition = 'transform 0.1s ease'; // Make movement quick
            
            // Apply the new position
            noBtn.style.transform = `translate(${newX}px, ${newY}px)`;
        });

        // Reset position on mouseleave or after a slight delay
        noBtn.addEventListener('mouseleave', () => {
             // Optional: reset after a quick run-around, if you want it to jump back
             // noBtn.style.transform = 'translate(0, 0)';
        });
        
        // Function for when the "Yes" button is clicked
        function handleYes() {
            // Remove the buttons
            noBtn.style.display = 'none';
            yesBtn.style.display = 'none';

            // Display a celebratory message
            message.innerHTML = "YES!!! I'm so happy! 🥰 Let's celebrate your birthday and plan our date! 🎉";
            
            // Optional: Change the background to be even more celebratory
            document.body.style.backgroundColor = '#f7cac9'; // Even brighter pink
            
            // Optional: Add confetti effect (requires more code, but you can imagine it!)
        }
    </script>
</body>
</html>
