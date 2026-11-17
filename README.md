# Rotina Bebê & Mãe

App web (um único `index.html`) com a rotina diária do bebê (1a4m) e da mãe em home office.

- Destaca o bloco do horário atual e mostra o próximo
- Checklist diário do bebê e da mãe, salvo no aparelho e zerado a cada dia
- Filtro Bebê / Mãe, tema claro/escuro e versão para imprimir (A4 paisagem)
- Lembretes: dia de cozinha em lote (dom/qua) e rodízio de brinquedos (a cada 3 dias)

Site: https://franppires.github.io/routine/

## Login e família (Firebase)

Sem configuração, o app funciona só no aparelho (dados no `localStorage`).
Com o Firebase configurado, ele pede login (Google ou e-mail e senha) e salva a rotina
e o diário na nuvem, compartilhados apenas entre os membros da mesma família.

1. Crie um projeto em https://console.firebase.google.com (Analytics pode ficar desativado).
2. **Authentication → Sign-in method**: ative **Google** e **E-mail/senha**.
3. **Authentication → Settings → Domínios autorizados**: adicione `franppires.github.io`.
4. **Firestore Database → Criar banco** (modo produção, região `southamerica-east1`).
5. **Firestore → Regras**: cole o conteúdo de [`firestore.rules`](firestore.rules) e publique.
6. **Configurações do projeto → Seus apps → Web**: registre o app e copie o `firebaseConfig`
   para a constante `FIREBASE_CONFIG` no `index.html`.

O `firebaseConfig` não é segredo: quem protege os dados são as regras do Firestore.

## Créditos

Ilustrações: [Fluent Emoji](https://github.com/microsoft/fluentui-emoji) (Microsoft, licença MIT), na pasta `img/`.
