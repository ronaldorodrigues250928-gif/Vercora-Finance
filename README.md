# Vercora Finance — App local

Aplicação web em React + Vite + Tailwind CSS, com o fluxo completo da
plataforma: institucional, simulador de nicho, cadastro/contratação da
empresa, painel do lojista e checkout do cliente final.

## Como rodar

Pré-requisito: Node.js 18 ou superior instalado.

```bash
npm install
npm run dev
```

O terminal vai mostrar o endereço local, algo como:

```
Local:   http://localhost:5173/
```

Abra esse endereço no navegador. O app abre automaticamente ao rodar `npm run dev`.

## Build de produção

```bash
npm run build
npm run preview
```

## Estrutura

```
src/
  App.jsx                     -> navegação entre as visões
  components/
    Header.jsx                -> menu superior
    Home.jsx                  -> institucional + simulador de nicho
    RoiCalculator.jsx         -> calculadora de retorno
    CompanyRegistration.jsx   -> cadastro da empresa e contratação (8 etapas)
    Dashboard.jsx             -> painel do lojista + terminal de emissão
    Checkout.jsx              -> tela do cliente final
    Field.jsx, Wordmark.jsx   -> componentes de apoio
  data/niches.js               -> nichos atendidos (mock)
  utils/masks.js                -> máscaras de CNPJ, CPF, CEP e telefone
```

## Sobre o cadastro de empresa

A etapa "Contratar Vercora" busca automaticamente dados públicos de CNPJ
(via BrasilAPI) e de endereço (via ViaCEP) para agilizar o preenchimento —
isso exige conexão com a internet ao rodar localmente. Se a busca falhar,
o formulário permanece editável manualmente.

Os uploads de documentos e a assinatura eletrônica são apenas a interface:
não há backend conectado. Para integrar de verdade, é preciso plugar uma
API própria (ex. Node/Express) para persistir os dados e os arquivos.
