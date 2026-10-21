# Carteira Verde

Site de finanças pessoais para acompanhar seus investimentos de forma simples, com fundo branco e detalhes em verde e prata.

**Acesse:** https://lucas-3010.github.io/Carteira-Verde/

## O que o site faz

- **Quanto sua carteira vale:** mostra o valor atual, o total investido, o lucro ou prejuízo e a rentabilidade.
- **Composição da carteira:** mostra um gráfico com a porcentagem de cada tipo de investimento (ações, FIIs, renda fixa, Tesouro, exterior e cripto).
- **Investimentos por banco:** você informa em qual banco ou corretora está cada investimento. O site mostra um gráfico geral com quanto você tem em cada banco e um gráfico para cada banco. Um seletor deixa você ver só os investimentos de um banco.
- **Ações em alta e notícias:** são seções com dados de exemplo, prontas para receber uma fonte real.
- **Meus investimentos:** é onde você adiciona, edita e remove seus investimentos. O autocompletar sugere códigos e nomes de cerca de 120 ativos. Ao escolher um, o código, o nome e o tipo são preenchidos de uma vez.
- **Renda fixa:** para CDB, LCI, LCA, Tesouro Direto e outros títulos, você informa o indexador (% do CDI, IPCA +, Selic + ou prefixado), a taxa, a data de aplicação e o vencimento. O site projeta o valor bruto e o líquido no vencimento, com o imposto da tabela regressiva. Também mostra o próximo vencimento e quanto vence em cada ano. As premissas de CDI, Selic e IPCA podem ser editadas.
- **Meu perfil:** guarda nome, CPF, celular, e-mail, data de nascimento, endereço (com busca pelo CEP no ViaCEP), profissão, renda e perfil de investidor. O site valida o CPF, o celular, o e-mail e o CEP.
- **Simulador:** calcula juros compostos com valor inicial, aporte mensal, prazo e taxa. Você pode escolher o tipo de rendimento (taxa fixa, % do CDI, IPCA + ou Selic +) e descontar o imposto de renda. Tem atalhos com taxas de referência, como poupança, CDB, LCI/LCA e Tesouro IPCA+, e um gráfico que mostra a evolução ano a ano.

## Privacidade

Não há login nem servidor. Os investimentos e os dados do perfil ficam salvos somente no navegador de quem usa (localStorage) e não são enviados para nenhum lugar. A única consulta externa é o CEP, enviado ao [ViaCEP](https://viacep.com.br) para preencher o endereço. Em computador compartilhado, use "Apagar meus dados" na aba Meu perfil.

## Como rodar localmente

Abra o `index.html` no navegador. Não é preciso instalar nada.

## Onde mexer

Todo o código está no `index.html`, dividido em seções comentadas no script:

| Seção | O que tem |
|---|---|
| 1. Configuração e dados de exemplo | tipos e cores, bancos, lista de ativos (`ATIVOS`), premissas de CDI/Selic/IPCA, indexadores, padrões de renda fixa, listas do perfil |
| 2. Armazenamento | salvar e carregar do navegador |
| 3. Formatação e cálculos | moeda, porcentagens, resumo e juros compostos |
| 4. Telas / 4b. Autocompletar | desenho de cada parte da tela e a caixa de sugestões |
| 5. Fonte de dados de mercado | `fonteDeDados`: troque os exemplos por uma API real, como a [brapi.dev](https://brapi.dev) |
| 6. Eventos / 6b. Meu perfil | cliques, formulário, abas, máscaras e validação de CPF/celular/e-mail/CEP |
| 7. Inicialização | o que roda ao abrir o site |

As cores ficam nos tokens `:root` no começo do CSS.

> Simulações não incluem impostos e taxas. Rentabilidade passada não garante rentabilidade futura.
