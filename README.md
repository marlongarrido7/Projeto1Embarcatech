# Utilização da Placa BitDogLab com Raspberry Pi W 2040

## Integração de Teclado Matricial, LED RGB e Buzzer Passivo

### Autor do Projeto:
**Dr. Marlon da Silva Garrido**
Professor Associado IV (CENAMB - PPGEA)  
Universidade Federal do Vale do São Francisco (UNIVASF)

Este projeto faz parte das atividades do **EMBARCATECH 2024/25**.

---

### Objetivo:
O objetivo deste projeto é desenvolver um código em linguagem C para:
- Acionamento de periféricos, como um teclado matricial 4x4.
- Controle de LEDs RGB para sinalizações visuais.
- Acionamento de um buzzer passivo para feedback sonoro.

---

### Resumo do Funcionamento:
O programa realiza as seguintes funções principais:
- **Inicialização dos GPIOs**: Configura as linhas e colunas do teclado matricial e os pinos dos LEDs e buzzer.
- **Leitura do Teclado Matricial**: Detecta e identifica as teclas pressionadas.
- **Controle de LEDs**: Liga e desliga LEDs RGB com base em teclas especificadas.
- **Acionamento do Buzzer**: Gera sons em frequências determinadas e por duracoes específicas.

As funções principais do código estão descritas abaixo.

---

### Estrutura do Código e Funções:

#### **1. Inicialização de GPIOs**:
```c
void init_gpio();
```
Configura os GPIOs utilizados para as linhas e colunas do teclado matricial, além de inicializar os LEDs e o buzzer.

#### **2. Inicialização de LEDs e Buzzer**:
```c
void init_leds_and_buzzer();
```
Configura os GPIOs dos LEDs RGB e do buzzer como saídas e os inicializa desligados.

#### **3. Configuração do PWM para o Buzzer**:
```c
void set_buzzer_frequency(uint pin, uint frequency);
```
Configura o PWM no pino do buzzer para gerar uma frequência sonora específica.

#### **4. Emissão de Som pelo Buzzer**:
```c
void play_buzzer(uint pin, uint frequency, uint duration_ms);
```
Toca o buzzer com uma frequência específica por um tempo determinado (em milissegundos).

#### **5. Leitura do Teclado Matricial**:
```c
char scan_keypad();
```
Varre as linhas e colunas do teclado matricial para detectar e identificar a tecla pressionada.

#### **6. Controle de LEDs e Buzzer com Base nas Teclas Pressionadas**:
```c
void control_leds_and_buzzer(char key);
```
Executa ações com base na tecla pressionada:
- **A**: Liga o LED verde.
- **B**: Liga o LED azul.
- **C**: Liga o LED vermelho.
- **D**: Liga todos os LEDs.
- **#**: Toca o buzzer.

#### **7. Função Principal**:
```c
int main();
```
Inicializa os componentes e entra em um loop infinito, aguardando interações do teclado matricial para acionar LEDs ou o buzzer.

---

### Dependências:
- Raspberry Pi Pico SDK
- Biblioteca `pico/stdlib.h` para manipulação de GPIOs
- Biblioteca `hardware/pwm.h` para controle do PWM

### Simulação e Testes:
1. **Simulação no VSCode integrado ao Wokwi**: [Assista aqui](https://youtu.be/95_jIXYhDss)
2. **Testes diretos na placa BitDogLab**: [Assista aqui](https://youtube.com/shorts/_TYyaADbXDo)

---

### Como Executar:
1. Configure o ambiente de desenvolvimento do Raspberry Pi Pico com suporte ao SDK.
2. Clone o repositório para sua máquina local.
3. Compile o código utilizando o `cmake`.
4. Suba o binário gerado para o Raspberry Pi W 2040.
5. Conecte o hardware conforme os pinos descritos no código.

---

### Layout de Pinos:
- **Teclado Matricial**: GPIOs 17, 16, 18, 19 (linhas) e 20, 4, 9, 8 (colunas)
- **LED RGB**: GPIOs 11 (verde), 12 (azul) e 13 (vermelho)
- **Buzzer Passivo**: GPIO 21

---

### Licença:
Este projeto é de uso livre para fins acadêmicos e educacionais, com os devidos créditos ao autor.

