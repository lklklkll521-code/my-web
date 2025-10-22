.................
<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Миний Хамгийн Сайн Найз 💕</title>
<style>
  body {
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(180deg, #ffe6f0, #fffafc);
    display: flex;
    justify-content: center;
    padding-top: 40px;
    margin: 0;
  }

  #chat-container {
    width: 100%;
    max-width: 420px; /* Гар дээр ч тохиромжтой */
    background: #fff;
    padding: 20px;
    border-radius: 20px;
    box-shadow: 0 5px 15px rgba(255, 105, 180, 0.3);
    display: flex;
    flex-direction: column;
  }

  h2 {
    text-align: center;
    color: #ff66a3;
    margin-bottom: 15px;
    font-family: 'Dancing Script', cursive;
    font-size: 26px;
  }

  #messages {
    height: 300px;
    overflow-y: auto;
    border: 1px solid #ffcce0;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 12px;
    background: #fff0f7;
    font-family: 'Comic Neue', cursive;
    flex-grow: 1;
  }

  .message {
    margin: 6px 0;
    padding: 8px 12px;
    border-radius: 14px;
    max-width: 80%;
    word-wrap: break-word;
  }

  .user {
    background: #d8eaff;
    color: #004085;
    margin-left: auto;
    text-align: right;
  }

  .bot {
    background: #ffe0f0;
    color: #b30059;
    margin-right: auto;
  }

  /* Input ба Button зэрэгцсэн стиль */
  #input-container {
    display: flex;
    gap: 8px;
  }

  #user-input {
    flex: 1;
    padding: 10px;
    border-radius: 20px;
    border: 1px solid #ffb6c1;
    font-family: 'Comic Neue', cursive;
    font-size: 15px;
    outline: none;
  }

  #send-btn {
    padding: 10px 16px;
    border-radius: 20px;
    border: none;
    background: linear-gradient(45deg, #ff66a3, #ff3385);
    color: white;
    font-family: 'Dancing Script', cursive;
    font-size: 15px;
    cursor: pointer;
    transition: 0.3s;
  }

  #send-btn:hover {
    background: linear-gradient(45deg, #ff3385, #ff66a3);
    transform: scale(1.05);
  }

  /* Гар дээр жижиг дэлгэцэд */
  @media (max-width: 480px) {
    #chat-container {
      padding: 15px;
    }
    #messages {
      height: 250px;
    }
    #user-input, #send-btn {
      font-size: 14px;
      padding: 8px 10px;
    }
  }
</style>
</head>
<body>

<div id="chat-container">
  <h2>💬 Миний Сайн Найз Чатбот</h2>
  <div id="messages"></div>

  <!-- Input ба Button зэрэгцүүлсэн хэсэг -->
  <div id="input-container">
    <input type="text" id="user-input" placeholder="Надтай ярь 💖">
    <button id="send-btn" onclick="sendMessage()">Илгээх</button>
  </div>
</div>

<script>
const messages = document.getElementById('messages');

const qa = [
  { question: "сайн уу", answer: "Сайн , миний хөөрхөн найз минь! 💖 Өнөөдөр ямар байна?" },
  { question: "ядарч байна", answer: "ядарж болохгүй шүү эрт унтаж амраад хоолоо сайн идээрэй <3😊" },
  { question: "би чиний хувьд ямар хүн бэ?", answer: "алдаж болохгүй хүний нэг" },
  { question: "баярлалаа", answer: "зүгээрээ 😊" },
  { question: "ганцаардаж байна", answer: "би чамтай хамт байна шүү, битгий гунигла 💕" },
  { question: "би хэр хөөрхөн бэ?", answer: "шөнийн тэнгэрийн одноос хөөрхөншд😌" },
  { question: "намайг дуугаар илэрхийл", answer: "enkhe & erkhem chi dur bulaam." },
  { question: "үүрд найзууд байна биздээ", answer: "тэгэлгүй яхавдээ🌸" },
  { question: "чамд хэлэх үг байна уу", answer: "Мэдээж! анх танилцсандаа харамсаж үзээгүй ээ цаашдаа ч бас сайн найзууд байя ❤️" },
  { question: "баяртай сайхан амраарай", answer: "чи бас сайхан амраарай гоё зүүд зүүдлээрэй 💖" }
];

function sendMessage() {
  const input = document.getElementById('user-input');
  const userText = input.value.trim();
  if (!userText) return;

  appendMessage(userText, 'user');
  input.value = '';

  const botReply = getBotReply(userText);
  setTimeout(() => appendMessage(botReply, 'bot'), 500);
}

function appendMessage(text, sender) {
  const msgDiv = document.createElement('div');
  msgDiv.className = 'message ' + sender;
  msgDiv.textContent = text;
  messages.appendChild(msgDiv);
  messages.scrollTop = messages.scrollHeight;
}

function getBotReply(userText) {
  const lowerText = userText.toLowerCase();
  for (let i = 0; i < qa.length; i++) {
    if (lowerText.includes(qa[i].question)) {
      return qa[i].answer;
    }
  }
  return "Хөөе найз аа 😄 энэ чинь ямар асуулт вэ? Дахиад сонирхолтой юм асуугаач~ 💬";
}
</script>

</body>
</html>
