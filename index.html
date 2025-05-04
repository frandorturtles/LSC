// Base de datos de señas LSC
const LSC_DATABASE = {
  'hola': {
    sign: '👋',
    description: 'Saludo moviendo la mano de lado a lado a la altura del hombro',
    examples: ['¡Hola! ¿Cómo estás?', 'Hola a todos']
  },
  'gracias': {
    sign: '🤲',
    description: 'Manos juntas moviéndose hacia adelante desde el pecho',
    examples: ['Muchas gracias', 'Te agradezco mucho']
  },
  'colombia': {
    sign: '🇨🇴',
    description: 'Movimiento circular con la mano derecha mientras se señala con el índice',
    examples: ['Soy de Colombia', 'Viva Colombia']
  },
  'si': {
    sign: '👍',
    description: 'Pulgar hacia arriba con movimiento de arriba hacia abajo',
    examples: ['Sí, estoy de acuerdo', '¿Sí?']
  },
  'no': {
    sign: '👎',
    description: 'Pulgar hacia abajo con movimiento de lado a lado',
    examples: ['No quiero', 'No, gracias']
  },
  'ayuda': {
    sign: '🙏',
    description: 'Manos juntas moviéndose hacia arriba y abajo',
    examples: ['Necesito ayuda', '¿Me puedes ayudar?']
  },
  'amor': {
    sign: '🤟',
    description: 'Manos cruzadas sobre el pecho',
    examples: ['Te amo', 'Con mucho amor']
  },
  'familia': {
    sign: '👨‍👩‍👧‍👦',
    description: 'Dibujar un círculo con ambas manos empezando desde los hombros',
    examples: ['Mi familia', 'Familia unida']
  },
  'comida': {
    sign: '🤲🍽️',
    description: 'Manos simulando llevar comida a la boca',
    examples: ['Quiero comida', '¿Qué hay de comer?']
  },
  'agua': {
    sign: '✋💧',
    description: 'Mano en forma de C moviéndose hacia la boca',
    examples: ['Quiero agua', 'Agua por favor']
  }
};

// Alfabeto manual LSC
const LSC_ALPHABET = {
  'a': '✋', 'b': '🤚', 'c': '🤏', 'd': '🤙', 'e': '🖖',
  'f': '👌', 'g': '🤘', 'h': '✌️', 'i': '🤞', 'j': '🤟',
  'k': '🤚', 'l': '👋', 'm': '🤲', 'n': '👐', 'o': '🙌',
  'p': '👏', 'q': '👍', 'r': '👎', 's': '✊', 't': '👊',
  'u': '🤛', 'v': '🤜', 'w': '🤝', 'x': '🙏', 'y': '👆',
  'z': '👇', ' ': '␣', ',': '↩️', '.': '⏺️', '?': '❓',
  '!': '❗', 'á': '✋', 'é': '🖖', 'í': '🤞', 'ó': '🙌', 'ú': '🤛',
  '0': '0️⃣', '1': '1️⃣', '2': '2️⃣', '3': '3️⃣', '4': '4️⃣',
  '5': '5️⃣', '6': '6️⃣', '7': '7️⃣', '8': '8️⃣', '9': '9️⃣'
};

// Elementos del DOM
const DOM = {
  textTab: document.getElementById('text-tab'),
  cameraTab: document.getElementById('camera-tab'),
  textInputContainer: document.getElementById('text-input-container'),
  cameraInputContainer: document.getElementById('camera-input-container'),
  inputText: document.getElementById('input-text'),
  translateBtn: document.getElementById('translate-btn'),
  clearTextBtn: document.getElementById('clear-text-btn'),
  startCameraBtn: document.getElementById('start-camera-btn'),
  stopCameraBtn: document.getElementById('stop-camera-btn'),
  cameraFeed: document.getElementById('camera-feed'),
  processingCanvas: document.getElementById('processing-canvas'),
  signAnimation: document.getElementById('sign-animation'),
  signText: document.getElementById('sign-text'),
  signDescription: document.getElementById('sign-description'),
  historyItems: document.getElementById('history-items'),
  clearHistoryBtn: document.getElementById('clear-history-btn'),
  modal: document.getElementById('sign-modal'),
  closeModal: document.querySelector('.close-modal'),
  modalSign: document.getElementById('modal-sign'),
  modalTitle: document.getElementById('modal-title'),
  modalDescription: document.getElementById('modal-description'),
  modalExamples: document.getElementById('modal-examples')
};

// Estado de la aplicación
const AppState = {
  videoStream: null,
  cameraInterval: null,
  signHistory: JSON.parse(localStorage.getItem('signHistory')) || [],
  currentAnimation: null,
  activeTab: 'text'
};

// Inicialización de la aplicación
function init() {
  setupEventListeners();
  renderHistory();
  showWelcomeSign();
}

// Configurar event listeners
function setupEventListeners() {
  // Cambio de pestañas
  DOM.textTab.addEventListener('click', () => switchTab('text'));
  DOM.cameraTab.addEventListener('click', () => switchTab('camera'));
  
  // Botones de texto
  DOM.translateBtn.addEventListener('click', handleTranslate);
  DOM.clearTextBtn.addEventListener('click', () => {
    DOM.inputText.value = '';
    DOM.inputText.focus();
  });
  
  // Botones de cámara
  DOM.startCameraBtn.addEventListener('click', startCamera);
  DOM.stopCameraBtn.addEventListener('click', stopCamera);
  
  // Historial
  DOM.clearHistoryBtn.addEventListener('click', clearHistory);
  
  // Modal
  DOM.closeModal.addEventListener('click', closeModal);
  window.addEventListener('click', (e) => {
    if (e.target === DOM.modal) closeModal();
  });
  
  // Tecla Enter para traducción
  DOM.inputText.addEventListener('keypress', (e) => {
    if (e.key === 'Enter') handleTranslate();
  });
}

// Cambiar entre pestañas
function switchTab(tab) {
  AppState.activeTab = tab;
  
  if (tab === 'text') {
    DOM.textTab.classList.add('active');
    DOM.cameraTab.classList.remove('active');
    DOM.textInputContainer.style.display = 'block';
    DOM.cameraInputContainer.style.display = 'none';
    stopCamera();
  } else {
    DOM.cameraTab.classList.add('active');
    DOM.textTab.classList.remove('active');
    DOM.textInputContainer.style.display = 'none';
    DOM.cameraInputContainer.style.display = 'block';
  }
}

// Manejar traducción de texto
function handleTranslate() {
  const text = DOM.inputText.value.trim().toLowerCase();
  
  if (!text) {
    showAlert('Por favor ingresa un texto para traducir');
    return;
  }
  
  translateTextToSign(text);
}

// Traducir texto a señas
function translateTextToSign(text) {
  // Limpiar animación previa
  if (AppState.currentAnimation) {
    clearInterval(AppState.currentAnimation);
    AppState.currentAnimation = null;
  }
  
  const words = text.split(' ');
  const outputSigns = [];
  const outputTexts = [];
  const outputDescriptions = [];
  
  words.forEach(word => {
    if (LSC_DATABASE[word]) {
      // Palabra conocida
      outputSigns.push(LSC_DATABASE[word].sign);
      outputTexts.push(word);
      outputDescriptions.push(LSC_DATABASE[word].description);
      addToHistory(word, LSC_DATABASE[word].sign, 'word');
    } else {
      // Deletrear palabra
      [...word].forEach(char => {
        if (LSC_ALPHABET[char]) {
          outputSigns.push(LSC_ALPHABET[char]);
          outputTexts.push(char);
          outputDescriptions.push(`Letra ${char.toUpperCase()} en LSC`);
          addToHistory(char, LSC_ALPHABET[char], 'letter');
        }
      });
    }
  });
  
  // Mostrar resultados
  if (outputSigns.length > 0) {
    showSign(outputSigns[0], outputTexts[0], outputDescriptions[0]);
    
    // Animar si hay múltiples señas
    if (outputSigns.length > 1) {
      let currentIndex = 1;
      AppState.currentAnimation = setInterval(() => {
        showSign(outputSigns[currentIndex], outputTexts[currentIndex], outputDescriptions[currentIndex]);
        currentIndex++;
        
        if (currentIndex >= outputSigns.length) {
          clearInterval(AppState.currentAnimation);
          AppState.currentAnimation = null;
        }
      }, 1500);
    }
  }
}

// Mostrar una seña
function showSign(sign, text, description) {
  DOM.signAnimation.textContent = sign;
  DOM.signText.textContent = text;
  DOM.signDescription.textContent = description;
  
  // Efecto visual
  DOM.signAnimation.classList.add('pulse');
  setTimeout(() => {
    DOM.signAnimation.classList.remove('pulse');
  }, 500);
}

// Agregar al historial
function addToHistory(text, sign, type) {
  // Evitar duplicados consecutivos
  const lastItem = AppState.signHistory[AppState.signHistory.length - 1];
  if (lastItem && lastItem.text === text && lastItem.sign === sign) return;
  
  // Limitar historial a 20 items
  if (AppState.signHistory.length >= 20) {
    AppState.signHistory.shift();
  }
  
  AppState.signHistory.push({ text, sign, type, timestamp: new Date() });
  saveHistory();
  renderHistory();
}

// Renderizar historial
function renderHistory() {
  DOM.historyItems.innerHTML = '';
  
  AppState.signHistory.forEach(item => {
    const historyItem = document.createElement('div');
    historyItem.className = 'history-item';
    historyItem.innerHTML = `
      <div class="sign">${item.sign}</div>
      <div class="letter">${item.text}</div>
    `;
    
    historyItem.addEventListener('click', () => showSignDetail(item));
    DOM.historyItems.appendChild(historyItem);
  });
}

// Mostrar detalles de seña
function showSignDetail(item) {
  if (item.type === 'word') {
    const signData = LSC_DATABASE[item.text];
    DOM.modalSign.textContent = signData.sign;
    DOM.modalTitle.textContent = item.text;
    DOM.modalDescription.textContent = signData.description;
    
    let examplesHTML = '<h3>Ejemplos de uso:</h3><ul>';
    signData.examples.forEach(example => {
      examplesHTML += `<li>${example}</li>`;
    });
    examplesHTML += '</ul>';
    DOM.modalExamples.innerHTML = examplesHTML;
  } else {
    DOM.modalSign.textContent = item.sign;
    DOM.modalTitle.textContent = `Letra ${item.text.toUpperCase()}`;
    DOM.modalDescription.textContent = `Seña correspondiente a la letra ${item.text.toUpperCase()} en el alfabeto manual LSC`;
    DOM.modalExamples.innerHTML = '<h3>Uso:</h3><ul><li>Para deletrear palabras</li></ul>';
  }
  
  DOM.modal.style.display = 'flex';
}

// Cerrar modal
function closeModal() {
  DOM.modal.style.display = 'none';
}

// Limpiar historial
function clearHistory() {
  AppState.signHistory = [];
  saveHistory();
  renderHistory();
}

// Guardar historial en localStorage
function saveHistory() {
  localStorage.setItem('signHistory', JSON.stringify(AppState.signHistory));
}

// Mostrar seña de bienvenida
function showWelcomeSign() {
  const welcomeSigns = ['hola', 'bienvenido', 'colombia'];
  const randomSign = welcomeSigns[Math.floor(Math.random() * welcomeSigns.length)];
  
  if (LSC_DATABASE[randomSign]) {
    showSign(
      LSC_DATABASE[randomSign].sign,
      randomSign,
      LSC_DATABASE[randomSign].description
    );
  }
}

// Manejo de la cámara
async function startCamera() {
  try {
    const stream = await navigator.mediaDevices.getUserMedia({ 
      video: { 
        width: { ideal: 1280 }, 
        height: { ideal: 720 },
        facingMode: 'user'
      } 
    });
    
    AppState.videoStream = stream;
    DOM.cameraFeed.srcObject = stream;
    
    DOM.startCameraBtn.disabled = true;
    DOM.stopCameraBtn.disabled = false;
    
    // Simular reconocimiento (en una app real usarías un modelo de IA)
    AppState.cameraInterval = setInterval(simulateSignRecognition, 3000);
    
  } catch (err) {
    console.error("Error al acceder a la cámara:", err);
    showAlert("No se pudo acceder a la cámara. Por favor asegúrate de permitir el acceso.");
  }
}

// Simular reconocimiento de señas
function simulateSignRecognition() {
  const signs = Object.keys(LSC_DATABASE);
  const randomSign = signs[Math.floor(Math.random() * signs.length)];
  
  showSign(
    LSC_DATABASE[randomSign].sign,
    randomSign,
    LSC_DATABASE[randomSign].description
  );
  
  addToHistory(randomSign, LSC_DATABASE[randomSign].sign, 'word');
}

// Detener cámara
function stopCamera() {
  if (AppState.videoStream) {
    AppState.videoStream.getTracks().forEach(track => track.stop());
    AppState.videoStream = null;
    DOM.cameraFeed.srcObject = null;
  }
  
  if (AppState.cameraInterval) {
    clearInterval(AppState.cameraInterval);
    AppState.cameraInterval = null;
  }
  
  DOM.startCameraBtn.disabled = false;
  DOM.stopCameraBtn.disabled = true;
}

// Mostrar alerta
function showAlert(message) {
  const alertDiv = document.createElement('div');
  alertDiv.className = 'alert';
  alertDiv.textContent = message;
  
  document.body.appendChild(alertDiv);
  setTimeout(() => alertDiv.remove(), 3000);
}

// Iniciar la aplicación cuando el DOM esté listo
document.addEventListener('DOMContentLoaded', init);
