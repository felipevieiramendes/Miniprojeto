Sistema Solar Interativo

Integrantes: 
-Felipe Vieira Mendes
-Lucas Paraíso Benning de Oliveira
-Caio Cordeiro Simões de Oliveira

Tecnologias Utilizadas
Linguagem: JavaScript 

Renderização: Canvas API (2D Context)

Matemática: Trigonometria (Math.atan2, sin, cos) e Álgebra Linear (Matrizes de Transformação).

Conceitos de Transformações Aplicados
O projeto foi construído respeitando os seguintes requisitos técnicos:

1. Composição e Hierarquia
O sistema utiliza uma estrutura de "árvore" para as transformações, onde o estado da matriz é preservado e restaurado via save() e restore():

Nível 1 (Raiz): O Sol define a origem central.

Nível 2 (Filhos): Mercúrio, Terra, Marte e Saturno herdam a translação do centro e aplicam sua própria rotação (órbita).

Nível 3 (Netos): A Lua (Terra) e as luas Fobos e Deimos (Marte) herdam a posição de seus respectivos planetas, demonstrando o empilhamento de matrizes.

2. Transformações Fundamentais
Translação: Utilizada para posicionar os astros em suas respectivas órbitas e mover a nave.

Rotação: Aplicada para as órbitas planetárias e para orientar a nave na direção do movimento.

Escala (Scale): * Uniforme: Utilizada no "pulso" do Sol e no tamanho da nave.

Não-Uniforme: Aplicada em Saturno para achatar um círculo e criar a elipse dos anéis (scale(1, 0.4)).

Reflexão (Espelhamento): Implementada na nave através de escala negativa (scale(1, -1)) ao pressionar a tecla Shift.

Cisalhamento (Shear): Aplicado no cometa através de ctx.transform(1, 0, -0.5, 1, 0, 0), distorcendo a geometria para simular rastro de velocidade.

3. Dinâmica e Interatividade
Ponto Fixo: A rotação interna da Terra (continentes) ocorre em torno de seu próprio eixo local.

Trigonometria Dinâmica: A nave utiliza a função Math.atan2(dy, dx) para calcular o ângulo de rotação em tempo real baseada no vetor de movimento das setas do teclado.

Controles
Setas (↑ ↓ ← →): Movimentam a nave. A nave rotaciona automaticamente para a direção do deslocamento.

Espaço: Ativa o Turbo. Aumenta a velocidade de translação e a escala da nave, ativando o efeito visual de propulsão.

Shift: Aplica reflexão (espelhamento) no eixo vertical da nave.

Como Executar:
Copie o código do arquivo index.html.

Abra em qualquer navegador moderno.

Certifique-se de que o foco da janela esteja no navegador para capturar os eventos de teclado.
