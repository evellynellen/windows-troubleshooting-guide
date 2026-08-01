# BSOD (Tela Azul da Morte)

## Problema

A Tela Azul da Morte (BSOD) é um erro crítico do Windows que ocorre quando o sistema operacional detecta uma falha grave, como problemas de hardware, drivers ou arquivos do sistema. Nessa situação, o Windows interrompe seu funcionamento, exibe um código de erro e reinicia o computador para evitar danos ao sistema ou perda de dados.

---

## Sintomas

O problema pode se manifestar de uma ou mais das seguintes formas:

- Tela azul repentina acompanhada de um código de erro (ex.: `IRQL_NOT_LESS_OR_EQUAL`, `PAGE_FAULT_IN_NONPAGED_AREA`, `SYSTEM_SERVICE_EXCEPTION`).
- Reinicialização automática logo após a exibição da tela azul.
- Travamento completo do sistema antes ou durante o reinício.
- Ocorrência recorrente da BSOD, geralmente ao iniciar o Windows, abrir um aplicativo específico ou executar tarefas que exigem mais do hardware.
- Ciclo de reinicialização (boot loop), em que o computador reinicia continuamente após a BSOD.

---

## Impacto

- Interrupção das atividades do usuário.
- Possível perda de dados não salvos.
- Indisponibilidade temporária do equipamento.
- Risco de recorrência caso a causa raiz não seja corrigida.
- 
---

## Possíveis causas

- Drivers desatualizados, corrompidos ou incompatíveis.
- Falhas de hardware (memória RAM, HD ou SSD).
- Arquivos do sistema do Windows corrompidos.
- Atualizações do Windows malsucedidas ou incompatíveis.
- Superaquecimento da CPU, GPU ou outros componentes.
- Conflitos entre softwares de baixo nível (antivírus, drivers ou ferramentas de virtualização).
- Configurações incorretas de BIOS/UEFI ou overclock instável.

---

## Diagnóstico

### 1. Anotar o código de erro da BSOD

Anote o código exibido na tela azul, pois ele fornece uma indicação inicial da causa do problema.

Exemplos:

- `CRITICAL_PROCESS_DIED`
- `IRQL_NOT_LESS_OR_EQUAL`
- `PAGE_FAULT_IN_NONPAGED_AREA`
- `MEMORY_MANAGEMENT`
- `SYSTEM_SERVICE_EXCEPTION`

---

### 2. Verificar o Visualizador de Eventos

1. Pressione `Win + X`.
2. Abra **Visualizador de Eventos** (`eventvwr.msc`).
3. Acesse:

```
Logs do Windows → Sistema
```

Procure eventos classificados como **Erro** ou **Crítico** registrados no mesmo horário em que ocorreu a BSOD.

---

### 3. Verificar arquivos de despejo de memória (Minidump)

Confirme se o Windows gerou arquivos de despejo em:

```
C:\Windows\Minidump
```

Esses arquivos podem ser analisados com ferramentas como **WinDbg** para identificar o driver ou componente responsável pela falha.

---

### 4. Verificar alterações recentes

Investigue se o problema começou após:

- Instalação de drivers;
- Atualizações do Windows;
- Instalação de novos programas;
- Alteração ou substituição de hardware.

---

### 5. Testar a memória RAM

Execute o **Diagnóstico de Memória do Windows**:

1. Pressione `Win + R`.
2. Digite:

```
mdsched.exe
```

3. Escolha reiniciar o computador para iniciar o teste.

---

### 6. Verificar a integridade do disco

Abra o Prompt de Comando como Administrador e execute:

```cmd
chkdsk C: /scan
```

Caso sejam encontrados erros, poderá ser necessário executar:

```cmd
chkdsk C: /f
```

---

### 7. Identificar drivers problemáticos

Se houver suspeita de falha em drivers, utilize o **Verificador de Driver** (`verifier.exe`) para identificar drivers incompatíveis ou corrompidos.

---

## Possíveis soluções

### 1. Atualizar ou reinstalar drivers

Atualize ou reinstale o driver relacionado ao código de erro identificado, principalmente drivers de:

- Vídeo (GPU)
- Rede
- Armazenamento (SATA/NVMe)
- Chipset

Utilize o **Gerenciador de Dispositivos** ou baixe a versão mais recente no site do fabricante.

---

### 2. Reparar arquivos do sistema

Abra o Prompt de Comando como Administrador e execute:

```cmd
sfc /scannow
```

Após a conclusão, execute:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

### 3. Verificar a memória RAM

Execute o **Diagnóstico de Memória do Windows** (`mdsched.exe`) para identificar possíveis falhas na memória.

---

### 4. Verificar a integridade do disco

Execute:

```cmd
chkdsk C: /f
```

Se necessário, reinicie o computador para concluir a verificação.

---

### 5. Remover atualizações recentes

Caso o problema tenha começado após uma atualização do Windows, desinstale a atualização em:

**Configurações → Windows Update → Histórico de atualizações → Desinstalar atualizações**

---

### 6. Restaurar o Sistema

Se houver um ponto de restauração disponível, restaure o Windows para uma data anterior ao início do problema.

---

### 7. Redefinir o Windows

Caso nenhuma das soluções anteriores resolva o problema, considere redefinir o Windows mantendo os arquivos pessoais ou realizar uma instalação limpa do sistema operacional.

---

## Como validar

- O computador inicializa normalmente.
- Nenhuma nova BSOD ocorre durante o uso.
- O Visualizador de Eventos não registra novos erros críticos relacionados ao problema.
- Todos os drivers estão funcionando corretamente no Gerenciador de Dispositivos.
- O sistema permanece estável após reinicializações e uso prolongado.

---

## Ferramentas utilizadas

- Visualizador de Eventos (`eventvwr.msc`)
- Prompt de Comando (CMD)
- Windows Memory Diagnostic (`mdsched.exe`)
- Verificador de Driver (`verifier.exe`)
- Gerenciador de Dispositivos
- Windows Update
- WinDbg (opcional, para análise de arquivos de despejo)

---

## Como validar

Após aplicar a solução, confirme que:

- O computador inicializa normalmente.
- Nenhuma nova BSOD ocorre durante o uso.
- O Visualizador de Eventos não registra novos erros críticos relacionados ao problema.
- O sistema permanece estável após várias reinicializações.
- Todos os dispositivos funcionam corretamente e não apresentam erros no Gerenciador de Dispositivos.

---

## Boas práticas

- Manter o Windows e os drivers sempre atualizados.
- Instalar drivers apenas de fontes oficiais ou do fabricante do equipamento.
- Monitorar a temperatura da CPU, GPU e demais componentes.
- Criar pontos de restauração antes de alterações importantes.
- Realizar backups periódicos dos dados.

---

## Observações

O código de erro exibido na BSOD é o principal ponto de partida para a investigação. Em conjunto com o Visualizador de Eventos e os arquivos de despejo de memória (Minidump), ele fornece informações essenciais para identificar a causa raiz e aplicar a solução adequada.

---

## Referências

- Microsoft Learn
- Documentação Oficial da Microsoft