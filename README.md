# Página de vendas do Umbra Voice Lab

Site estático, sem build: `index.html` e a pasta `assets/`. Fica separado do código do app.

## Antes de publicar

Abra `index.html`, procure o bloco `const SALE` no final do arquivo e preencha:

```js
const SALE = {
  price: 'R$ 197',                  // preço exibido
  priceLabel: 'Pagamento único',    // ou 'Assinatura anual', etc.
  priceNote: 'À vista ou em até 12x.',
  checkoutUrl: 'https://...',       // link do checkout (Hotmart, Kiwify, Stripe...)
};
```

Hoje a seção de preço mostra "Sob consulta", com um botão para o WhatsApp (https://wa.me/message/EF4DJTI6JTOTH1). A pergunta "Quanto custa?" nas perguntas frequentes leva ao mesmo link. Os botões "Quero o Umbra" do topo levam até a seção de preço.

Quando você preencher `price`, o valor aparece no lugar de "Sob consulta". Quando preencher `checkoutUrl`, todos os botões de compra passam a abrir o checkout em vez do WhatsApp.

## Publicar na Vercel

Pelo terminal, dentro desta pasta:

```powershell
npx vercel          # primeira vez: faz login e cria o projeto (gera uma prévia)
npx vercel --prod   # publica em produção
```

Na primeira vez, aceite as opções padrão. É um site estático, não precisa de comando de build nem de pasta de saída. Depois, ligue o seu domínio em **Project → Settings → Domains** no painel da Vercel.

## Conteúdo

- **Imagens:** as capturas em `assets/tela-*.jpg` são do app real, feitas com dados de exemplo (o roteiro sobre a história do café).
- **Ícone e favicon:** `assets/icone.svg`, `assets/icone-256.png` e `assets/favicon-32.png` vêm de `build/icon.svg` do app.
- **Números da página:** vêm de medições reais (Piper: 59,8 min de áudio em ~9 min; voz clonada: ~5 a 6 h por hora de áudio num Xeon E5-2650 v4 com 16 GB). Se mudar o hardware de referência, atualize a seção "Desempenho real".
- **Uso comercial das vozes:** o texto segue as licenças registradas no app. Revise se o catálogo de vozes mudar.
