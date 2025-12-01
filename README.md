# Utilização de chatbots como ferramentas de estudo para alunos do curso de Fisioterapia da UFSC - Campus Araranguá

Alunos: Guilherme da Silva Trajano e Luan Daniel de Oliveira Melo

## Introdução e Objetivos

Este projeto foi desenvolvido como uma parte do trabalho da disciplina de Projeto de Sistemas Ubíquos e Embarcados do curso de Engenharia de Computação e em parceria com alunos e professores do curso de Fisioterapia. 

A utilização de modelos de inteligência artificial tem ganhado muita força nos últimos anos, e cada vez mais pesquisas têm surgido sobre possibilidade destas ferramentas serem utilizadas para auxiliar alunos em seus estudos. Um dos softwares mais utilizados recentemente é o NotebookLM (https://notebooklm.google.com/), desenvolvido pela Google. Ele fornece uma interface de conversação entre usuários humanos e o modelo de IA (um LLM) que está rodando por trás. A plataforma permite aos usuários adicionar PDFs (como artigos científicos), gerar resumos em áudio e vídeo, testes, dentre outras funcionalidades. Tudo isso torna essa ferramenta bastante promissora para ser utilizada como suporte aos estudos de alunos da graduação. 

Dessa forma, essa plataforma foi apresentada e explicada a colaboradores do curso de Fisioterapia da UFSC - Campus Araranguá que visam compreender os impactos que a utilização de tais ferramentas tem no desemepenho acadêmico de seus alunos. Além disso, foram também apresentadas técnicas de engenharia de prompt para que os alunos obtenham o melhor desemepenho do chatbot. 

## Configuração do Software

<img width="1365" height="599" alt="image" src="https://github.com/user-attachments/assets/72d7b020-d96a-437e-9e43-e2dafc065ed2" />

A interface do software está apresentada na imagem acima. 

- O campo "Fontes" permite ao usuário adicionar arquivos e materiais, como livros e artigos científicos, para que o modelo utilize como contexto em suas respostas e apresente as informações com a precisão que o usuário deseja. 

- No campo "Conversa" está a interface de conversação do usuário com o modelo, que utilizará como base para as suas respostas o que foi adicionado no campo "Fontes".

- Já o campo "Estúdio" apresenta diversos recursos que permitem ao usuário criar, com base nos arquivos definidos como contexto e no próprio histórico de conversação, novos materiais, indo desde criação personalizada de resumos em áudio e vídeo, que permitem ao usuário definir características muito específicas de como eles devem ser criados (como idioma, tempo de duração, um assunto específico como o único a ser tratado, etc.), até mesmo a pequenos testes que podem ser personalizados à vontade do usuário (desde o número de questões até mesmo à estrutura das respostas). 

<img width="1363" height="601" alt="image" src="https://github.com/user-attachments/assets/0e998cbd-4595-4927-b110-7ece4b6c004e" />

O campo apresentado acima possui uma das funcionalidades mais importantes para a utilização neste projeto, que é a de alteração do prompt de sistema. Ele permite a um usuário com acesso de editor guiar o modelo em suas respostas, estabelecendo regras que devem seguidas e estruturas específicas das respostas. 



### Visão Geral

Uma das limitações da ferramenta é o limite máximo de caracteres para o uso do prompt do sistema. Foi fornecido a nós prompts que os colaboradores do curso de fisioterapia desenvolveram, mas estes ultrapassavam o limite de caracteres do software. Por conta disso, foi necessário realizar engenharia de prompt, visando diminuir o tamanho do prompt mas mantendo o fluxo, a coerência e as regras que devem ser seguidas. Por conta disso, o prompt desenvolvido foi dividido em duas partes. A primeira parte foi separada para ser utilizada como a primeira mensagem na interação com o chatbot. Ela, portanto não estaria presente no prompt do sistema, mas utilizá-la no ínicio da conversa é suficiente para manter a coerência em conversas que não ficam muito longas. O exemplo desenvolvido foi:

> Você é um tutor especialista em neurociência da dor para estudantes de fisioterapia. Seu papel é ensinar de forma clara e baseada em evidências. 

>Tema: BLOCO 1 - Fundamentos da Dor

>1. Definição de dor segundo a IASP
>2. Função protetora e adaptativa da dor
>3. Dor como doença e classificações clínicas
>4. Mecanismos de dor: nociceptiva, neuropática e nociplástica
>5. Modificações neurais que diferenciam dor aguda e dor crônica.

>Os tópicos devem ser explicados um de cada vez, iniciando pela “Definição de dor segundo a IASP” e seguindo fielmente as regras de condução descritas, indo para o próximo tópico apenas após o aluno dizer que está pronto.

Já a segunda parte, que contém as regras de condução, foram definidas e ajustadas para estarem no prompt do sistema. Seria ela:

>Regras de condução: 
>Cada tópico deve ter no máximo 3-6 parágrafos. 
>Mantenha uma linguagem acessível, mas sem perder o rigor científico. 
>Aponte e corrija equívocos comuns dos estudantes.
>Finalize com 2 perguntas de checagem de compreensão.
>Adapte o nível da explicação conforme as respostas dos estudantes. Se eles errarem nas questões, volte ao ponto em que houve confusão e explique novamente com outro exemplo.
>Só avance para o próximo tópico se o aluno responder que está pronto.

Dessa forma, nós guiamos o modelo para responder como os colaboradores desejam, contornando as limitações da plataforma.

Porém, um dos problemas apresentados foi relacionado ao modelo não realizar a checagem da veracidade da resposta do aluno ao final de cada conteúdo e simplesmente passar a explicar o próximo tema. Para solucionar isso, foi necessário alterar as regras de condução no prompt e exigir explicitamente a verificação das respostas do aluno antes de prosseguir. 

### Considerações Finais

A plataforma apresentada e explicada teve grande aceitação pelo professor responsável pelo projeto e pelos seus alunos que iriam desenvolver os trabalhos em cima dela com os alunos da graduação. A capacidade de adicionar um número muito grande de fontes ao software chamou bastante atenção, e a possibilidade de gerar resumos em áudio e vídeo com fluxo e coerência totalmente naturais, além de testes personalizados e outros materiais de estudo foi bastante elogiada pelo colaboradores. 

Além disso, a engenharia de prompt se mostrou eficaz, onde nos foram apresentadas dúvidas com relação à formulação dos prompts e estas foram solucionadas utilizando técnicas como as apresentadas acima. 
