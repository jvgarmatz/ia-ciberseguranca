# IA para Cibersegurança

Repositório acadêmico com notebooks, atividades e experimentos da disciplina **IA para Cibersegurança**, do **4º período do curso de Segurança da Informação da CESAR School**.

A disciplina explora o uso de inteligência artificial e aprendizado de máquina na análise de dados de segurança, na identificação de ameaças e no apoio à investigação de alertas. As atividades percorrem o ciclo de um projeto de ML: preparação dos dados, seleção de características (*features*), treinamento, avaliação e interpretação dos modelos, considerando o impacto de falsos positivos e falsos negativos na operação de segurança.

**Professor:** Raphael Crespo  
**Instituição:** CESAR School  
**Curso:** Segurança da Informação — 4º período

## Alunos

- João Victor Garmatz
- João Danilo

## Aulas e materiais

Os materiais estão organizados por aula, seguindo a progressão dos fundamentos aos experimentos aplicados à cibersegurança.

| Aula | Tema | Conteúdo e notebook |
| :--- | :--- | :--- |
| **1** | Ambiente e reprodutibilidade | Configuração do Google Colab e Google Drive, organização das pastas, registro de dependências, sementes aleatórias e teste de um pipeline de classificação. [Acessar notebook](Aula%201/setup_aula1_ia_ciberseguranca.ipynb). |
| **2** | Fundamentos de IA e ML | Conceitos de aprendizado supervisionado e não supervisionado, generalização e sobreajuste. Treinamento de um classificador de imagens no Teachable Machine, carregamento em Keras, inferência e avaliação com imagens de teste independentes. [Acessar notebook](Aula%202/aula2_fundamentos_ml_teachable_machine.ipynb). |
| **3** | Dados e features de tráfego de rede | Exploração e limpeza do CIC-IDS2017, classificação de tráfego benigno e ataques com Random Forest, análise da importância das features e comparação com agrupamentos por K-Means e visualização com PCA. [Acessar notebook](Aula%203/aula3_ml_ciberseguranca_cicids2017_1.ipynb). |
| **4** | Métricas, validação e phishing | Classificador de phishing com Random Forest, matriz de confusão, precisão, recall, F1, ROC-AUC, PR-AUC, validação cruzada e análise do efeito do limiar de decisão sobre os erros. O código carrega a base UCI Phishing Websites, com alternativa sintética em caso de falha no download. [Acessar notebook](Aula%204/aulas4_metricas_validacao_phishing_alunos.ipynb). |
| **5** | Modelagem de um detector de malware | Uso de features previamente extraídas de executáveis Windows da base UCI VxHeaven/VirusTotal. Comparação entre baseline e Random Forest, divisão em treino, validação e teste, escolha do limiar, análise das famílias de features e exportação opcional para o Splunk. [Acessar notebook](Aula%205/aula5_modelagem_detector_malware_uci_splunk.ipynb). |
| **6** | Anomalias, UEBA e mineração de processos | Construção de perfis de usuários a partir de logs de eventos, detecção de anomalias com Isolation Forest, LOF e K-Means, priorização de alertas para o SOC e análise de sequências de ações com grafos e escores de raridade. [Acessar notebook](Aula%206/aula6_ueba_anomalias_process_mining_%282%29.ipynb). |

### AV1 — Experimento com o detector de malware

A [avaliação prática AV1](AV1_detector_malware.ipynb) retoma o detector da Aula 5 para comparar o modelo original com alterações no parâmetro `min_samples_leaf` e no limiar de alerta. O experimento mantém a base, as 28 features, as divisões dos dados e a semente aleatória, analisa precisão, recall, F1 e matriz de confusão na validação e reserva o teste para a avaliação final. O notebook fixa o scikit-learn em **1.6.1** para reproduzir os resultados registrados.

## Tecnologias utilizadas

- **Ambiente:** Python, Jupyter Notebook, Google Colab e Google Drive.
- **Análise de dados e visualização:** NumPy, pandas, Matplotlib e Seaborn.
- **Aprendizado de máquina:** scikit-learn, Teachable Machine e TensorFlow/Keras.
- **Mineração de processos:** NetworkX e Graphviz.
- **Integração opcional:** Splunk AI Toolkit, com exportação de features e exemplos de consultas SPL.

## Como utilizar

1. Selecione o notebook na tabela de aulas e abra-o no Google Colab pela opção **Arquivo → Abrir notebook → GitHub**, informando o endereço deste repositório.
2. Execute as células na ordem apresentada e siga as orientações de configuração e instalação de dependências de cada notebook.
3. Nas atividades que utilizam o Google Drive, ajuste a pasta do projeto e autorize a montagem do Drive quando solicitado.
4. Para a Aula 2, prepare o modelo exportado do Teachable Machine e as imagens de teste. As demais atividades de dados utilizam downloads indicados nos próprios notebooks, que dependem de acesso à internet e da disponibilidade das fontes.

Os dados, modelos e arquivos gerados durante as práticas são armazenados no ambiente de execução ou no Google Drive, conforme cada notebook. A Aula 1 gera o `requirements.txt` na pasta do projeto no Drive.

## Contexto dos experimentos

Os materiais têm finalidade didática e incluem discussões sobre desbalanceamento, vazamento de dados, viés de coleta e custo dos erros. Os experimentos de malware trabalham com tabelas de features já extraídas. Resultados obtidos nessas bases devem ser interpretados no contexto de cada atividade e não representam uma validação para uso em produção.
