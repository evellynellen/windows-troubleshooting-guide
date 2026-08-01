<p align="center">

<img src="https://img.shields.io/badge/Windows%2011-D5A6BD?style=for-the-badge&logo=windows&logoColor=white">

<img src="https://img.shields.io/badge/PowerShell%205.1-D5A6BD?style=for-the-badge&logo=powershell&logoColor=white">

<img src="https://img.shields.io/badge/Status-In%20Progress-D5A6BD?style=for-the-badge">

<img src="https://img.shields.io/badge/License-MIT-D5A6BD?style=for-the-badge">

</p>

# 🖥️ Windows Troubleshooting Guide

Guia prático de resolução de problemas do Windows, documentando procedimentos utilizados em ambientes de Suporte Técnico, Service Desk e Infraestrutura.

---

## 📌 Objetivo

Este repositório reúne problemas comuns encontrados no Windows e suas respectivas soluções, utilizando ferramentas nativas do sistema e boas práticas de troubleshooting.

O objetivo é desenvolver habilidades práticas em:

- Diagnóstico de problemas
- Resolução de incidentes
- Administração do Windows
- Documentação técnica
- Atendimento de suporte

---

## 🛠️ Tecnologias e Ferramentas

- Windows 10
- Windows 11
- Windows PowerShell
- Prompt de Comando (CMD)
- Windows Recovery
- Event Viewer
- Device Manager
- Services
- Registry Editor

---

## 📚 Conteúdo

- BSOD (Tela Azul)
- Windows lento
- Disco em 100%
- Uso elevado de memória RAM
- Erros do Windows Update
- Driver com problema
- Restaurar arquivos do sistema
- Problemas de inicialização
- Rede sem Internet
- DNS
- Impressoras
- Bluetooth
- Áudio
- USB
- Firewall
- Backup
- Recuperação do sistema

---

## 📂 Estrutura do Projeto

```
windows-troubleshooting-guide/

├── bsod/
├── windows-update/
├── disk-100/
├── memory-high/
├── drivers/
├── network/
├── dns/
├── printer/
├── bluetooth/
├── audio/
├── firewall/
├── backup/
└── recovery/
```

---

## 📝 Modelo de Documentação

Cada problema segue o mesmo padrão.

### Problema

Descrição do erro.

### Sintomas

- ...
- ...

### Possíveis causas

- ...
- ...

### Diagnóstico

Comandos utilizados.

### Solução

Passo a passo completo.

### Resultado

Problema resolvido.

### Aprendizado

O que foi aprendido durante a resolução.

---

## 💻 Comandos úteis

```powershell
sfc /scannow

DISM /Online /Cleanup-Image /RestoreHealth

chkdsk /f

ipconfig /flushdns

ipconfig /release

ipconfig /renew

netsh winsock reset
```

---

## 🎯 Objetivos de Aprendizado

- Desenvolver raciocínio de troubleshooting
- Aprender ferramentas nativas do Windows
- Documentar procedimentos técnicos
- Simular atividades de Service Desk
- Criar um portfólio profissional

---

## 📈 Status

🚧 Em desenvolvimento.

Novos casos de troubleshooting serão adicionados continuamente.

---

## 📖 Licença

Projeto desenvolvido para fins educacionais e de portfólio.
