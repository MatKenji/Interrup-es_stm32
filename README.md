# Estudos de Interruptores com STM32F411

Este projeto tem como objetivo estudar o uso de interruptores com o microcontrolador STM32F411 (Blackpill). Os interruptores serão conectados aos pinos B6, B7 e B8 do microcontrolador, enquanto os LEDs estarão conectados aos pinos A0, A1 e A2, cada um com um resistor de 330 ohms para limitação de corrente. Além disso, cada pino de entrada (B6, B7, B8) terá um filtro passa-baixa composto por um capacitor de 100nF em paralelo com um resistor de 220 ohms em série com o botão.

### Componentes Necessários

- Microcontrolador STM32F411 (Blackpill)
- LEDs (3 unidades)
- Resistores de 330 ohms (3 unidades)
- Botões (3 unidades)
- Capacitores de 100nF (3 unidades)
- Resistores de 220 ohms (3 unidades)
- Fonte de alimentação 5V
- Cabos de conexão
- Placa de desenvolvimento (por exemplo, ST-Link V2)

### Conexões

- **LEDs:**
  - A0 do STM32F411 -> LED + Resistor 330 ohms -> GND
  - A1 do STM32F411 -> LED + Resistor 330 ohms -> GND
  - A2 do STM32F411 -> LED + Resistor 330 ohms -> GND

- **Botões com Filtro Low-Pass:**
  - B6 do STM32F411 -> Resistor 220 ohms -> Botão -> GND
  - B7 do STM32F411 -> Resistor 220 ohms -> Botão -> GND
  - B8 do STM32F411 -> Resistor 220 ohms -> Botão -> GND
  - Capacitor de 100nF em paralelo com o botão.

![image](https://github.com/MatKenji/Interrup-es_stm32/assets/169562589/34595bda-5776-48ff-85c2-649a578236d7)

![image](https://github.com/MatKenji/Interrup-es_stm32/assets/169562589/11af5ec8-08d3-4599-8502-7cba59d6aaa7)


## Funcionamento Esperado

1. **LED Vermelho:**
   - Configurado para inverter seu estado (ligado/desligado) quando o botão conectado ao pino B6 é pressionado (detecção de falling edge).

2. **LED Azul:**
   - Permanece ligado apenas enquanto o botão conectado ao pino B7 é pressionado (detecção de rising ou falling edge).

3. **LED Branco:**
   - Fica ligado por um período determinado após o botão conectado ao pino B8 ser pressionado (detecção de falling edge).
  
   ![image](https://github.com/MatKenji/Interrup-es_stm32/assets/169562589/601b2c21-ff55-4ad0-b49d-7067576f478a)


### Configuração do Projeto

1. **STM32CubeMX:**
   - Configure os pinos GPIO necessários para os LEDs (A0, A1, A2) como saídas.
   - Configure os pinos GPIO necessários para os botões (B6, B7, B8) como entradas com pull-up interna ativada.

2. **Código na IDE:**
   - Implemente o código C para configurar interrupções nos pinos de entrada (B6, B7, B8) para detectar mudanças de estado dos botões.
   - Programe a lógica para controlar os LEDs conforme descrito acima, utilizando interrupções para garantir uma resposta rápida aos eventos de botão.


Este projeto proporcionará uma experiência prática valiosa no uso de interruptores com microcontroladores STM32F411, explorando conceitos como debounce e uso eficiente de GPIOs.

**Nota:** Os arquivos de código fornecidos neste repositório foram desenvolvidos usando STM32CubeIDE. Devido a limitações de minha experiência com o STM32CubeIDE, a importação direta do projeto para o Git pode não ter sido feita da maneira mais eficiente ou padronizada. 
