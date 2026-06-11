# OKRs Tecnologia 2026 — Painel de Controle

Painel web para monitorar, acompanhar e validar as entregas dos OKRs da área de Tecnologia da BIUD (Governança 2026). Site estático, hospedado no GitHub Pages, sem backend e sem dependência de equipe técnica para operar.

🔗 **Acesso ao painel:** `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO`
*(substitua pelo endereço real após ativar o GitHub Pages)*

---

## O que o painel faz

- Acompanha **2 objetivos (TEC-O1 e TEC-O2)**, seus KRs e atividades
- Calcula o **status automaticamente** a partir das datas — ninguém escolhe cor de farol
- Exige **evidência registrada** (link ou texto) para concluir qualquer atividade ou KR
- Filtros por objetivo, cadeira responsável, status e busca por texto
- Registro de métricas por KR (baseline, valor atual e meta)

### Regras de status (calculadas, não escolhidas)

| Status | Regra |
|---|---|
| ⚪ Não iniciado | Sem registro de início e a mais de 15 dias do prazo |
| 🔵 Em andamento | Iniciada, não concluída, a mais de 15 dias do prazo |
| 🟠 Atenção | Não concluída e a 15 dias ou menos do prazo (iniciada ou não) |
| 🔴 Atrasada | Não concluída com prazo vencido |
| 🟢 Concluída | Finalizada **com evidência registrada** — sem evidência, não conclui |

Atividades sem prazo próprio **herdam o prazo do KR**.

---

## Perfis de acesso

| Perfil | O que pode fazer |
|---|---|
| **Administrador** | Editar tudo: iniciar/concluir atividades, registrar evidências, métricas, prazos e descrições |
| **Visualizador** | Somente leitura: vê status, evidências, métricas e descrições, sem nenhum botão de edição |

O acesso é feito por senha única na tela de login — o painel identifica o perfil automaticamente pela senha informada.

> ⚠️ **Sobre segurança:** este é um site estático público. As senhas organizam o acesso, mas não garantem sigilo — os dados do painel ficam em arquivo público no repositório. Não registre informações confidenciais ou dados pessoais de clientes.

---

## Como publicar o painel (primeira vez)

1. Crie um repositório **público** no GitHub
2. Faça upload dos arquivos pelo navegador (**Add file → Upload files**):
   - `index.html` — o painel
   - `dados.json` — os dados dos OKRs (se aplicável à sua versão)
3. Vá em **Settings → Pages**
4. Em *Source*, selecione **Deploy from a branch** → branch `main` → pasta `/ (root)` → **Save**
5. Aguarde 1–2 minutos e acesse o endereço gerado

---

## Como atualizar os dados (rotina do administrador)

1. Abra o painel e entre como **administrador**
2. Registre as atualizações: iniciar atividades, concluir com evidência, atualizar métricas
3. Clique em **Exportar** — o navegador baixa o arquivo de dados atualizado
4. No GitHub, abra o repositório → **Add file → Upload files** → arraste o arquivo baixado (substituindo o anterior) → **Commit changes**
5. Em 1–2 minutos, todos os visualizadores passam a ver a versão nova

💡 Cada atualização fica registrada no histórico do GitHub — auditoria gratuita de quem mudou o quê e quando.

---

## Estrutura do repositório

```
├── index.html    → o painel (interface completa, sem dependências externas)
├── dados.json    → estado atual dos OKRs (atividades, evidências, métricas)
└── README.md     → este arquivo
```

---

## Perguntas frequentes

**O visualizador precisa de conta no GitHub?**
Não. Basta o link do painel e a senha de visualizador.

**Fechei o navegador, perco algo?**
Não — o estado oficial é o que está publicado no repositório. Edições não exportadas/enviadas ficam só na sua sessão, então sempre finalize a rotina com Exportar + Upload.

**Posso restaurar uma versão anterior?**
Sim. No GitHub, abra o histórico de commits do arquivo de dados e restaure qualquer versão anterior.

**O painel funciona no celular?**
Sim, o layout é responsivo — ideal para consulta dos visualizadores.

---

## Fonte

OKRs_Tecnologia — BIUD Governança 2026. Status derivado das datas registradas no próprio painel.
