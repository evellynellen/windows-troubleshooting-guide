# Uso de CPU/Disco em 100%

> **Categoria:** Performance
> **Nível de risco/impacto:** Médio (deixa a máquina lenta ou inutilizável, mas raramente causa perda de dados)
> **Aplicável a:** Windows 10 / Windows 11
> **Última atualização:** 25/07/2026
>
> ## 🩺 Sintomas

- Computador extremamente lento, travando ao abrir programas ou até o Explorer.
- Ventoinha em rotação alta constante.
- Gerenciador de Tarefas mostra CPU ou disco em 100% de uso mesmo sem programas abertos.

## 🔍 Possíveis causas

1. Processo específico consumindo recursos (ex: antivírus em varredura, atualização do Windows em segundo plano, indexação de busca).
2. Malware minerando criptomoeda ou executando em segundo plano.
3. Disco rígido (HDD) com fragmentação severa ou próximo da falha.
4. Serviço do Windows travado em loop (ex: `Superfetch/SysMain`, `Windows Search`).
5. Falta de memória RAM, forçando uso excessivo de memória virtual (paginação em disco).

## 🧪 Diagnóstico

**1. Abra o Gerenciador de Tarefas e identifique o processo culpado:**

```
Ctrl + Shift + Esc
```

Ordene por CPU e por Disco para ver qual processo está no topo.

**2. Para uma visão mais detalhada, use o Monitor de Recursos:**

```
resmon.exe
```

Ele mostra exatamente qual processo está lendo/gravando no disco e a que taxa.

**3. Verifique se é um serviço específico do Windows (comum: SysMain, Windows Search, Windows Update):**

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"} | Sort-Object DisplayName
```

**4. Descarte malware com uma varredura completa:**

```powershell
Start-MpScan -ScanType FullScan
```

## ✅ Solução

**Se o processo culpado for um serviço legítimo do Windows travado:**

```powershell
# Exemplo: reiniciar o serviço SysMain (Superfetch), comum causador de alto uso de disco
Restart-Service -Name SysMain
```

**Se for o Windows Search/indexação:**

```powershell
Restart-Service -Name WSearch
```

Se o problema for recorrente com a indexação, considere reconstruir o índice em `Painel de Controle > Opções de Indexação > Avançado > Reconstruir`.

**Se for falta de memória RAM (uso excessivo de paginação):**

- Feche processos desnecessários em segundo plano.
- Verifique se há memória suficiente para a carga de trabalho do usuário; considere upgrade de RAM se for recorrente.

**Se for malware confirmado:**

- Isole a máquina da rede.
- Execute a varredura completa e remova as ameaças encontradas.
- Escale para a equipe de segurança se houver indício de comprometimento mais amplo.

**Se for fragmentação/saúde do disco (apenas para HDD, não SSD):**

```powershell
defrag C: /A /V
```

> ⚠️ **Atenção:** nunca execute desfragmentação em SSDs — isso reduz a vida útil do disco sem benefício de performance.

## 🛡️ Prevenção

- Manter antivírus com varreduras agendadas fora do horário de uso intenso.
- Monitorar espaço em disco e saúde (S.M.A.R.T.) preventivamente.
- Padronizar máquinas com SSD quando possível, reduzindo gargalos de I/O.

## 📚 Referências

- [Documentação Microsoft — Monitor de Recursos](https://learn.microsoft.com/pt-br/windows-server/administration/windows-commands/resmon)
- [Documentação Microsoft — Start-MpScan](https://learn.microsoft.com/pt-br/powershell/module/defender/start-mpscan)
