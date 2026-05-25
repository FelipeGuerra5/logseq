- [link](https://questoes.grancursosonline.com.br/aluno/simulado/24072913/resolver)
- # Questões
	- **10** Julgue os seguintes itens, a respeito dos algoritmos RSA e AES e de noções de criptografia.
	  collapsed:: true
	  O RSA é suscetível a um ataque conhecido como ataque de Wiener, que pode expor a chave privada de um sistema criptográfico RSA se os parâmetros utilizados para definir a chave privada forem considerados pequenos, e consequentemente, tido como matematicamente inseguros. #card
		- **Correto**
		- **RSA** Rivest Shamir Adleman -> cryptografia assimétrica com chave publica privada, utilizada em sua maioria em sites com https mais lento do que AES
		- **AES** Advanced Encryption Standard -> Utiliza uma única chave e, mais rapido e simetrico.
		- Ataque de **Wiener** é umna ataque que se vale de um expoente d privado, se este é pequeno: d<1/3n^1/4
	- **16**
	  collapsed:: true
	  Com relação a redes peer-to-peer (P2P), julgue os itens subsecutivos.
	  O principal objetivo de se usar DHT (distributed hash table) em redes P2P descentralizadas e estruturadas é permitir que cada peer tenha informação total sobre seus vizinhos. #card
		- Errada
		- **DHT** Distributed Hash Tables -> São tabelas que visão retornar a informação de maneira mais eficiente, sem que haja um prejuizo de tempo e NÃO para que haja conhecimento de todos os vizinhos, o que contraria o uso de rede P2P estruturada, o DHT evita a busca por flooding massivo, ou quase o elimina.
		- Lembrando que em redes P2P Desestruturadas o Flooding é o método utilizado.
		-
	- **17**
	  collapsed:: true
	  Em relação às estruturas de controle e de fluxo de execução, julgue os itens seguintes.
	  O laço do-while será executado sempre que a condição for falsa e terminará quando esta for verdadeira, ao passo que o laço repeat-until será executado sempre que a condição for verdadeira e terminará quando esta for falsa. #card
		- Errado
		- o loop do while e repeate until são implementados assim:
			- ```js 
			  do {} while (condition)
			    
			  // diferente de
			  while (condition) {}
			  //ou
			  for (condition) {}
			  ```
			- ```Pascal
			  repeat {} until (consdition)
			  ```
	- **18**
	  collapsed:: true
	  Existem diversas técnicas para descompilar programas maliciosos. Conforme a característica de um malware, essas técnicas podem ou não ser utilizadas. A respeito desse assunto, julgue os seguintes itens.
	  Existem três técnicas chaves para a análise de malware: análise binária, análise de entropia e análise de strings. #card
		- Errado
		- Embora os items citados sejam tipos de análise de malware não são os principais, nem os chaves.
		- analise binária é um termo generico e pode ser utilizado em analise estatica ou dinamica
		- Analise de entropia -> é uma ferramenta na determinação da ofuscação de um malware e não uma téctica de depuração em sí.
		- Resposta correta:
		  background-color:: green
			- Analise Estática, Analise Dinamica, Analise de Memória.
			-
	- **21**
	  collapsed:: true
	  Com relação à governança de tecnologia da informação (TI), julgue os itens subsequentes.
	  O COBIT abrange controles acerca de gerência de central de serviços especificamente no domínio Entregar e Suportar. No ITIL v3, a central de serviços é tipificada como uma função do estágio Operação de Serviços. #card
		- Certo
		- **COBIT** -> Control Objectives for Information and Related Technologies  é um framework para governaça de TI
			- planning and organize PO
			- Acquire eand implemente AI
			- Deliver and Suport DS
			- Monitoring and Evaluate ME
		- **ITIL v3** -> Information Technology Infrastructure Library é um conjunto de boas praticas para genrenciamento de serviços de TI
			- estrategia de serviço
			- desenho de serviço
			- transição de serviço
			- operação de serviço
			- melhoria continua de serviço
		- Ou Seja: operação de serviço é o momento de suporte e entrega do ITIL v3 e  coicidde com a etapa de DS do COBIT 4.1
		  background-color:: green
	- **25**
	  background-color:: red
	  collapsed:: true
	  Com relação à norma ISO/IEC 27001:2006, julgue os itens a seguir.
	  Segundo a norma ISO/IEC 27001:2006, a organização deve elaborar uma declaração de aplicabilidade, detalhando os ativos dentro do escopo do SGSI e os seus proprietários, bem como as possíveis ameaças aplicadas a tais ativos e as vulnerabilidades por elas exploradas. #card
		- Errado
		- **SGSI** -> **Sistema de Gestão de Segurança da Infomação**
		- Embora a norma verse sobre segurança a declaração de aplicabilidade, **SoA** => **Statement of Application**, lista todos  os controles selecionados e se estão aplicados ou não, a etapa de possiveis ameaças e vulnerabilidades a ser exploradas fazerm parte da **ANALISE DE RISCO**
		- A **Declaração de Aplicabilidade (SoA – Statement of Applicability)** **não analisa os riscos** diretamente — ela **documenta as decisões tomadas após a análise de riscos**.
	- **27**
	  background-color:: red
	  collapsed:: true
	  Julgue os itens que se seguem, referentes a técnicas de comunicação, topologias, arquiteturas e protocolos relacionados às redes de computadores.
	  Para assegurar uma topologia livre da ocorrência de loops, o que é fundamental para que redes IEEE 802.5 funcionem adequadamente, os equipamentos de interconexão, como switches e pontes, trocam informações com a utilização do protocolo STP (Spanning Tree Protocol). #card
		- Errado,
		- **STP**  Spanning Tree Protocol -> é utilizado em 802.1D, (Redes Wifi), já o 802.5 utiliza **Token Ring**
		- ## 🧠  **Mapa Mental: Padrões IEEE 802 para Concursos (CESPE)**
		- ### 🟩  **📦 IEEE 802.3 – Ethernet (Cabeada)**
		- **Tipo de rede**: LAN com fio
		- **Tecnologia**: CSMA/CD (em versões antigas)
		- **Velocidades**: 10 Mbps até 10 Gbps+
		- **Camada OSI**: Física e Enlace (camada 1 e 2)
		- **Equipamentos**: Switches, cabos UTP/Fibra
		- **Situação**: Amplamente utilizada
		  
		  ---
		- ### 🟦  **📡 IEEE 802.11 – Wi-Fi (Sem fio)**
		- **Tipo de rede**: WLAN (Wireless LAN)
		- **Subpadrões**:
			- **a**: 5 GHz, 54 Mbps
			- **b/g**: 2.4 GHz, 11/54 Mbps
			- **n**: 2.4 e 5 GHz, até 600 Mbps
			- **ac**: 5 GHz, até 1 Gbps+
			- **ax**: (Wi-Fi 6), até 9.6 Gbps
		- **Segurança**: WEP ❌, WPA, WPA2 ✅, WPA3 ✅
		- **Tecnologia**: CSMA/CA, OFDM
		- **Camada OSI**: 1 e 2
		  
		  ---
		- ### 🟨  **🌐 IEEE 802.1Q – VLAN (Virtual LAN)**
		- **Função**: Marcação de VLANs em redes Ethernet
		- **Tag VLAN**: Inserida no quadro Ethernet
		- **Trunk vs Access**: Comunicação entre switches
		- **Importante em redes corporativas**
		  
		  ---
		- ### 🟥  **🌲 IEEE 802.1D – STP (Spanning Tree Protocol)**
		- **Função**: Prevenir *loops* de camada 2
		- **Estados da porta**: Blocking, Forwarding, Learning, Listening
		- **Bridge raiz**: eleita com base no menor ID
		- **Evolução**: 802.1w (RSTP) – mais rápido
		  
		  ---
		- ### 🟫  **🔐 IEEE 802.1X – Controle de acesso**
		- **Função**: Autenticação de usuários na rede (ex: Wi-Fi corporativo)
		- **Usado com**: WPA2-Enterprise
		- **Componentes**:
			- Supplicant (usuário)
			- Authenticator (switch/AP)
			- Authentication Server (RADIUS)
			  
			  ---
		- ### ⚪  **🌀 IEEE 802.5 – Token Ring (Obsoleto)**
		- **Tipo de rede**: LAN em anel lógico
		- **Tecnologia**: Passagem de token
		- **Velocidade**: 4 ou 16 Mbps
		- **Situação**: Obsoleta – raramente cobrada
		  
		  ---
		- ## 🎯 Foco para CESPE:
		  
		  ✅ 802.3
		  
		  ✅ 802.11
		  
		  ✅ 802.1Q
		  
		  ✅ 802.1D
		  
		  ☑️ 802.1X
		  
		  ❌ 802.5 (obsoleto, só por comparação)
	- **28**
	  background-color:: yellow
	  collapsed:: true
	  Julgue os itens que se seguem, referentes a técnicas de comunicação, topologias, arquiteturas e protocolos relacionados às redes de computadores.
	  Considerando-se o endereçamento IPv4 das redes com arquitetura TCP/IP e sabendo-se que o endereço de um host em uma sub-rede é 182.44.82.16/27, é correto afirmar que os endereços 182.44.82.158 e 182.44.82.159 representam hosts em uma mesma sub-rede. # card
		- O ultimo número, 27 quer dizer que os primeiros 27 digitos são para o endereçamento da sub-rede e que depois disso os endereços não liberados. sendo assim:
			- ``` js
			  11111111.11111111.1111111.11100000
			  // sendo addim existem 00000 5 bits para o endereço: dos quais
			  - o primeiro valido é a partir do 16 e o último sera para broadcast,
			  em 5 bits temos 2^5  = 32 combinações, ou seja 32 endereços, menos o de broadcast,
			    158 e 159 não entrarão neste subrede
			  ```
			-