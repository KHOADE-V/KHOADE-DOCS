# Segurança de contas

Poucas medidas bloqueiam a grande maioria dos ataques a contas pessoais. Faça nesta ordem.

## 1. Use um gerenciador de senhas

Uma senha **única** para cada site. Quando um site vaza, só aquela conta é afetada. Um gerenciador (Bitwarden, 1Password, KeePassXC, o do seu navegador ou sistema) cria e lembra tudo por você. Memorize apenas a senha-mestra.

Senha-mestra boa: uma frase longa de 4 a 6 palavras sem relação entre si, por exemplo `cadeira-nuvem-tigela-onze`.

## 2. Ative a verificação em duas etapas (2FA)

Ordem do mais forte para o mais fraco:

1. **Chave de segurança física** (FIDO2/WebAuthn) ou **passkey**
2. **App autenticador** (Aegis, Google Authenticator, Authy etc.)
3. **SMS**: melhor que nada, mas vulnerável a troca de chip

Comece pelas contas mais importantes: **e-mail**, banco, GitHub e redes sociais. Quem controla o seu e-mail consegue redefinir as outras senhas.

Guarde os **códigos de recuperação** em lugar seguro (no gerenciador de senhas, por exemplo).

## 3. Desconfie de mensagens que criam urgência

Phishing tenta fazer você agir sem pensar: "sua conta será bloqueada", "pagamento recusado", "você ganhou".

- Não clique em links da mensagem. Abra o site digitando o endereço ou pelo app oficial.
- Confira o endereço de verdade do remetente e do link.
- Nenhuma empresa séria pede sua senha ou código de 2FA por mensagem ou telefone.

## 4. Mantenha tudo atualizado

Sistema, navegador e aplicativos. Atualizações corrigem falhas que atacantes realmente exploram. Ative as atualizações automáticas.

## 5. Revise de tempos em tempos

- Veja os dispositivos e sessões conectados e encerre os que você não reconhece.
- Revise os aplicativos com acesso à sua conta e remova os que não usa.
- Consulte [haveibeenpwned.com](https://haveibeenpwned.com) para saber se seu e-mail apareceu em vazamentos.

## Em desenvolvimento de software

- Nunca commite tokens, chaves de API ou arquivos `.env`. Use variáveis de ambiente e `.gitignore`.
- Se um segredo vazou: **revogue e gere outro imediatamente**. Apagar o commit não resolve.
- Dê a cada token só as permissões de que ele precisa e uma data de expiração.

## Se você acha que foi invadido

1. Troque a senha da conta (e de qualquer outra que repetia a mesma senha), a partir de um dispositivo confiável.
2. Encerre todas as sessões ativas.
3. Ative ou revise o 2FA.
4. Confira o e-mail de recuperação e o telefone cadastrados.
5. Avise o suporte do serviço e, se envolver dinheiro, o seu banco.
