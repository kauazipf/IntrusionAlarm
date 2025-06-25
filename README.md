
# 🔔 Alarme de Intrusão com ESP32

Este projeto é um **sistema simples de alarme de intrusão** desenvolvido na plataforma [Wokwi](https://wokwi.com), utilizando um microcontrolador **ESP32**, sensores básicos e atuadores para detectar movimento e alterações de luminosidade.

## 👨‍💻 Autores

- Caetano Matos Penafiel - RM557984
- Victor Egidio Lira - RM556653
- Kauã Ferino Zipf - RM558957

---

## 📌 Visão Geral

O projeto simula um alarme que é ativado quando há **detecção de movimento** ou **mudanças bruscas de luz ambiente**, indicando uma possível presença de intrusos. Ao detectar essas condições, o sistema:

- Acende um **LED vermelho** como alerta visual;
- Emite um som através de um **buzzer piezoelétrico** como alerta sonoro;
- Mostra informações no **Serial Monitor**.

---

## ⚙️ Componentes Utilizados

- ESP32 DevKit v4  
- Sensor de movimento PIR  
- Sensor de luminosidade (LDR)  
- Buzzer  
- LED vermelho  
- 2 resistores de 1kΩ  

---

## 🔌 Esquema de Ligações (Diagrama Wokwi)

O projeto foi montado no simulador Wokwi com os seguintes pontos de conexão:

### Conexões principais:

| Componente         | Pino ESP32 | Descrição                        |
|--------------------|------------|----------------------------------|
| PIR (movimento)    | GPIO 2     | Sinal digital de detecção        |
| Buzzer             | GPIO 16    | Alerta sonoro                    |
| LED vermelho       | GPIO 17    | Alerta visual                    |
| LDR (luminosidade) | GPIO 34    | Leitura analógica de luz         |
| PIR e LDR          | 3.3V / GND | Alimentação                      |

O projeto também utiliza resistores pull-down para o LDR e LED, garantindo leituras estáveis e segurança no circuito.

---

## 🧠 Lógica do Sistema

1. **Inicialização** do ESP32, sensores e pinos de saída.
2. A **leitura do PIR** verifica se há movimento próximo.
3. A **leitura do LDR** monitora a luminosidade ambiente (ex: abrir uma porta ou janela).
4. Caso o movimento ou uma queda brusca de luz seja detectada:
   - O **LED vermelho acende**.
   - O **buzzer toca**.
5. Caso contrário, os alertas permanecem desativados.
6. O **Serial Monitor** exibe logs úteis para debug e testes.

---

## 🛠️ Como Testar

1. Acesse [wokwi.com](https://wokwi.com).
2. Importe o projeto usando o diagrama JSON acima.
3. Faça upload do código C/C++ com a lógica do alarme (pode ser fornecido em outro momento).
4. Simule a detecção de movimento e alterações de luz.
5. Observe os alertas visuais e sonoros, bem como as mensagens no monitor serial.

---

## ✅ Possíveis Melhorias

- Enviar notificações via Wi-Fi/MQTT.
- Adicionar um teclado ou botão de desativação.
- Integrar com sistema de câmeras ou app mobile.
