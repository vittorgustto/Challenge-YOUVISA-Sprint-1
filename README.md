# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
  <a href="https://www.fiap.com.br/">
    <img src="./assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" style="border:0; width:40%; height:40%;">
  </a>
</p>

<br>


## Grupo 39

## 👨‍🎓 Integrantes: 
- <a href="https://www.linkedin.com/in/vittor-augusto/">Vitor Augusto Gomes</a>
- <a href="https://www.linkedin.com/in/jo%C3%A3o-vitor-lopes-beiro-59a007248/">João Vitor Lopes Beiro</a>

## 👩‍🏫 Professores:
### Tutor(a) 
- <a href="https://www.linkedin.com/in/leonardoorabona/">Leonardo Ruiz Orabona</a>
### Coordenador(a)
- <a href="https://www.linkedin.com/in/profandregodoi/">André Godoi Chiovato</a>


## 📜 Descrição

# 📘 Challenge YOUVISA – Sprint 1

**Plataforma Inteligente de Atendimento Multicanal**

Entrega: Definição do escopo e arquitetura inicial da solução
Instituição: FIAP
Empresa Parceira: YOUVISA

---

# 🧩 1. Justificativa do Problema

Empresas que atuam com emissão de vistos e serviços consulares enfrentam o desafio de atender grandes volumes de solicitações de forma rápida, segura e personalizada.
Atendimentos repetitivos e manuais sobre status de processos, envio de documentos e dúvidas gerais consomem tempo humano e aumentam custos operacionais.

Além disso, muitos usuários iniciam o contato por um canal (ex.: WhatsApp) e desejam continuar o atendimento em outro (ex.: e-mail ou Telegram) sem perder o histórico. Isso exige integração multicanal e consistência de dados.

A proposta deste projeto busca solucionar esses desafios com uma plataforma de atendimento inteligente multicanal, integrando chatbots, automação, visão computacional e análise de dados, garantindo:

- Redução de tarefas repetitivas por meio de automação (RPA);
- Atendimento contínuo entre múltiplos canais digitais;
- Validação automatizada de documentos via visão computacional;
- Segurança e privacidade dos dados coletados;
- Encaminhamento eficiente para atendimento humano quando necessário.

---

# 💡 2. Descrição da Solução Proposta

A solução proposta é uma plataforma cognitiva de atendimento multicanal, composta por chatbots inteligentes que atuam em diferentes canais (WhatsApp, Telegram, Web e E-mail), com integração em nuvem e automação de processos internos.

O sistema utilizará processamento de linguagem natural (NLP) para compreender intenções do usuário, e visão computacional para reconhecimento e validação de documentos (como passaportes e formulários de visto).

Quando o chatbot identificar dúvidas complexas ou falhas na validação documental, o atendimento será encaminhado automaticamente para um atendente humano, preservando o histórico de conversa e os dados do cliente.

Principais funcionalidades:

- Atendimento automatizado via chatbots (WhatsApp, Telegram e Web);
- Reconhecimento e validação de documentos por OCR (ex.: passaporte);
- Encaminhamento automático para agente humano;
- Integração de dados e histórico entre canais;
- Geração de relatórios e insights para otimização do atendimento.

---

# ⚙️ 3. Tecnologias e Ferramentas Utilizadas

| Categoria                                    | Tecnologia / Ferramenta                          | Justificativa                                                             |
| -------------------------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------- |
| **Linguagens**                               | Python, JavaScript                               | Python para IA e automação; JS para front-end e integrações.              |
| **NLP (Processamento de Linguagem Natural)** | Rasa / Dialogflow                                | Interpretação de intenções, análise de mensagens e respostas automáticas. |
| **Visão Computacional / OCR**                | OpenCV + EasyOCR / Google Vision API             | Extração e validação de dados de documentos enviados pelos usuários.      |
| **RPA (Automação de Processos)**             | Robocorp / UiPath                                | Automação de tarefas repetitivas, como preenchimento de formulários.      |
| **Infraestrutura em Nuvem**                  | AWS (Lambda, S3, API Gateway, DynamoDB) / Azure  | Escalabilidade, armazenamento seguro e integração entre módulos.          |
| **Banco de Dados**                           | DynamoDB / MongoDB                               | Armazenamento do histórico de conversas e dados do usuário.               |
| **Segurança e LGPD**                         | Criptografia TLS, autenticação IAM, anonimização | Proteção e privacidade dos dados de usuários.                             |
| **Ferramentas de Diagramação**               | diagrams.net / mermaid.js                        | Modelagem da arquitetura e fluxos UML.                                    |
| **Controle de Versão**                       | GitHub                                           | Versionamento, colaboração e entrega do projeto.                          |

---

# 🏗️ 4. Arquitetura da Solução

A arquitetura proposta segue um modelo modular em nuvem, com integração entre os principais componentes do sistema:

```
graph LR
  U[Usuário<br>(WhatsApp / Telegram / Web / Email)]
  A[Adaptadores de Canal]
  G[API Gateway / Roteador]
  N[NLP Engine<br>(Rasa/Dialogflow)]
  V[Serviço de Visão Computacional<br>(OCR / Validação)]
  R[RPA / Automação de Processos]
  D[Banco de Dados<br>(MongoDB / DynamoDB)]
  S[Armazenamento em Nuvem<br>(S3 / Blob Storage)]
  H[Atendimento Humano<br>(Painel Web)]
  B[Analytics / Relatórios]
  Sec[Segurança e IAM]

  U --> A --> G
  G --> N
  G --> V
  G --> R
  N --> D
  V --> D
  R --> D
  D --> B
  G --> H
  Sec -.-> G
```

# 🧠 Fluxo Resumido:

1. O usuário envia mensagens por um canal digital.
2. O adaptador direciona o conteúdo ao API Gateway, que centraliza o roteamento.
3. O motor de NLP interpreta a intenção e decide a ação (responder, pedir documento ou encaminhar).
4. Se o usuário enviar um documento, o módulo de visão computacional (OCR) faz a validação automática.
5. O histórico e resultados são salvos no banco de dados.
6. Casos complexos são encaminhados a um atendente humano.
7. Dados agregados são analisados e transformados em insights preditivos para melhoria contínua.

---

# 🧾 5. Estratégia de Coleta e Tratamento de Dados

📥 Dados coletados:

- Mensagens e intenções de usuários;
- Arquivos/documentos enviados (ex.: passaporte, formulário);
- Metadados de sessão (canal, idioma, horário, dispositivo);
- Logs de erros e eventos do chatbot.

🔒 Tratamento e privacidade:

- Todos os dados trafegam via TLS/HTTPS;
- Armazenamento criptografado em S3 e DynamoDB;
- Dados pessoais são pseudonimizados antes de análise;
- Política de retenção de dados com exclusão periódica;
- Conformidade com a LGPD, incluindo consentimento explícito do usuário antes da coleta de dados sensíveis.

---

# 🗺️ 6. Plano Inicial de Desenvolvimento

| Etapa                                    | Descrição                                                         | Resultado Esperado                                 |
| ---------------------------------------- | ----------------------------------------------------------------- | -------------------------------------------------- |
| **1. Definição de Escopo e Arquitetura** | Identificação das tecnologias e desenho da arquitetura inicial.   | Documento e diagrama prontos.                      |
| **2. Modelagem do Chatbot (NLP)**        | Estruturação dos fluxos de atendimento e intenções principais.    | Documento de intents e entidades.                  |
| **3. Integração de Canais**              | Configuração inicial dos adaptadores (Telegram, WhatsApp, Web).   | Documento explicativo e testes simulados.          |
| **4. Visão Computacional (OCR)**         | Planejamento da automação para leitura e validação de documentos. | Estratégia definida e testada com dados simulados. |
| **5. Estratégia de Handover Humano**     | Definição dos gatilhos e interface para atendimento humano.       | Desenho conceitual do painel de atendente.         |
| **6. Segurança e LGPD**                  | Aplicação de práticas de criptografia e anonimização.             | Política de segurança documentada.                 |

---

# 🔐 7. Segurança e Privacidade de Dados

- Conformidade com a Lei Geral de Proteção de Dados (LGPD);
- Criptografia de dados em trânsito (HTTPS) e em repouso (KMS/AES-256);
- Controle de acesso por papéis (IAM / RBAC);
- Logs de auditoria e alertas de acesso não autorizado;
- Exclusão programada de dados sensíveis após o prazo legal;
- Consentimento do usuário antes de processar informações pessoais.

---

# 📚 8. Referências

[Rasa Documentation](https://rasa.com/docs/)

[Telegram Bot API](https://core.telegram.org/bots/api)

[Twilio WhatsApp API](https://www.twilio.com/whatsapp)

[OpenCV Documentation](https://opencv.org/)

[EasyOCR](https://github.com/JaidedAI/EasyOCR)

[AWS Textract](https://aws.amazon.com/textract/)

[Robocorp RPA Framework](https://robocorp.com/)

[LGPD – Lei Geral de Proteção de Dados (Lei nº 13.709/2018)](https://www.gov.br/cidadania/pt-br/acesso-a-informacao/lgpd)

---

# ✅ 10. Conclusão

Esta documentação representa a primeira entrega do Challenge YOUVISA, apresentando uma proposta técnica detalhada e coerente para uma plataforma inteligente de atendimento multicanal, combinando NLP, visão computacional, automação de processos e segurança de dados.
O foco da Sprint 1 é garantir clareza de planejamento, coerência técnica e integração entre os módulos, preparando o grupo para as próximas etapas de implementação.

---

## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>.github</b>: Nesta pasta ficarão os arquivos de configuração específicos do GitHub que ajudam a gerenciar e automatizar processos no repositório.

- <b>assets</b>: aqui estão os arquivos relacionados a elementos não-estruturados deste repositório, como imagens.

- <b>config</b>: Posicione aqui arquivos de configuração que são usados para definir parâmetros e ajustes do projeto.

- <b>docs</b>: aqui estão todos os documentos do projeto que as atividades poderão pedir. Na subpasta "other", adicione documentos complementares e menos importantes.

- <b>scripts</b>: Posicione aqui scripts auxiliares para tarefas específicas do seu projeto. Exemplo: deploy, migrações de banco de dados, backups.

- <b>src</b>: Todo o código fonte criado para o desenvolvimento do projeto ao longo das 7 fases.

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).



## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>




