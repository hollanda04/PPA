### Documentação em Markdown


# Metodologia Processo P + A (PP + A)
*Framework de Eficiência Operacional para Suporte Técnico e Desenvolvimento de Software*

---

## 1. Visão Geral e Propósito

A metodologia **Processo P + A (PP + A)** é um framework ágil de produtividade operacional desenvolvido para eliminar filas acumuladas de chamados (backlogs extensos) e otimizar a vazão de entregas.

A metodologia consiste em fracionar e gerenciar chamados simultaneamente com base na natureza de execução de suas subetapas, aproveitando os tempos mortos de processamento das máquinas para realizar análises e configurações manuais. Quando executada corretamente, a metodologia permite **dobrar a capacidade de resolução de chamados** por operador no mesmo intervalo de tempo.

---

## 2. Conceitos Fundamentais

Cada ticket ou demanda selecionada deve ser fracionada em **subetapas ou processos**, classificados obrigatoriamente em duas categorias:

### 2.1. Processos Ativos (`A|`)
São atividades que exigem a presença, atenção contínua e intervenção manual do operador para progredirem. A velocidade dessas tarefas depende diretamente da ação humana.
* **Exemplos:**
  * Definição e inserção de parâmetros em entradas de dados de sistemas.
  * Leitura e análise crítica de logs de erro.
  * Correção manual de bugs em código e scripts.
  * Configuração manual de parâmetros de rede ou sistema.

### 2.2. Processos Passivos (`P|`)
São atividades automáticas ou semiautomatizadas executadas pela máquina, servidor ou sistema, que exigem pouco ou nenhum acompanhamento manual, mas consomem tempo significativo de espera (tempo de processamento).
* **Exemplos:**
  * Instalação e atualização de softwares e sistemas operacionais.
  * Transferência e sincronização de grandes volumes de arquivos.
  * Execução de rotinas de backup ou migração de banco de dados.
  * Monitoramento visual de rotinas e varreduras de diagnósticos.

---

## 3. Regra de Execução: Multiprocessamento Paralelo

O pilar central do funcionamento do **PP + A** é o encadeamento contínuo entre processos ativos e passivos:

1. **Otimização de Telas (Dual Monitor):** O operador utiliza a tela secundária para manter um **Processo Passivo** em execução (ex: barra de progresso de um backup ou atualização) enquanto utiliza a tela principal para executar um **Processo Ativo** (ex: leitura de log ou ajuste manual).
2. **Encadeamento Contínuo:** Assim que um Processo Passivo é finalizado no segundo monitor, o operador deve, obrigatoriamente, iniciar o próximo Processo Passivo da fila logo em sequência.
3. **Ergonomia Operacional:** O objetivo é garantir que a máquina trabalhe continuamente enquanto o operador realiza tarefas intelectuais/manuais, eliminando o tempo ocioso de espera na frente da tela.

---

## 4. Padronização Visual e Sintaxe

### 4.1. Sintaxe de Identificação
Para garantir legibilidade rápida no Dashboard ou rascunho operacional, os processos recebem no início da sua descrição as letras maiúsculas **A** ou **P** seguidas de uma barra reta (`|`):

* `A|` — Indica Processo Ativo
* `P|` — Indica Processo Passivo

### 4.2. Modelos de Aplicação

#### Opção A: Dashboard Digital (Kanban / Trello / Notion)
Ideal para acompanhamento visual do lote de 2 a 5 tickets simultâneos:

### [SUP-1042] Atualização de Servidor de Aplicação
- [ ] A| Validar arquivos de configuração (.env)
- [ ] P| Executar script de atualização do sistema
- [ ] A| Verificar logs de inicialização do serviço

### [DEV-802] Correção de Script de Migração
- [ ] A| Ajustar sintaxe da query SQL de migração
- [ ] P| Executar script em ambiente de homologação



#### Opção B: Rascunho Rápido em Papel (Modo Ágil/Operacional)

Recomendado quando o operador precisa economizar o tempo de atualização de softwares de gestão de tarefas:

1. [Formatac. PC-04]
   A| Configurar nome e domínio
   P| Download de atualizações Windows Update
   A| Instalar drivers específicos

2. [Backup DB Nefrontec]
   P| Exportar dump do banco PostgreSQL
   A| Redigir relatório de verificação


---

## 5. Estudo de Caso e Validação Prática

### 5.1. Contexto de Aplicação

A metodologia foi validada em ambiente real de suporte técnico de TI. A aplicação ocorreu via solicitação de treinamento direto aos novos colaboradores durante a fase de onboarding, com aprovação da supervisão de TI.

### 5.2. Resultados Alcançados

* **Eliminação Total do Backlog:** A equipe alcançou o marco histórico de **zerar completamente o volume de chamados de Nível 1 (L1)** da empresa.
* **Ganho de Produtividade:** Aumento direto na vazão de resolução de chamados por turno de trabalho, chegando a dobrar a capacidade nominal.
* **Curva de Aprendizado:** Novos colaboradores adaptaram-se quase totalmente ao método em um tempo médio de **2 semanas**.

### 5.3. Mapeamento de Gargalos e Mitigação

| Gargalo Observado | Causa Raiz | Ação Corretiva / Impacto |
| --- | --- | --- |
| **Atraso na Mudança de Foco** *(Context Switching)* | Tempo de reação do operador ao notar a conclusão do processo passivo no 2º monitor. | **Mitigação:** Treinamento e prática diária. O tempo perdido provou ser insignificante e não comprometeu a entrega de demandas prioritárias. |

---

## 6. Checklist de Implementação para Equipes

* [ ] Garantir que os operadores possuem estrutura de trabalho com dois monitores ou ambiente com múltiplos desktops virtuais.
* [ ] Treinar a equipe na identificação imediata do que é `A|` (Ativo) e `P|` (Passivo) no momento da triagem do chamado.
* [ ] Limitar o limite de trabalho em progresso (WIP) para no máximo **5 tickets por lote**.
* [ ] Incentivar o uso de rascunhos em papel para atendimentos de alta velocidade em nível 1.
