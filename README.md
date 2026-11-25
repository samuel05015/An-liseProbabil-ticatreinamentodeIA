# EntreAtos

Protótipo da AV3 de Inteligência Artificial e Aprendizagem de Máquina. Após um ensaio de teatro escolar, a equipe pode descrever o que aconteceu com um figurino. O EntreAtos sugere encaminhar a peça para **conserto**, **limpeza** ou **conferência do acervo**. Quando a descrição oferece pouca evidência, o protótipo indica **revisão humana**.

## Como executar

1. Baixe e extraia os arquivos do repositório.
2. Abra `prototipo.html` no navegador. O protótipo funciona offline, sem instalação.
3. Clique em **Zíper travado** para ver um encaminhamento para conserto.
4. Digite *“O zíper travou e a manga está com mancha de café”* e clique em **Classificar relato** para ver um caso encaminhado para revisão humana.

## Como funciona

O navegador treina um classificador **Naive Bayes multinomial** com 60 relatos simulados, 20 por categoria. O modelo usa a frequência das palavras no treino para pontuar as classes. Quando reconhece menos de duas palavras distintas ou a maior pontuação fica abaixo de 68%, a regra de triagem indica revisão humana.

O código está comentado em português. Procure por `function avaliar` para ver como a decisão final (`destino`) é comparada com o gabarito (`esperado`).

## Resultados do teste

Use **Avaliação com relatos simulados → Rodar avaliação → Ver previsões por relato** para conferir os 32 casos usados no teste. Esses relatos ficaram fora do treinamento.

| Métrica | Resultado |
| --- | ---: |
| Decisões finais iguais ao gabarito | 28 de 32 (87,5%) |
| Encaminhamentos automáticos corretos | 21 de 23 (91,3%) |
| Casos previstos para revisão que foram sinalizados | 7 de 8 (87,5%) |

O modelo encaminhou para conserto um relato de costura aberta, zíper travado e mancha que o gabarito marcava para revisão. Os resultados se referem à amostra simulada. O comportamento com relatos reais ainda precisa ser avaliado.

## Arquivos

- [Protótipo e código comentado](./prototipo.html)
- [Relatório técnico da AV3](./relatorioTecnicoAV3-EntreAtos.html)
- [Apresentação em PowerPoint com notas de fala](./Apresentacao-EntreAtos-AV3.pptx)
