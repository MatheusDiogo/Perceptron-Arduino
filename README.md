<h1>Projeto de Detecção de Cores com Arduino e Perceptron</h1>

<p>Este projeto utiliza um Arduino para detectar cores e treinar um perceptron para classificar as cores baseando-se em leituras de um sensor de luminosidade (LDR). O sistema inclui LEDs RGB para iluminar o ambiente e um display LCD para fornecer feedback ao usuário.</p>

<h2>Materiais Necessários</h2>
<ul>
    <li><strong>Arduino Uno</strong> ou similar</li>
    <li><strong>Display LCD 16x2 com interface I2C</strong></li>
    <li><strong>LEDs RGB</strong> (com pinos de controle individuais para cada cor)</li>
    <li><strong>LEDs individuais</strong> (vermelho, verde e azul)</li>
    <li><strong>Sensor de Luminosidade (LDR)</strong></li>
    <li><strong>Resistor</strong> (10k ohms para o LDR)</li>
    <li><strong>Botões</strong> (para calibrar e confirmar)</li>
    <li><strong>Resistores</strong> (10k ohms para os botões)</li>
    <li><strong>Jumpers e fios de conexão</strong></li>
    <li><strong>Protoboard</strong></li>
    <li><strong>Fonte de alimentação para o Arduino</strong></li>
</ul>

![image](https://github.com/user-attachments/assets/de30a223-dace-4df4-b1e6-0023cf8bb7ea)

<h2>Funcionamento</h2>

<h3>Setup Inicial</h3>
<p>1. <strong>Configuração dos Pinos:</strong> Os LEDs RGB e LEDs individuais são conectados aos pinos digitais do Arduino. O sensor LDR é conectado a um pino analógico. Os botões são conectados a pinos digitais com pull-up interno ativado.</p>
<p>2. <strong>Configuração do LCD:</strong> O display LCD é inicializado e configurado para exibir mensagens.</p>
<p>3. <strong>Inicialização dos Pesos e Bias:</strong> Os pesos e bias do perceptron são inicializados aleatoriamente.</p>

<h3>Modo de Treinamento</h3>
<p>1. <strong>Treinamento de Cores:</strong> O usuário pode treinar o sistema pressionando os botões correspondentes às cores desejadas. O Arduino acende o LED correspondente à cor e coleta leituras do LDR.</p>
<p>2. <strong>Calibração:</strong> O sistema também pode ser calibrado para as cores preta e branca. Durante a calibração, o sistema coleta leituras do LDR quando o botão de calibração é pressionado.</p>

![image](https://github.com/user-attachments/assets/f1bcb996-0596-49dc-918f-f79a88706e66)

<h3>Predição</h3>
<p>1. <strong>Recebimento de Dados:</strong> Após o treinamento, o sistema pode prever a cor de entrada com base nas leituras atuais do LDR. O usuário confirma o treinamento pressionando o botão de confirmação.</p>
<p>2. <strong>Predição e Exibição:</strong> O sistema usa o perceptron treinado para prever a cor com base nas leituras do LDR e exibe a cor predita no display LCD.</p>

![image (1)](https://github.com/user-attachments/assets/ddb5fdb4-cf43-478b-a086-e0864a927c6a)

<h2>Código</h2>
<p>O código para o Arduino é dividido em várias funções principais:</p>

<ul>
    <li><strong><code>setup()</code></strong>: Inicializa os pinos, o display LCD, e o sensor LDR. Define os LEDs e botões.</li>
    <li><strong><code>loop()</code></strong>: Executa continuamente o código de treinamento e predição. Monitora os botões e realiza a calibração e treinamento conforme necessário.</li>
    <li><strong><code>setColor()</code></strong>: Define a cor do LED RGB.</li>
    <li><strong><code>controle_leds()</code></strong>: Controla o estado dos LEDs.</li>
    <li><strong><code>controle_lcd()</code></strong>: Atualiza o display LCD com mensagens.</li>
    <li><strong><code>captura_dados()</code></strong>: Coleta dados do LDR.</li>
    <li><strong><code>receber_luminosidade()</code></strong>: Recebe e processa leituras de luminosidade para calibração e treinamento.</li>
    <li><strong><code>inicializarPesosBias()</code></strong>: Inicializa os pesos e bias do perceptron.</li>
    <li><strong><code>ativacao()</code></strong>: Função de ativação do perceptron.</li>
    <li><strong><code>treinarPerceptron()</code></strong>: Treina o perceptron com base nas leituras.</li>
    <li><strong><code>preverPerceptron()</code></strong>: Faz previsões usando o perceptron treinado.</li>
</ul>

![Imagem do WhatsApp de 2024-06-19 à(s) 15 35 28_d9c5f27a](https://github.com/user-attachments/assets/a2fd6a8e-04fa-4d90-b797-c34a9cf219bd)

<h2>Como Usar</h2>
<ol>
    <li><strong>Carregue o código no Arduino:</strong> Use o Arduino IDE para compilar e carregar o código fornecido no seu Arduino.</li>
    <li><strong>Calibre o Sistema:</strong> Pressione o botão de calibração para definir as cores preta e branca.</li>
    <li><strong>Treine o Sistema:</strong> Pressione os botões correspondentes para treinar o sistema nas cores desejadas.</li>
    <li><strong>Realize Predições:</strong> Após o treinamento, o sistema pode prever a cor com base nas leituras atuais do LDR e mostrar o resultado no LCD.</li>
</ol>

Você pode encontrar a apresentação do projeto no <a href="https://drive.google.com/drive/u/2/folders/1Qbx11p6LOxqx_xfHMeIbv3NqFVKIwZ-T">link</a>.
