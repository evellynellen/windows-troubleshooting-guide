<p align="center">

<img src="https://img.shields.io/badge/Windows%2011-D5A6BD?style=for-the-badge&logo=windows&logoColor=white">

<img src="https://img.shields.io/badge/PowerShell%205.1-D5A6BD?style=for-the-badge&logo=powershell&logoColor=white">

<img src="https://img.shields.io/badge/Status-In%20Progress-D5A6BD?style=for-the-badge">

<img src="https://img.shields.io/badge/License-MIT-D5A6BD?style=for-the-badge">

</p>

# Windows Troubleshooting Guide

Uma base de conhecimento técnica que documenta procedimentos de solução de problemas do Windows, diagnósticos e soluções comumente realizados em ambientes de Suporte de TI e Service Desk.

Este projeto foca na resolução prática de problemas usando ferramentas nativas do Windows, utilitários de linha de comando e práticas de administração de sistemas.

---

Este repositório documenta incidentes comuns do Windows e suas resoluções, aplicando metodologias de solução de problemas usadas em ambientes profissionais de TI.

Os principais objetivos são:

- Desenvolver habilidades de solução de problemas
- Praticar administração do Windows
- Entender diagnósticos do sistema
- Criar documentação técnica
- Simular atividades de Service Desk
- Construir um portfólio profissional de TI

---

# Ambiente de Laboratório

Os cenários de solução de problemas são testados em ambientes controlados usando:

- Máquinas Virtuais Windows 10/11
- VirtualBox
- Ferramentas administrativas do Windows
- Utilitários de linha de comando
- Ambientes de usuário local

---

---

---

# Tecnologias e Ferramentas

## Sistemas Operacionais

- Windows 10
- Windows 11

## Ferramentas Administrativas

- Ambiente de Recuperação do Windows (WinRE)
- Visualizador de Eventos
- Gerenciador de Dispositivos
- Serviços
- Editor do Registro
- Gerenciador de Tarefas
- Gerenciamento de Disco

## Linha de Comando

- Prompt de Comando (CMD)
- PowerShell

---

# Troubleshooting Index

| Issue | Category | Status |
|------|----------|--------|
| Boot Loop | Startup | Completed |
| BIOS/UEFI Issues | Firmware | Completed |
| Windows Update Errors | Updates | In Progress |
| Driver Problems | Hardware | Planned |
| Blue Screen (BSOD) | System | Planned |
| Network Connectivity | Networking | Planned |
| DNS Issues | Networking | Planned |
| Printer Problems | Hardware | Planned |
| Bluetooth Issues | Hardware | Planned |
| Audio Problems | Hardware | Planned |
| System Recovery | Recovery | Planned |

---

## Modelo de Documentação

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

## Comandos úteis

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

## Objetivos de Aprendizado

- Desenvolver raciocínio de troubleshooting
- Aprender ferramentas nativas do Windows
- Documentar procedimentos técnicos
- Simular atividades de Service Desk
- Criar um portfólio profissional

---

## Status

🚧 Em desenvolvimento.

Novos casos de troubleshooting serão adicionados continuamente.

---

## Licença

Projeto desenvolvido para fins educacionais e de portfólio.
