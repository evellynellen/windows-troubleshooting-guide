# 🖤 Tela Preta (Black Screen)

## 📌 Problema

A Tela Preta (Black Screen) ocorre quando o Windows liga, mas o monitor não exibe nada além de uma tela preta — com ou sem cursor do mouse visível. Diferente da Tela Azul, geralmente não aparece nenhum código de erro, o que torna o diagnóstico um pouco mais indireto.

---

## 👤 Sintomas

O usuário pode relatar:

- A tela fica completamente preta após ligar o computador.
- É possível ver o cursor do mouse se movendo, mas nada mais aparece.
- A tela preta acontece depois de uma atualização do Windows ou de drivers de vídeo.
- O computador parece ligado (ventoinha funcionando, luzes acesas), mas o monitor não mostra nada.
- A tela fica preta por alguns segundos e depois volta ao normal.

---

## 🔍 Possíveis causas

- Driver de vídeo (placa de vídeo) corrompido, desatualizado ou incompatível.
- Monitor não detectado corretamente ou cabo de vídeo com mau contato.
- Atualização do Windows com falha, travada em segundo plano.
- Processo do Explorador de Arquivos (`explorer.exe`) travado ou não iniciado.
- Múltiplos monitores com a saída de vídeo configurada para o monitor errado.
- Placa de vídeo com defeito ou superaquecendo.

---

## 🛠️ Diagnóstico

### 1. Confirmar se o computador realmente ligou

Observe se há sons de inicialização, luzes do gabinete/notebook acesas e ventoinha girando. Isso ajuda a diferenciar um problema de vídeo de um problema de hardware mais grave (fonte, placa-mãe).

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

## ✅ Possíveis soluções

- Atualizar ou reinstalar o driver de vídeo pelo site do fabricante (NVIDIA, AMD, Intel).
- Reiniciar o processo `explorer.exe`, se for esse o caso.
- Desconectar monitores externos extras e testar apenas com um.
- Desfazer uma atualização recente do Windows, se a tela preta começou logo depois de instalá-la.
- Testar o monitor/cabo em outro computador para descartar defeito físico.
- Em notebooks, verificar se a tela preta persiste com um monitor externo (indica problema na tela ou no cabo flat interno).

---

## 🧰 Ferramentas utilizadas

- Gerenciador de Tarefas
- Visualizador de Eventos
- Gerenciador de Dispositivos
- Atalhos de teclado do Windows (`Win + Ctrl + Shift + B`, `Win + P`)

---

## 💡 Boas práticas

- Manter os drivers de vídeo atualizados direto pelo site do fabricante, não só pelo Windows Update.
- Evitar interromper atualizações do Windows no meio do processo.
- Verificar periodicamente os cabos de vídeo em máquinas de mesa (mau contato é uma causa comum e simples).

---

## 📚 Referências

- Microsoft Learn
- Documentação oficial da Microsoft
