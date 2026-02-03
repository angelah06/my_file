<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f8ff;
      color: #333;
      text-align: center;
    }
    
    .container {
      border: 2px solid #e94e77;
      border-radius: 10px;
      padding: 30px;
      background-color: white;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    h1 {
      color: #e94e77;
      font-size: 2.5em;
      margin-bottom: 20px;
    }

    p {
      font-size: 1.2em;
      margin-bottom: 20px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    .btn {
      padding: 15px 30px;
      font-size: 1.2em;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: transform 0.3s ease-in-out;
    }

    .yes-btn {
      background-color: #e94e77;
      color: white;
    }

    .no-btn {
      background-color: #ddd;
      color: #333;
      cursor: not-allowed;
    }

    .no-btn:hover {
      animation: moveAround 1.5s linear infinite;
    }

    @keyframes moveAround {
      0% { transform: translateX(0) translateY(0); }
      25% { transform: translateX(50px) translateY(0); }
      50% { transform: translateX(0) translateY(-50px); }
      75% { transform: translateX(-50px) translateY(0); }
      100% { transform: translateX(0) translateY(50px); }
    }

    #gifContainer {
      display: none;
      margin-top: 20px;
      text-align: center;
    }

    #gifContainer img {
      max-width: 100%;
      border-radius: 10px;
    }

    .message {
      font-size: 1.5rem;
      margin-top: 20px;
    }

  </style>
</head>
<body>
  <div class="container">
    <h1 id="question">Will You Be My Valentine?</h1>
    <div class="buttons" id="buttons">
      <button class="btn yes-btn" id="yesBtn">Yes</button>
      <button class="btn no-btn" id="noBtn" disabled>No</button>
    </div>

    <div id="gifContainer">
      <img src="https://media.giphy.com/media/oZN8XgbKxymtiIQ8E4/giphy.gif" alt="Valentine's Day GIF">
      <div class="message">Yay! Happy Valentine's Day!</div>
    </div>
  </div>

  <script>
    const yesBtn = document.getElementById('yesBtn');
    const gifContainer = document.getElementById('gifContainer');
    const question = document.getElementById('question');  // Added for question element
    const buttonsContainer = document.getElementById('buttons');

    // Show the gif and message after clicking "Yes", and hide the buttons and question
    yesBtn.addEventListener('click', function () {
      question.style.display = 'none';  // Hide the question
      buttonsContainer.style.display = 'none';  // Hide the buttons
      gifContainer.style.display = 'block';    // Show the GIF and message
    });

    // If the "No" button could be enabled later, you could add similar logic for it
    noBtn.addEventListener('click', function () {
      buttonsContainer.style.display = 'none';  // Hide the buttons
      gifContainer.style.display = 'none';     // Optionally hide the GIF
      alert('Oh no! Maybe next time!');         // Optional: Show message
    });
  </script>

</body>
</html>
