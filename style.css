const input = document.getElementById("input");
const micBtn = document.getElementById("mic-btn");
const output = document.getElementById("output");

const SpeechRecognition =
  window.SpeechRecognition || window.webkitSpeechRecognition;

if (!SpeechRecognition) {
  alert("Speech Recognition not supported");
}

const recognition = new SpeechRecognition();
recognition.lang = "en-US";
recognition.continuous = false;
recognition.interimResults = false;

micBtn.addEventListener("click", () => {
  output.innerHTML = "🎧 Listening...";
  recognition.start();
});

recognition.onstart = () => {
  console.log("Mic started");
};

recognition.onresult = (event) => {
  const transcript = event.results[0][0].transcript;
  input.value = transcript;
  output.innerHTML = `You said: ${transcript}`;

  if (transcript.toLowerCase().includes("open google")) {
    output.innerHTML += "<br>Opening Google...";
    window.open("https://www.google.com", "_blank");
  }
};

recognition.onerror = (event) => {
  output.innerHTML = "❌ Mic error: " + event.error;
};
