# 🌟 StarRoutine Evelle - Painel de Rotina Gamificado

**Versão:** 1.0  
**Status:** 🟢 Concluído

## 📖 Visão Geral

O **StarRoutine Evelle** é uma aplicação web interativa (Single Page Application) desenvolvida para auxiliar na organização diária, construção de hábitos e disciplina positiva para uma criança de 5 anos. O sistema substitui os quadros de rotina tradicionais de papel por uma interface digital responsiva, gamificada e persistente, focada na autonomia da criança.

## 🚀 Objetivos do Projeto

* **Autonomia:** Permitir que a criança visualize e interaja com suas próprias tarefas de forma lúdica.
* **Reforço Positivo:** Utilizar um sistema de recompensas visuais (estrelas e troféus) para incentivar o cumprimento de deveres.
* **Monitoramento:** Permitir aos pais acompanhar a consistência da rotina através de métricas automáticas (diárias, semanais e mensais).

---

## 🛠️ Funcionalidades Principais

### 1. Checklist Diário Interativo
* Listagem cronológica de atividades divididas por períodos (Manhã, Tarde, Noite).
* **Interface Visual:** Uso de emojis grandes para fácil identificação de tarefas por crianças não alfabetizadas (ex: 🚿, 🥣, 🎒).
* **Validação Binária:** Sistema simples de "Conquista" onde a tarefa pode receber uma **Estrela (⭐)** ou um **X (❌)**.

### 2. Gamificação e Sistema de Troféus
O sistema calcula automaticamente a porcentagem de aproveitamento das tarefas e atribui troféus em tempo real:

| Símbolo | Nível | Critério (Aproveitamento) |
| :---: | :--- | :--- |
| 🥚 | **Início** | 0% |
| 🥉 | **Bronze** | < 50% |
| 🥈 | **Prata** | 50% - 89% |
| 🥇 | **Ouro** | 90% - 99% |
| 💎 | **Diamante** | 100% (Perfeição) |

### 3. Gestão Temporal e Persistência (LocalStorage)
* **Automático:** O sistema reconhece a data atual. Ao abrir o aplicativo em um novo dia, uma nova lista limpa é gerada automaticamente.
* **Imutabilidade:** Dias anteriores são salvos no histórico e bloqueados para edição, garantindo a integridade dos dados passados.
* **Offline-First:** Todos os dados são salvos no `LocalStorage` do navegador, dispensando conexão com internet ou banco de dados externo.

### 4. Dashboards de Performance
Três cartões visuais no topo da aplicação monitoram o progresso acumulado:
* **Hoje:** Desempenho do dia corrente.
* **Semana Atual:** Soma de todas as estrelas de Domingo a Sábado.
* **Mês Atual:** Visão macro do desempenho mensal (Dia 1 ao dia 30/31).

### 5. Flexibilidade
* Botão **"Adicionar Atividade Extra"** permite a inclusão dinâmica de tarefas esporádicas (ex: lição de casa extra, arrumar o quarto no fim de semana).

---

## 💻 Stack Tecnológica

O projeto foi construído utilizando tecnologias web padrão, sem dependências externas (bibliotecas ou frameworks), garantindo leveza e portabilidade.

* **Frontend:** HTML5 Semântico.
* **Estilização:** CSS3 (Flexbox, Grid Layout, Responsividade Mobile-First).
* **Lógica:** Vanilla JavaScript (ES6+).
* **Armazenamento:** Web Storage API (LocalStorage).
* **Fontes:** Google Fonts ('Comic Neue' para legibilidade infantil).

---

## 📂 Estrutura de Dados

Os dados são armazenados em formato JSON no navegador seguindo a estrutura:

```json
{
  "2023-10-25": [
    {
      "id": 1698245000000,
      "time": "08:00",
      "activity": "Escola",
      "icon": "🏫",
      "status": "star" // ou "x" ou null
    }
  ],
  "2023-10-26": [ ... ]
}
