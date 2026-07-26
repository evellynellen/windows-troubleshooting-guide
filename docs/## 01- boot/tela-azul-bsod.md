# 💙 Tela Azul (BSOD)

## 📌 Problema

A Tela Azul da Morte (Blue Screen of Death - BSOD) ocorre quando o Windows encontra um erro crítico que impede o sistema de continuar funcionando com segurança. Para evitar danos, o computador é interrompido e reiniciado.

---

## 👤 Sintomas

O usuário pode relatar:

- O computador reinicia inesperadamente.
- Uma tela azul aparece com uma mensagem de erro.
- O Windows entra em um ciclo de reinicialização.
- O sistema trava durante o uso.

---

## 🔍 Possíveis causas

- Drivers incompatíveis ou corrompidos.
- Atualizações do Windows com falhas.
- Memória RAM com defeito.
- Problemas no SSD ou HD.
- Arquivos do sistema corrompidos.
- Superaquecimento do computador.
- Hardware incompatível.

---

## 🛠️ Diagnóstico

### 1. Anotar o código de erro

Exemplos:

- CRITICAL_PROCESS_DIED
- IRQL_NOT_LESS_OR_EQUAL
- MEMORY_MANAGEMENT
- SYSTEM_SERVICE_EXCEPTION

Esses códigos ajudam a identificar a causa do problema.

---

### 2. Verificar o Visualizador de Eventos

1. Pressione `Win + X`.
2. Abra **Visualizador de Eventos**.
3. Vá para:

```
Logs do Windows → Sistema
```

Procure eventos marcados como **Erro** ou **Crítico** próximos ao horário da falha.

---

### 3. Verificar arquivos do sistema

Abra o Prompt de Comando como Administrador e execute:

```cmd
sfc /scannow
```

---

### 4. Reparar a imagem do Windows

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

### 5. Verificar o disco

```cmd
chkdsk C: /f
```

Pode ser necessário reiniciar o computador.

---

### 6. Testar a memória RAM

Pressione:

```
Win + R
```

Digite:

```
mdsched.exe
```

Escolha reiniciar para verificar a memória.

---

## ✅ Possíveis soluções

- Atualizar drivers.
- Desinstalar drivers recentes.
- Executar SFC e DISM.
- Atualizar o Windows.
- Verificar a integridade do SSD/HD.
- Testar a memória RAM.
- Restaurar o sistema para um ponto anterior.

---

## 🧰 Ferramentas utilizadas

- Visualizador de Eventos
- Prompt de Comando
- Windows Memory Diagnostic
- Gerenciador de Dispositivos
- Windows Update

---

## 💡 Boas práticas

- Manter o Windows atualizado.
- Instalar drivers apenas de fontes confiáveis.
- Monitorar a temperatura do computador.
- Fazer backups regularmente.

---

## 📚 Referências

- Microsoft Learn
- Documentação oficial da Microsoft