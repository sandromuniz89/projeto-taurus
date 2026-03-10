<div align="center">

# ⚡ Projeto Taurus
### Sistema de Gestão Completo com Integração a Painel de Servidor

[![Firebase](https://img.shields.io/badge/banco-Firebase%20Firestore-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Functions](https://img.shields.io/badge/backend-Firebase%20Functions-FF6F00?style=flat-square&logo=firebase)](https://firebase.google.com/docs/functions)
[![PWA](https://img.shields.io/badge/PWA-instalável-5A0FC8?style=flat-square&logo=pwa)](#)
[![License](https://img.shields.io/badge/licença-MIT-22c55e?style=flat-square)](LICENSE)

**Dashboard de gestão profissional com integração em tempo real a painel de servidor externo — controle total de clientes, financeiro, relatórios e automação de operações, tudo em uma única interface.**

</div>

---

## ✨ Visão Geral

O **Projeto Taurus** nasceu da necessidade de centralizar em um único painel todas as operações de um negócio baseado em assinaturas e serviços — eliminando o uso de múltiplas ferramentas, planilhas e acessos manuais.

A solução integra um dashboard de gestão moderno diretamente ao painel do servidor de serviços, permitindo que todas as operações — desde o cadastro de um novo cliente até a renovação de um plano — sejam realizadas com um único clique, de forma automatizada e sem a necessidade de acessar sistemas externos.

---

## 🚀 Funcionalidades

### 📊 Dashboard
- Visão geral em tempo real: total de clientes, ativos, expirados, receita e lucro
- Alerta automático de clientes com vencimento no dia
- Receita esperada para os próximos 30 dias
- Gráfico de lucro mensal dos últimos 6 meses
- Gráfico de distribuição por tipo de plano
- Lista de vencimentos próximos e expirados com busca integrada
- Renovação direta pelo dashboard com um clique

### 👥 Clientes
- Cadastro completo com nome, telefone, e-mail, plano, acessos e vencimento
- Filtros por status: Todos, Ativos, Expirados, Mensais, Trimestrais, Vencendo em 7 dias
- Busca inteligente por nome, telefone ou **data de vencimento** — aceita `05/04/2026` ou `04/2026`
- Paginação com opções de **10, 50 ou 100** registros por página
- Vinculação do cliente ao painel de servidor diretamente pelo modal de detalhes
- Suporte a clientes cadastrados antes da integração via botão **🔗 Vincular Painel**
- Cadastro de clientes já existentes no servidor sem gastar créditos (**Cadastro Existente**)

### 🔄 Renovação Integrada
- **Modal de confirmação** antes de renovar — exibe o tipo de plano (Mensal/Trimestral) para validação antes de executar
- Correção automática do tipo de plano no Firebase ao confirmar a renovação
- Cálculo automático de créditos, valor e lucro antes de confirmar
- Data de vencimento calculada a partir do vencimento atual — não de hoje
- Atualização simultânea no Firebase e no painel do servidor
- Suporte a clientes com campo `painel_username` (legado) e `painelUsername` (novo)

### 📡 Testes / Trials
- Criação de acesso de teste diretamente pelo dashboard
- **Busca em tempo real** por usuário ou telefone — ideal para localizar testes antigos entre dezenas de registros
- Listagem de testes com status, senha, plano, conexões e expiração
- Botão de copiar as informações formatadas para envio direto via WhatsApp
- Ativação do teste como cliente com seleção de plano, acessos e conteúdo adulto
- Salvamento automático no Firebase para controle persistente

### 💰 Relatórios Financeiros
- **Receita do Mês** — total e quantidade de clientes no mês atual
- **Taxa de Retenção** — percentual de clientes do mês anterior que renovaram
- **Clientes em Risco** — expirados há mais de 7 dias
- **Margem de Lucro** — percentual sobre o histórico geral
- **Novos vs Ativados** — cadastros novos versus ativações via teste no mês
- Lucro separado por tipo de plano (Mensal e Trimestral)
- Comparativo mensal dos últimos 6 meses com receita e clientes

### ⚙️ Configurações
- Tema claro e escuro
- Botão de privacidade para ocultar valores financeiros na tela
- Credenciais de acesso com troca de usuário e senha

---

## 🔗 Integração com Painel de Servidor

O Projeto Taurus se conecta via **Firebase Functions** (backend seguro em nuvem) ao painel de servidor externo, executando as seguintes operações de forma automatizada:

| Operação | Descrição |
|----------|-----------|
| Criar cliente | Cadastro automático no servidor ao registrar novo cliente |
| Renovar plano | Renovação no servidor sincronizada com o dashboard — Mensal (30d) ou Trimestral (90d) |
| Criar teste | Geração de acesso de teste diretamente pelo painel |
| Bloquear / Desbloquear | Suspensão e reativação de acesso pelo modal do cliente |
| Excluir cliente | Remoção sincronizada no servidor e no Firebase |
| Exibir créditos | Saldo de créditos atualizado em tempo real no header |

> Todas as operações são realizadas através de um proxy seguro no backend — nenhuma credencial do servidor é exposta no frontend.

---

## 🏗️ Arquitetura

```
Projeto Taurus/
├── index.html              # Interface principal
├── css/
│   └── style.css           # Estilos, temas e responsividade
├── js/
│   ├── firebase.js         # Conexão e operações com Firestore
│   ├── auth.js             # Autenticação de acesso
│   ├── dashboard.js        # Lógica do dashboard e relatórios
│   ├── clientes.js         # Gestão de clientes, renovação e relatórios
│   ├── testes.js           # Gestão de testes/trials com busca
│   ├── painel.js           # Integração com painel de servidor
│   ├── config.js           # Configurações e personalização
│   └── utils.js            # Funções utilitárias
└── functions/
    └── index.js            # Firebase Functions — proxy seguro para o servidor
```

---

## 🧰 Tecnologias Utilizadas

| Tecnologia | Finalidade |
|------------|------------|
| HTML5 / CSS3 / JavaScript | Frontend puro, sem frameworks |
| Firebase Firestore | Banco de dados em nuvem com sincronização em tempo real |
| Firebase Functions | Backend seguro para integração com servidor externo |
| PWA | Instalação como app no celular sem loja de aplicativos |
| CSS Grid e Flexbox | Layout totalmente responsivo |
| Google Fonts | Tipografia profissional |

---

## 🤝 Suporte

Desenvolvido por **Sandro Muniz**

[![WhatsApp](https://img.shields.io/badge/Suporte%20via%20WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/5521980415517?text=Olá%20Sandro!%20Tenho%20interesse%20no%20Projeto%20Taurus.)

---

<div align="center">
  <sub>Feito com ❤️ por <strong>Sandro Muniz</strong></sub>
</div>
