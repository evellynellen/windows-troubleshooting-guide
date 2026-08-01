# Boot Loop - Reinicialização contínua do Windows

## Impacto 

**Alto**

O usuário fica impossibilitado de acessar o sistema operacional e utilizar o equipamento.

---

## Descrição 

Boot Loop ocorro quando o computador inicia o processo de carregamento do Windows, mas reinicia automaticamente antes de chegar à tela de login.

o clico pode acontecer continuamente, impedindo o acesso ao sistema.

---

## Sistemas

- Logo do Fabrincante ou Windows aparece e o computador reinicia
- Reinicialiçao acontecem repetidamente
- Sistema entra automaticamente no Ambiente de recuperação (WinRE)
- Tela azul pode aparecer antes do reinicio

---

## Possíveis causas

- Arquivos de inicialização corrompidos (BCD)
- Atualização do Windows malsucedida 
- Drivers incopatíveis
- Arquivos do sistema corrompidos
- Falha em armazenamentos (SSD/HDD)
- Problemas de memória RAM

---

## Diagnóstico

1. Confirmar se o problema ocorre anres ou depois do carregamento do Windows.
2. Verificar alterações recentes:
   - Atualizações 
   - Drivers
   - Instalação de softwares
   - alterações de hardware
3. Acessar o Ambiente de Recuperação do Windows (WinRE).
4. Executar testes:
   - Reparo Automático
   - Modo de Segurança
   - Prompt de Comando
5. Verificar integridade do sistema.

---

## Solução 

### Reparação do Boot

Acessar:

`Solução de Problemas → Opções Avançadas →  Prompt de Comando`

Executar:

```cmd
bootrec /fixmbr
bootrec /fixboot
bootrec /rebuildbcd
```

---

### Correção de arquivos do sistema

```cmd
sfc /scannow

DISM /Online /Cleanup-Image /ResporeHealth
```

---

### Outras ações 

- Remover atualização recente pelo WinRE
- Iniciar em modo de Segurança para validar drivers 
- Verificar intregridade do disco

---

## Ferramentas utilizadas 

- 
windows Recovery Environment (WinRE)
Prompt de Comando
Modo de Segurança
Visualizador de Eventos

---

## Comandos

```cmd
bootrec /fixbr
bootrec /fixboot
bootrec /rebuildbcd
chkds c: /f /r
sfc /scannow 
DISM /Oline /Cleanup-Image /RestoreHealth
```

---

## Validação

- Windowa inicia normalmente até a tela de login
- Computador permanece ligado durante múltiplos ciclos de teste
- Usuário consegue acessar o ambiente normalmente
- Não existem novos erros críticos registrados

---

## Referências 

- `problemas-inicializção.md`
- `recuperacao-sistem.md`