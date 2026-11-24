# MicroClima IoT — SaaS de Gestão e Automação Inteligente de Estufas (IoT)

O **MicroClima IoT**, é uma plataforma SaaS (Software as a Service) desenvolvida para aprimorar meus conhecimentos sobre desenvolvimento de software. O sistema unifica a coleta de dados de sensores IoT em tempo real, a visualização analítica do microclima e o controle dinâmico da irrigação em um painel simples e intuitivo.

---

## O Problema e a Solução 

### O Problema
Produtores agrícolas e gestores de estufas enfrentam desafios constantes na manutenção da produtividade e uso eficiente de recursos:
* **Perdas por desequilíbrio térmico e hídrico:** Falta de visibilidade instantânea das variações de temperatura e umidade.
* **Desperdício de água e energia:** Irrigação realizada em horários ineficientes ou por estimativas visuais.
* **Falta de controle centralizado:** Dificuldade em gerenciar múltiplos sensores e estufas com diferentes tipos de cultivo simultaneamente.

### A Solução MicroClima IoT
O AgroGreen resolve esses gargalos fornecendo:
* **Telemetria em Tempo Real:** Leitura constante de parâmetros climáticos vitais por estufa e por sensor.
*  **Irrigação Híbrida Inteligente:** Alternância entre o **Modo Automático** (agendamento de regas programadas com duração controlada) e o **Modo Manual** (acionamento imediato da bomba).
* **Decisões Baseadas em Dados:** Histórico visual em gráficos para identificação de padrões climáticos e prevenção de estresse vegetal.

---
## Requerimentos de Hardware

* ESP32
* Sensor DHT
* Cabos para conexão

## Requerimentos de Software

* Node.js
* Docker 
* PlatformIO | Arduino IDE

---

## Tecnologias Utilizadas por Camada

A arquitetura do sistema é dividida em módulos independentes, desacoplados e conteinerizados, garantindo escalabilidade e facilidade de manutenção.

### Front-end (Client-Side)
* **HTML5 & CSS3:** Estruturação semântica e estilização moderna com suporte completo a *CSS Grid*, *Flexbox* e variáveis CSS para suporte a temas.
* **JavaScript (ES6+ Vanilla):** Manipulação dinâmica do DOM, controle do estado da aplicação sem dependência de frameworks pesados e requisições assíncronas via `Fetch API`.
* **Chart.js:** Biblioteca JavaScript para renderização e atualização dinâmica dos gráficos de histórico de temperatura e umidade.
* **FontAwesome v6:** Iconografia contextual para identificação de status, atuadores e sensores na interface.

### Back-end & Servidor de Aplicação
* **Node.js:** Ambiente de execução assíncrono e baseado em eventos, ideal para lidar com conexões concorrentes do ecossistema IoT.
* **API RESTful (Express.js):** Camada de serviços responsável por prover os endpoints da aplicação, incluindo o endpoint centralizador `POST /dados` para sincronização de estado.
* **Orquestração de Regras de Irrigação:** Módulo encarregado de processar os agendamentos cadastrados pelo usuário e disparar os comandos para os atuadores.

### Camada de Integração IoT & Hardwares
* **Protocolo HTTP / MQTT:** Comunicação leve para recebimento dos dados de telemetria enviados pelos microcontroladores (ex: ESP32 / Arduino).
* **Mapeamento por Serial ID:** Associação lógica do **Código Serial** do hardware físico com a respectiva estufa e regras de acionamento.

### Conteinerização & Infraestrutura (Docker)
* **Docker & Docker Compose:** Todo o ambiente do AgroGreen (Front-end, Back-end e Banco de Dados) é empacotado em contêineres Docker isolados. Isso garante que a aplicação rode com o mesmo comportamento em qualquer ambiente de desenvolvimento ou produção, eliminando problemas de compatibilidade de dependências.

---

## Como rodar o projeto
Para executar o projeto, é necessário certificar-se de que o Docker já esteja instalado. Após, execute os comandos a seguir:
```bash
git clone https://github.com/GPottratz/MicroClima-IoT.git
cd MicroClima-IoT
docker compose up -d
```
# Resultados

## Arquitetura do servidor
<img width="1920" height="1080" alt="arquitetura servidor (5)" src="https://github.com/user-attachments/assets/bcf050f3-49d0-4656-b5ac-e5e4a8eb6bdb" />

## Modelagem de dados
<img width="1920" height="1080" alt="usuario" src="https://github.com/user-attachments/assets/a82303e7-44bf-438e-9332-297aa68d83f1" />

## Hardware
<img width="879" height="879" alt="ESP32" src="https://github.com/user-attachments/assets/98f1ab20-f1f0-4471-bd87-cac862b02a3e" />

## Software
<img width="1920" height="872" alt="dashboard" src="https://github.com/user-attachments/assets/28b2e6b7-1e1d-4099-84e5-e4b541d7c4b0" />

---
## Sobre o Projeto 
O **MicroClima IoT** é um projeto autoral criado estritamente para fins de aprendizado, experimentação técnica e composição de portfólio profissional. Todos os dados exibidos são simulados ou coletados em ambiente de testes, sem qualquer finalidade comercial.

## Licença
MIT
