# WebReport — chave de controle

Este repositório guarda só o arquivo **controle.json**, assinado pela WebTechs. Os servidores do WebReport leem este
arquivo a cada 15 minutos para saber o nível do sistema:

| Nível | O que acontece |
|---|---|
| `normal` | Tudo funciona. |
| `aviso` | Faixa com a mensagem em todas as telas. |
| `somente-leitura` | Ninguém grava (só o dono do sistema). |
| `bloqueio` | Página de bloqueio para todos e rotinas automáticas paradas. |

**Para mudar:** aba **Actions** › **Mudar o nivel do WebReport** › **Run workflow**, escolha o nível e a mensagem.
Leva até 15 minutos para os servidores verem.

O arquivo é assinado com uma chave que fica só nos *Secrets* deste repositório; qualquer alteração manual no
`controle.json` invalida a assinatura e é ignorada pelos servidores. Se um servidor ficar 7 dias sem conseguir ler
um arquivo válido, ele se bloqueia sozinho.
