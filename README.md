<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday [Nama Teman]!</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="message" id="message1">
            <h1>🎉 Selamat Ulang Tahun, [Nama Teman]! 🎉</h1>
            <p>Hari ini adalah hari istimewa untukmu! Kami semua sangat bersemangat untuk merayakannya denganmu.</p>
            <img src="images/birthday-cake.jpg" alt="Birthday Cake" class="photo">
            <button onclick="nextMessage(2)">Next</button>
        </div>

        <div class="message" id="message2" style="display:none;">
            <h1>🎂 Ulang Tahun ke-[umur] 🎂</h1>
            <p>Semoga kamu mendapatkan kebahagiaan, kesehatan, dan kesuksesan di tahun yang baru ini!</p>
            <img src="images/balloons.jpg" alt="Balloons" class="photo">
            <button onclick="nextMessage(3)">Next</button>
        </div>

        <div class="message" id="message3" style="display:none;">
            <h1>🎁 Pesan Spesial 🎁</h1>
            <p>Jangan lupa untuk merayakan dengan penuh suka cita. Kami semua sangat beruntung memiliki kamu!</p>
            <img src="images/party.jpg" alt="Party" class="photo">
            <button onclick="nextMessage(4)">Next</button>
        </div>

        <div class="message" id="message4" style="display:none;">
            <h1>🎊 Rencana Perayaan 🎊</h1>
            <p>Tanggal: [Tanggal Perayaan]<br>
               Tempat: [Tempat Perayaan]<br>
               Waktu: [Waktu Perayaan]</p>
            <img src="images/confetti.jpg" alt="Confetti" class="photo">
            <button onclick="nextMessage(5)">Next</button>
        </div>

        <div class="message" id="message5" style="display:none;">
            <h1>🎈 Terima Kasih! 🎈</h1>
            <p>Terima kasih atas semua momen berharga yang telah kita bagikan. Selamat ulang tahun sekali lagi!</p>
            <button onclick="endMessage()">Selesai</button>
        </div>
    </div>

    <audio id="birthday-audio" src="audio/happy-birthday.mp3"></audio>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f8ff;
    color: #333;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
}

.container {
    text-align: center;
    padding: 20px;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.message {
    margin-bottom: 20px;
}

.photo {
    width: 100%;
    max-width: 400px;
    border-radius: 10px;
    margin: 20px 0;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
body {
    font-family: Arial, sans-serif;
    background-color: #f0f8ff;
    color: #333;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
}

.container {
    text-align: center;
    padding: 20px;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.message {
    margin-bottom: 20px;
}

.photo {
    width: 100%;
    max-width: 400px;
    border-radius: 10px;
    margin: 20px 0;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('birthday-audio');
    audio.play(); // Play birthday song when the page loads

    function nextMessage(nextId) {
        // Hide all messages
        const messages = document.querySelectorAll('.message');
        messages.forEach(message => message.style.display = 'none');
        
        // Show the next message
        const nextMessage = document.getElementById('message' + nextId);
        if (nextMessage) {
            nextMessage.style.display = 'block';
        }
    }

    function endMessage() {
        const messages = document.querySelectorAll('.message');
        messages.forEach(message => message.style.display = 'none');
        
        // Show a final message or redirect
        alert('Semoga hari ulang tahunmu menyenangkan!');
        // window.location.href = 'https://example.com'; // Redirect to a custom URL
    }

    // Expose the functions to the global scope for button onclick events
    window.nextMessage = nextMessage;
    window.endMessage = endMessage;
});
