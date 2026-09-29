# Politica de privacidade — Nexify Bloqueador

**Aplicativo:** Nexify Bloqueador
**Pacote:** `ink.nexify.callblocker`
**Versao desta politica:** 1.1 (29 de setembro de 2026)
**Contato:** suporte@nexify.ink

---

## TL;DR (em portugues claro)

- O app **bloqueia ligacoes indesejadas no seu celular**. Nada mais.
- **Nao tem propaganda. Nao tem rastreamento.** Nenhum SDK de analise de
  comportamento (Mixpanel, Firebase Analytics, Amplitude etc.). Nenhum
  pixel de marketing.
- **Seus dados ficam no seu celular.** Sua lista de bloqueados, seus contatos,
  suas tags e o historico de ligacoes bloqueadas nao saem do aparelho.
- O app nao precisa de internet para funcionar. **Voce pode ficar com o
  Wi-Fi e os dados moveis desligados** que o bloqueio continua trabalhando.
- Sem login, sem conta, sem cadastro.

---

## 1. Quem somos

O Nexify Bloqueador e um aplicativo Android nativo, gratuito, distribuido
pela Nexify, atraves da Google Play
Store. Nao ha versao web nem servidor de aplicacao proprio: todo o
processamento acontece dentro do seu aparelho.

## 2. O que o app faz

Quando alguem te liga, o sistema operacional Android entrega a chamada para
o app **antes do telefone tocar**. O app verifica em sequencia:

1. Se o numero esta na sua **lista de bloqueio** (que voce mesmo cria);
2. Se o numero parece **telemarketing automatico** (prefixos brasileiros como
   0800, 0300, 0303, 4003, 4004, 3003, 3004) — toggle opcional em "Ajustes";
3. Se o numero **nao esta na sua agenda** e voce ligou o modo "so contatos"
   — toggle opcional em "Ajustes";
4. Se nada acima se aplicar, a ligacao toca normalmente.

Em chamadas bloqueadas, o app posta uma notificacao silenciosa pra voce
saber quem tentou ligar (so se voce liberar a permissao de notificacoes).

Para chamadas que vem pelo **WhatsApp/WhatsApp Business**, o app aplica as
mesmas regras usando o acesso a notificacoes, quando ativado pelo usuario.

## 3. O que voce nos da (permissoes do app)

| Permissao | O que o app faz com isso | Sai do aparelho? |
|---|---|---|
| Atender chamadas (`ROLE_CALL_SCREENING`) | Decidir, antes de tocar, se uma ligacao deve ser bloqueada. | Nao |
| Contatos (`READ_CONTACTS`) | Saber se quem esta ligando esta na sua agenda (modo "so contatos"). Usado **localmente**: o app **nao envia sua agenda pra lugar nenhum**. | Nao |
| Notificacoes (`POST_NOTIFICATIONS`) | Avisar voce em silencio quando uma chamada for bloqueada. | Nao |
| Internet (`INTERNET`, `ACCESS_NETWORK_STATE`) | Declarada para futuras funcionalidades opcionais (identificacao colaborativa de chamadas). **Nao e usada na versao atual** — o app nao se conecta a servidores nossos. | Nao |
| Acesso a notificacoes (`BIND_NOTIFICATION_LISTENER_SERVICE`) | Necessario para identificar uma chamada de WhatsApp e recusa-la conforme suas regras. So vale para `com.whatsapp` e `com.whatsapp.w4b`. | Nao |

Voce libera cada permissao manualmente no fluxo de configuracao da tela
**Inicio**. Pode revogar a qualquer momento em **Configuracoes do Android
> Apps > Nexify Bloqueador > Permissoes**.

## 4. O que NAO fazemos

Compromissos formais — escritos antes de qualquer feature pra que o produto
nao se desvie:

1. **Nao usamos propaganda**, banner, patrocinio, paywall, "premium" nem
   compra dentro do app. O app e gratuito e seguira gratuito.
2. **Nao usamos analytics de comportamento**: nada de saber que voce abriu
   o app, em qual tela ficou mais tempo, qual botao apertou. Nao temos
   Firebase Analytics, Mixpanel, Amplitude, Adjust, AppsFlyer, GA4, etc.
3. **Nao temos rastreador de identidade**: nao geramos identificador unico
   de instalacao para correlacionar voce em outros apps. Nao usamos GAID
   (Google Advertising ID).
4. **Nao enviamos sua lista de bloqueio, sua agenda nem seu historico de
   chamadas pra fora do aparelho.** Sequer existe servidor pra onde
   enviarmos hoje.
5. **Nao gravamos suas chamadas.**
6. **Nao usamos servico de acessibilidade** e nao capturamos teclas ou telas.

## 5. O que fica armazenado no seu celular

Tudo que o app guarda fica em armazenamento privado do app (acessivel apenas
ao app), no proprio aparelho:

- **Lista de bloqueio:** os numeros que voce cadastrou manualmente, na
  ordem que cadastrou. Banco de dados local (SQLite/Room).
- **Configuracoes:** os switches que voce liga/desliga ("Bloquear quem nao
  esta na agenda", "Bloquear telemarketing automaticamente", "Bloquear
  chamadas de WhatsApp"). Arquivo de preferencias local (DataStore).
- **Cache da agenda:** copia local dos contatos lidos do sistema para
  agilizar a tela "Meus contatos". So `lookup_key`, nome de exibicao,
  numero principal, data em que o app viu o contato pela primeira vez,
  tags que voce criou e (opcional) genero que voce informou. **Nao guardamos
  fotos, emails ou enderecos da agenda.**
- **Historico local de bloqueios:** ate as ultimas centenas de chamadas que
  o app bloqueou, com data/hora, numero (quando exibido pela operadora),
  razao do bloqueio. Voce pode limpar a qualquer momento na aba
  **Bloqueados > Historico**.

Tudo isso e apagado quando voce desinstala o app. Nada e exportado
automaticamente.

## 6. Compartilhamento com terceiros

**Nenhum.** O app nao compartilha dados com terceiros porque nao coleta
dados em servidores nossos.

A unica empresa que pode receber metadados sobre voce em relacao ao app e a
Google, atraves da Google Play Store, quando voce instala/atualiza/desinstala
o app. Isso e governado pela politica de privacidade da Google e foge do
nosso controle.

## 7. Crashes

A Play Store pode coletar relatorios anonimos de travamento do app
(stacktrace + modelo do aparelho + versao do Android). Esses dados ficam
com o Google, **nao temos servidor proprio que receba isso**. Voce pode
desligar o envio nas Configuracoes do Android > Google > Diagnosticos.

## 8. Criancas

O app nao e direcionado a menores de 13 anos. Nao coletamos dados de
ninguem (incluindo criancas) deliberadamente.

## 9. Mudancas nesta politica

Quando esta politica mudar:

- Subimos uma versao nova com data e numero ("Versao desta politica");
- O changelog do que mudou fica em [`docs/CHANGELOG.md`](CHANGELOG.md);
- Mudancas materiais (que afetem o que voce libera ou como tratamos seus
  dados) viram um aviso visivel dentro do app na proxima vez que voce
  abrir.

## 10. Direitos do titular (LGPD)

Como nao coletamos dados em servidor nosso, na pratica:

- **Acesso** aos seus dados: tudo esta no seu proprio aparelho. Abra o app
  e veja.
- **Correcao**: editar/remover diretamente no app.
- **Exclusao**: remover individual no app, ou desinstalar — o sistema
  Android limpa todo o storage privado do app.
- **Portabilidade**: por enquanto nao ha exportar/importar JSON; esta na
  lista para uma versao futura.
- **Reclamacao a ANPD**: voce sempre pode procurar a Autoridade Nacional
  de Protecao de Dados em [https://www.gov.br/anpd/](https://www.gov.br/anpd/).

## 11. Contato

Duvidas, sugestoes, reportar problemas:

- Email: suporte@nexify.ink

---

> Versoes futuras (caso o app evolua):
>
> - **Identificacao colaborativa de chamadas (Caller ID):** se algum dia
>   um toggle "Contribuir com a base comum de identificacao" for ativado por
>   voce, o app passara a enviar pares (numero em formato internacional E.164,
>   nome) anonimizados a uma base coletiva. Estamos preparando essa feature
>   como **opt-in explicito**, com aviso na hora de ligar e a possibilidade
>   de remover sua contribuicao a qualquer momento. Nada sera ligado por
>   default.
> - **Login com Google + telefones vinculados:** nao esta presente na
>   versao atual da loja. Se entrar, esta politica sera atualizada antes
>   da feature ir ao ar.
