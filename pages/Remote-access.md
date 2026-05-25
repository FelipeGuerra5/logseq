- #[[Ubuntu Server]]
- # Chat
	- Perfeito. Vamos seguir com **WireGuard**.
	  
	  Base técnica: documentação oficial do WireGuard ([https://www.wireguard.com/quickstart/](https://www.wireguard.com/quickstart/)) e implementação padrão em Linux (kernel + `wg`/`wg-quick`).
	  
	  ---
	- ## 🧭 Etapa 1 — Instalar o WireGuard no servidor Ubuntu
	  
	  Execute no servidor:
	  
	  ```
	  sudo apt update
	  sudo apt install wireguard
	  ```
	- ### ✔️ O que isso faz
	- Instala o módulo e ferramentas (`wg`, `wg-quick`)
	- Base: repositórios oficiais do Ubuntu (pacote `wireguard`)
	  
	  ---
	- ## 🔍 Validação (obrigatória)
	  
	  Execute:
	  
	  ```
	  wg --version
	  ```
	- ### Resultado esperado
	- Deve retornar versão do WireGuard (ex: `wireguard-tools v1.x`)
	  
	  ---
	- ## 👉 Próximo passo
	  
	  Após confirmar que o comando funcionou, me diga **“ok”**.
	  
	  (Se der erro, cole o erro — não avançamos sem validar)
	  
	  OK
	  
	  Perfeito. Prosseguindo.
	  
	  ---
	- ## 🧭 Etapa 2 — Gerar as chaves (servidor)
	  
	  Execute no servidor:
	  
	  ```
	  wg genkey | tee privatekey | wg pubkey > publickey
	  ```
	  
	  ---
	- ### ✔️ O que isso faz
	- `wg genkey` → gera chave privada
	- `tee privatekey` → salva a chave privada em arquivo
	- `wg pubkey` → gera a chave pública a partir da privada
	- `> publickey` → salva a chave pública
	  
	  **Base técnica:** funcionamento definido no utilitário `wg` (documentação oficial do WireGuard)
	  
	  ---
	- ### 🔐 Ajustar permissões (obrigatório)
	  
	  ```
	  chmod 600 privatekey
	  ```
	  
	  ✔️ Isso restringe acesso à chave privada (boa prática de segurança em sistemas Unix)
	  
	  ---
	- ### 🔍 Validação
	  
	  Mostre as chaves:
	  
	  ```
	  cat privatekey
	  cat publickey
	  ```
	- #### Resultado esperado
	- Dois valores longos em base64 (strings aleatórias)
	  
	  ---
	- ### ⚠️ Importante
	- **Nunca compartilhe a privatekey**
	- A **publickey será usada depois no cliente**
	  
	  ---
	  
	  👉 Quando terminar, diga **“ok”**.
	  
	  OK
	  
	  Perfeito. Continuando.
	  
	  ---
	- ## 🧭 Etapa 3 — Criar a interface WireGuard no servidor
	  
	  Vamos criar o arquivo de configuração.
	  
	  Execute:
	  
	  ```
	  sudo nano /etc/wireguard/wg0.conf
	  ```
	  
	  ---
	- ### 🧾 Conteúdo do arquivo
	  
	  **Cole exatamente isso (substituindo apenas a chave privada):**
	  
	  ```
	  [Interface]
	  Address = 10.0.0.1/24
	  ListenPort = 51820
	  PrivateKey = SUA_PRIVATE_KEY
	  ```
	- #### ✔️ Substituição obrigatória
	- `SUA_PRIVATE_KEY` → conteúdo do arquivo `privatekey`
	  
	  ---
	- ### ✔️ O que cada linha faz
	- `Address`
	  
	  Define IP interno da VPN (rede virtual)
	  
	  **Base:** modelo de rede do WireGuard (interface layer 3)
	- `ListenPort`
	  
	  Porta UDP usada pelo WireGuard
	  
	  **Base:** protocolo UDP definido pelo WireGuard
	- `PrivateKey`
	  
	  Identificação criptográfica do servidor
	  
	  **Base:** criptografia Curve25519 (WireGuard)
	  
	  ---
	- ### 🔐 Ajustar permissão (obrigatório)
	  
	  ```
	  sudo chmod 600 /etc/wireguard/wg0.conf
	  ```
	  
	  **Base:** proteção de segredo em sistemas Unix
	  
	  ---
	- ### 🔍 Validação
	  
	  Execute:
	  
	  ```
	  sudo cat /etc/wireguard/wg0.conf
	  ```
	  
	  Confirme:
	- A chave foi colada corretamente
	- Não há espaços extras ou linhas quebradas
	  
	  ---
	  
	  👉 Quando terminar, diga **“ok”**.
	  
	  (Não avançamos sem isso correto)