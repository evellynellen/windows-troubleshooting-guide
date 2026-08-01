# Falha de acesso ou configuração da BIOS/UEFI

## Impacto 

**Médio**

O usuário pode ficar impossibilitado de iniciar o sistema operacional , alterar configurações de hardware ou realizar instalações.

---

## Descrição 

Problemas relacionados ao acesso ou configuração do firmware BIOS/UEFI, incluindo falhas de inicialização, ordem de boot incorreta, configurações incompatíveis de Secure Boot e alteração entre modos Legacy e UEFI.

---

## Sintomas

- Fast Boot ativado reduzindo tempo para acessar o firmwaare
- bateria CMOS descarregada
- Configuração Secure Boot incompatívo
- Ordem de inicialização incorreta 
- Alteração de disco entre GPT e MBR

---

## Diagnóstico 

1. Confirmar fabricanre e modelo do equipamento.
2. Indentificar tecla de acesso (`Del`, `F2`, `F10`, `Esc`).
3. Verificar modo de inicialização: 
   - UEFI
   - Legacy/CSM
4. Validar formato do disco:
   - GPT
   - MBR
5. Conferir Secure Boot e Fast Boot.

---

## Solução

1. Acessar firmware pelo Windows:

`Configurações → Sistema → Inicialização avançada → Reiniciar agora → Solução de Problemas → Configurações de Firmware UEFI`

2. Ajustar prioridade de boot.
3. Substituir bateria CMOS caso data/hora sejam perdidas.
4. Ajustar Secure Boot conforme necessidade.
5. Confirmar compatibilidade entre modo de boot e sistema instalado.

---

## Ferramentas utilizadas

- BIOS/UEFI Setup
- Windows Recovery Environment (WinRE)
- Gerenciamento de Disco

---

## Comandos

```powershell
shutdown /r /o /t /0
