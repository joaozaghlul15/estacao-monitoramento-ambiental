Projeto:
    Estação de Monitoramento Ambiental Inteligente

        Este projeto consiste no desenvolvimento de uma estação de monitoramento ambiental inteligente, capz dee realizar leitura de variaveis ambientais e fornecer alertas visuais e sonoros conforme as condições identificadas.
        O sistema tem com objetivo monitorar temperatura,  umidade relativa do ar e pressão atimosferica, além de calcular o indice de calor para identificar situações de maior desconforto termico.

Equipe:

    João Pedro Sousa Zaghlul --> 12221EBI018
    Julia Barbosa Okuzono --> 12121EAU015


Funcionalidades Previstas:

    Leitura de temperatura, umidade relativa e pressão atmosférica.
    Exibição das informações em um display OLED.
    Cálculo do índice de calor.
    Sinalização visual por LEDs.
    Alertas sonoros por buzzer.
    Botões para interação com o sistema.
    Lembretes de hidratação em condições de maior calor.

Hardware:

    STM322F411 Black Pill --> Unidade Central de Processamento.
    BME280 --> Sensor de Medição de Temperatura, Umidade Relativa e Pressão Atmosferica
    LED SSD1306 --> Display Led para a Exibição das Informações do Sistema
    LED Verde --> Indicação de Temperatura e índice de calor em condição normal
    LED Vermelho --> Alerta de temperatura ou indice de calor elevado
    LED Amarelo --> Lembrete de hidratação em condições de maior calor (tem dois tipos de indicação quue varia de accordo com a temperatura, Aceso -> 27 °C a 31,9 °C; Piscando -> => 32 °C)
    Buzzer ativo 3,3V --> Emissão de Alerta Sonoro (temperaturas baixas e normais permanece desligado, na faixa de 27 °C a 31,9 °C ele emite 1 bipe a cada intervalo de 60 minutos, servindo como aviso de temperatura e lembrete parrra o consumo d'agua. Já em temperaturaas altas => 32 °C ele emite três bipes curtos a cada intervalo de 30 minutos)
    Transistor NPN BC337 --> acionamento do buzzeer
    Botão 1 Tactavel --> Interação com o usuario (Silenciar o boozzer, mas apenas na faixa de temperatura que ele se encontra no momento do acionamento, sempre que muda de faixa ele reinicia)
    Botâo 2 Tactavel --> Interação com o Usuario (1 click <2s Alterna as informações apresentadas no OLED; 1 click =>5s reinicia e reconfigura o sensor de temperatura e imprimi uma mensagem de reinicialização)
    Resistores de 1 kΩ (3U) --> Limmitação de corrente dos LEDs
    Resistor de 1 kΩ --> Limitação da corrente da base do transistor
    Resistores de 4,7 kΩ (2 unidades) --> Pull-up do barramento I²C, se o mudulo nao possuir
    Resistor de 100 kΩ --> Pull-down da base do transistor (ajuda a evitar que o transistor ligue involuntariamente e faça o buzzer emitir sons inesperados durante a inicialização do sistema.)
    2 Capacitores de 100 nF --> Desaclopamento da alimentação (1 para o conector do BME280 e 1 para o conector do OLED SSD1306)
    Capacitor de 10 µF --> Estabilização local da alimentação
    Headers fêmea 1×20 --> Conexão da Black Piill a PCB
    Conectores para Sensore e Display --> Conexão dos modulos a PCB

Ferramentas de Desenvolvimento:

    Ubuntu (WSL)
    Visual Studio Code
    ARM GCC (arm-none-eabi-gcc)
    GNU Make
    GDB (gdb-multiarch)
    OpenOCD
    Git e GitHub
    A decidir(Esquematico e PCB)

Organização do Repositorio:

    estacao-monitoramento-ambiental/
    ├── docs/
    ├── firmware/
    │   ├── drivers/
    │   │   ├── bme280/
    │   │   └── ssd1306/
    │   ├── inc/
    │   ├── linker/
    │   ├── src/
    │   └── startup/
    ├── hardware/
    │   ├── pcb/
    │   └── schematic/
    ├── tests/
    └── README.md

Desenvolvimento:

Mapa de Pinos do STM32:

Digrama de funcionamento do sistema:

Status do projeto:

    - [x] Criação do repositório GitHub.
    - [x] Configuração inicial do ambiente Ubuntu.
    - [x] Organização inicial das pastas.
    - [ ] Desenvolvimento do esquemático eletrônico.
    - [ ] Desenvolvimento da PCB.
    - [ ] Implementação do firmware.
    - [ ] Integração dos componentes.
    - [ ] Testes e validação.
    - [ ] Documentação final.