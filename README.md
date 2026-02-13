# Animação mensagem / notificação

Este projeto apresenta um envelope animado que, ao ser clicado, abre e revela uma mensagem em tela cheia. É uma solução elegante para convites digitais, mensagens de agradecimento ou "surpresas" em sites.

---

## Funcionalidades

* **Animação de Envelope:** O envelope possui dobras (superior, lateral e fundo) que simulam um objeto real em 3D.
* **Transições Suaves:** Uso de `transition` e `rotateX` para abrir a aba do envelope de forma realista.
* **Efeito de Revelação:** Após a animação de abertura, uma janela modal (carta aberta) surge com a mensagem principal.
* **Interatividade Bidirecional:** O usuário pode abrir o envelope clicando nele e fechá-lo clicando no "X", o que reseta a animação.

---

## Detalhes Técnicos

### Estrutura Visual (CSS)
O envelope é construído inteiramente com CSS através de manipulação de bordas e camadas (`z-index`):
* **Top Fold (Aba):** Utiliza `transform-origin` no topo para girar 180 graus para cima.
* **Letter (Papel):** Fica escondido entre as dobras e desliza para cima alterando sua altura (`height`).
* **Shadow (Sombra):** Uma sombra radial que diminui de tamanho quando o envelope "abre", simulando profundidade.

### Lógica de Controle (JavaScript)
O script gerencia a sequência de eventos:
1.  **Abertura:** Quando o `envelope` é clicado, as propriedades de CSS do papel e da aba são alteradas. Um `setTimeout` de 500ms é usado para mostrar a mensagem apenas após a animação terminar.
2.  **Fechamento:** A função `fecharCarta()` limpa a tela e reverte todas as propriedades do envelope ao estado original.

---

## Como Personalizar a Mensagem

Para alterar o texto que aparece quando a carta é aberta, localize a `div` com a classe `open-letter` no HTML:

```html
<div class="open-letter" id="openLetter">
    <div class="close-x" onclick="fecharCarta()">×</div>
    <h1>Seu Título Aqui</h1>
    <p>Sua mensagem personalizada aqui!</p>
</div>

<img width="712" height="421" alt="Image" src="https://github.com/user-attachments/assets/85530a20-37fb-4e9c-8e22-583ed729b627" />

