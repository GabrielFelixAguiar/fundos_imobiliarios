# Provento — Fundos Imobiliários mais rentáveis

Mini página de conversão sobre Fundos de Investimento Imobiliário (FIIs), com ranking de fundos, calculadora de retorno e simulador de longo prazo. Feita em HTML, CSS e JavaScript puros, em um único arquivo.

## Funcionalidades

- **Ranking de fundos**: lista os FIIs do mercado, ordenável por DY (dividend yield), cotação ou nome, com filtro por segmento (tijolo / papel).
- **Dados ao vivo (opcional)**: busca cotações e histórico de dividendos direto na API da [brapi.dev](https://brapi.dev), calculando o DY dos últimos 12 meses a partir dos proventos pagos.
- **Modo demonstração**: sem token de API configurado, o site funciona com dados ilustrativos, claramente sinalizados na interface.
- **Calculadora de retorno**: simula renda mensal, total em proventos e patrimônio final para um valor investido e prazo em meses, com opção de reinvestir os proventos.
- **Simulador de longo prazo**: projeta aportes mensais recorrentes com juros compostos sobre o DY esperado, com gráfico (Chart.js) de patrimônio acumulado x total aportado.
- **Passo a passo de uso**: seção final explicando como usar a página, do ranking até a projeção de longo prazo.

## Como rodar

Não há build nem dependências para instalar. Basta abrir o arquivo `provento-fii.html` direto no navegador, ou servir a pasta com qualquer servidor estático:

```bash
npx serve .
# ou
python3 -m http.server 8000
```

## Configurando dados ao vivo

1. Crie uma conta gratuita em [brapi.dev/dashboard](https://brapi.dev/dashboard) e gere um token.
2. Na página, cole o token no campo acima da tabela de fundos e clique em **Conectar**.
3. O token fica apenas na memória do navegador (variável JS) — não é salvo em disco nem enviado a nenhum servidor além da própria brapi.dev.

Sem token válido ou em caso de falha na API, o site cai automaticamente para os dados de demonstração.

## Estrutura do projeto

```
.
├── provento-fii.html   # site completo (HTML + CSS + JS em um único arquivo)
└── README.md
```

## Tecnologias

- HTML5 + CSS3 (sem framework)
- JavaScript vanilla (fetch API)
- [Chart.js](https://www.chartjs.org/) via CDN, para o gráfico do simulador de longo prazo
- [brapi.dev](https://brapi.dev) como fonte de dados de mercado (ações, FIIs e dividendos da B3)

