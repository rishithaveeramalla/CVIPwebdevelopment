# CVIPwebdevelopment
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Link Shortener</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      font-style: italic;
      background-color: #ffc0cb; 
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      text-align: center;
      background-color: #fff;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    input[type="text"] {
      width: 80%;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 3px;
      border: 1px solid #ccc;
    }

    button {
      padding: 10px 20px;
      background-color: #007bff;
      color: #fff;
      border: none;
      border-radius: 3px;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    #result {
      margin-top: 20px;
    }

    #shortenedUrl {
      width: 80%;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Link Shortener</h1>
    <input type="text" id="inputUrl" placeholder="Enter URL">
    <button onclick="shortenUrl()">Shorten</button>
    <div id="result" style="display: none;">
      <p>Shortened URL:</p>
      <input type="text" id="shortenedUrl" readonly>
    </div>
  </div>

  <script>
    function shortenUrl() {
      const inputUrl = document.getElementById('inputUrl').value;
    
      const hashedUrl = hashString(inputUrl);
      
      const shortenedUrlInput = document.getElementById('shortenedUrl');
      shortenedUrlInput.value = `http://yourdomain.com/${hashedUrl}`;
    
      const resultDiv = document.getElementById('result');
      resultDiv.style.display = 'block';
    }

    function hashString(str) {
      let hash = 0;
      for (let i = 0; i < str.length; i++) {
        hash += str.charCodeAt(i);
      }
      return hash.toString(36);
    }
  </script>
</body>
</html>
