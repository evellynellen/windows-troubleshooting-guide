# Problemas de Inicialização

## Problema

O Windows não inicializa corretamente ou não consegue concluir o processo de boot. O problema pode se manifestar de diferentes formas, como travamento na tela de carregamento, reinicializações em loop, tela preta antes da área de trabalho ou falha na inicialização automática.

Esses sintomas podem estar relacionados a arquivos do sistema corrompidos, falhas de hardware, drivers incompatíveis, atualizações malsucedidas ou configurações incorretas de inicialização.

---

## Sintomas

O problema pode se manifestar de uma ou mais das seguintes formas:

- O computador trava na tela com o logotipo do fabricante (Dell, Lenovo, HP etc.) ou no logotipo do Windows.
- O sistema reinicia repetidamente antes de concluir a inicialização (boot loop).
- Tela preta antes da área de trabalho, com ou sem cursor do mouse.
- O Windows entra em **Reparo Automático** continuamente sem concluir a inicialização.
- Mensagens como **"Preparando Reparo Automático"**, **"Diagnosticando seu computador"** ou **"Reparando unidade"** permanecem indefinidamente.
- A inicialização demora excessivamente ou não é concluída.
- O computador permanece congelado durante o processo de boot.
- 
---

## Possíveis causas

- Arquivos de inicialização do Windows (BCD, Boot Manager ou MBR/GPT) corrompidos ou ausentes.
- Atualização do Windows interrompida ou malsucedida.
- Arquivos do sistema corrompidos.
- Disco rígido (HD) ou SSD com setores defeituosos ou falha iminente.
- Alterações recentes de hardware, como componentes mal conectados ou incompatíveis.
- Drivers incompatíveis ou corrompidos que impedem a inicialização do sistema.
- Configurações incorretas de BIOS/UEFI ou ordem de boot inadequada.
- Malware que comprometeu o processo de inicialização do Windows.
---

## Diagnóstico

### 1. Confirmar se o equipamento está energizado

Verifique se o computador foi ligado corretamente e se apresenta sinais de funcionamento:

- LEDs de energia acesos;
- Ventoinhas em funcionamento;
- Sons de inicialização (POST ou login do Windows);
- Atividade no disco (LED de armazenamento, quando disponível).

Essas verificações ajudam a determinar se o problema está relacionado à inicialização do sistema operacional ou a uma falha de hardware (fonte de alimentação, placa-mãe ou outros componentes).

---

### 2. Verificar o monitor e as conexões

- Confirme se o monitor está ligado.
- Verifique se o cabo HDMI, DisplayPort, VGA ou DVI está corretamente conectado.
- Teste outro cabo ou outro monitor, se possível.

---

### 3. Verificar se há mensagens de erro

Observe se durante a inicialização aparecem mensagens como:

- "Preparing Automatic Repair"
- "Diagnosing your PC"
- "No Bootable Device"
- "Operating System not found"

Essas mensagens fornecem indícios sobre a origem do problema.

---

### 4. Acessar o Ambiente de Recuperação do Windows (WinRE)

Caso o Windows não inicialize normalmente, interrompa a inicialização três vezes consecutivas para acessar o **Windows Recovery Environment (WinRE)**.

No ambiente de recuperação, utilize as opções de:

- Reparo de Inicialização;
- Restauração do Sistema;
- Prompt de Comando;
- Desinstalação de atualizações recentes.

---

### 5. Verificar a integridade do disco

No Prompt de Comando do WinRE, execute:

```cmd
chkdsk C: /f
```

para identificar e corrigir erros no sistema de arquivos.

---

### 6. Verificar arquivos do sistema

Ainda no Prompt de Comando, execute:

```cmd
sfc /scannow
```

Se necessário:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

### 7. Verificar configurações de boot

Acesse a BIOS/UEFI e confirme:

- Se o SSD/HD é reconhecido.
- Se a ordem de inicialização (Boot Order) está correta.
- Se não houve alterações recentes nas configurações de inicialização.

---

### 2. Testar combinações de teclado para "acordar" a tela

Antes de qualquer diagnóstico mais profundo, vale tentar:

```
Win + Ctrl + Shift + B
```

Esse atalho reinicia o driver de vídeo e pode "descongelar" a tela preta.

Também vale tentar:

```
Win + P
```

Para verificar se a saída de vídeo não está configurada para um monitor externo desconectado.

---

### 3. Verificar se o Explorador de Arquivos está rodando

1. Pressione `Ctrl + Shift + Esc` para abrir o Gerenciador de Tarefas (às vezes funciona mesmo com a tela preta).
2. Vá em **Arquivo → Executar nova tarefa**.
3. Digite:

```
explorer.exe
```

Se a área de trabalho aparecer depois disso, o problema era o processo do Explorador travado, não a placa de vídeo.

---

### 4. Verificar o Visualizador de Eventos

1. Pressione `Win + X`.
2. Abra **Visualizador de Eventos**.
3. Vá para:

```
Logs do Windows → Sistema
```

Procure eventos relacionados a driver de vídeo (geralmente da origem `nvlddmkm`, `amdkmdap` ou `Display`) próximos ao horário da falha.

---

### 5. Verificar o cabo e a conexão do monitor

- Teste outro cabo de vídeo (HDMI/DisplayPort/VGA), se possível.
- Conecte o monitor em outra entrada de vídeo do computador.
- Se for notebook, verifique se a tela preta some ao conectar um monitor externo (ajuda a isolar se o problema é a tela do notebook ou a placa de vídeo).

---

## Possíveis soluções

### 1. Executar o Reparo de Inicialização

Acesse o **Ambiente de Recuperação do Windows (WinRE)** e execute a opção **Reparo de Inicialização** para corrigir automaticamente problemas relacionados ao processo de boot.

---

### 2. Reparar arquivos do sistema

Abra o Prompt de Comando no WinRE e execute:

```cmd
sfc /scannow
```

Se necessário, execute também:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

### 3. Verificar a integridade do disco

Execute:

```cmd
chkdsk C: /f
```

Caso seja solicitado, reinicie o computador para concluir a verificação.

---

### 4. Reparar o carregador de inicialização

Se houver suspeita de corrupção do BCD ou do Boot Manager, utilize as ferramentas de reparo disponíveis no Ambiente de Recuperação do Windows.

---

### 5. Desinstalar atualizações recentes

Se o problema começou após uma atualização do Windows, remova a atualização em:

**Configurações → Windows Update → Histórico de atualizações → Desinstalar atualizações**

ou utilize a opção disponível no Ambiente de Recuperação.

---

### 6. Restaurar o Sistema

Utilize um ponto de restauração criado anteriormente para retornar o Windows a um estado funcional.

---

### 7. Verificar o hardware

Confirme se o SSD/HD é reconhecido pela BIOS/UEFI e verifique o encaixe de cabos e componentes internos, quando aplicável.

---

### 8. Redefinir ou reinstalar o Windows

Se nenhuma das soluções anteriores resolver o problema, considere redefinir o Windows mantendo os arquivos pessoais ou realizar uma instalação limpa do sistema operacional.
---

## 🧰 Ferramentas utilizadas

- Ambiente de Recuperação do Windows (Windows Recovery Environment - WinRE)
- Reparo de Inicialização (Startup Repair)
- Prompt de Comando (CMD)
- Verificador de Arquivos do Sistema (`sfc`)
- Deployment Image Servicing and Management (`DISM`)
- Check Disk (`chkdsk`)
- BIOS/UEFI
- Visualizador de Eventos (`eventvwr.msc`)

---

## 💡 Boas práticas

- Manter o Windows e os drivers sempre atualizados.
- Criar pontos de restauração antes de alterações importantes no sistema.
- Realizar backups periódicos dos dados.
- Desligar o computador corretamente, evitando interrupções forçadas durante atualizações.
- Monitorar a integridade do SSD/HD para identificar falhas precocemente.
- Verificar regularmente a saúde do hardware e manter a BIOS/UEFI atualizada, quando recomendado pelo fabricante.

---

## 📚 Referências

- Microsoft Learn – Troubleshoot Windows startup issues
- Microsoft Learn – Windows Recovery Environment (WinRE)
- Microsoft Learn – System File Checker (SFC)
- Microsoft Learn – DISM
- Microsoft Support – Startup Repair