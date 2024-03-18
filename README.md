const botao = document.getElementById('botao');
const textoInput = document.getElementById('texto');
const audioElement = document.getElementById('audio');

// Função para converter texto em áudio
async function textoParaAudio() {
    const texto = textoInput.value;
    
    // Verifica se o navegador suporta a API de fala
    if ('speechSynthesis' in window) {
        // Cria um novo objeto SpeechSynthesisUtterance
        const utterance = new SpeechSynthesisUtterance();
        
        // Define o texto a ser falado
        utterance.text = texto;
        
        // Fala o texto
        speechSynthesis.speak(utterance);
    } else {
        alert('Seu navegador não suporta a funcionalidade de texto para fala.');
    }
}

// Adiciona um evento de clique ao botão
botao.addEventListener('click', textoParaAudio);
