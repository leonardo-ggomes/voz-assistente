# Resposta por voz
const f = new SpeechSynthesisUtterance(texto);
f.lang = 'pt-BR';
window.speechSynthesis.speak(f);

# Captura
const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

 const recognition = new SpeechRecognition();
            recognition.lang = 'pt-BR';


 recognition.start();

  recognition.onstart = () => { ... }

  recognition.onresult = (event) => {
      const comando = event.results[0][0].transcript.toLowerCase();
      status.innerText = `Você disse: "${comando}"`;

  }


  recognition.onerror = () => {
    orb.classList.remove('listening');
    status.innerText = "Erro ao tentar ouvir.";
};