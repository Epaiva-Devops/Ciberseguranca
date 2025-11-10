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

 

