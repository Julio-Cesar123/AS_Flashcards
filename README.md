# Flashcards - Projeto de AS
- O projeto será trabalhado baseando-se nos conceitos abaixo:
1. carregar um conjunto contendo 10 flashcards, pelo menos;
2. virar um flashcard a cada solicitação do usuário;
3. passar para outro flashcard a pedido do usuário;
4. sortear um flashcard, quando o usuário desejar;
5. mostrar quantos flashcards o usuário corretamente se lembrou;
6. suportar a inserção e remoção de flashcards;
7. ser executado em desktops e celulares;
8. permitir que um usuário troque flashcards com outro usuário;
9. a aplicação deverá “animar” um flashcard sempre que ele for virado;
10. basear-se na proposta de Leitner quando do sorteio de flashcards.

- A lógica geral do projeto segue o diagramas UML abaixo:

![Figura 1: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Legenda.png) 
![Figura 2: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte1.png) 
![Figura 3: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte2.png) 
![Figura 4: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte3.png) 
![Figura 5: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte4.png) 
![Figura 6: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte5.png) 
![Figura 7: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte6.png) 
![Figura 8: Diagrama UML](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Parte7.png) 

## Modelagem de Arquitetura
### Visão lógica

- A funcionalidade do sistema e sua aplicação em cenários reais é relacionada a criação de um programa em Python que implementa a proposta Leitner com a utilização de flashcards para auxiliar o usuário final no estudo de tópicos de sua escolha.
O usuário fornecerá os tópicos que logicamente serão armazenados na parte da frente dos flashcards, e as respostas que serão armazenadas na parte de trás. Agora utilizando do método Leitner, será necessário a categorização de dificuldade dos tópicos para o usuário, introduzindo-os em cada caixa como na imagem a seguir:


![Figura 9: Sistema Leitner (autor: ZIRGUEZI)](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Leitner.png)

- Logo após, o usuário começará o método de estudo respondendo às perguntas da caixa 1, que são categorizadas como mais difíceis, ou seja, que o usuário mais precisa treinar para memorizar a resposta, tendo as respondido corretamente, elas são transferidas para as caixas em diante, no exemplo, as caixas 2 e 3, categorizadas como médias e fáceis, respectivamente, que devido à dificuldade reduzida, demoram mais tempo para aparecer para o usuário. Entretanto, quando estes flashcards aparecerem, e o usuário acaba errando a resposta, elas retornam a caixa um, demonstrando que o usuário ainda não conseguiu memorizar o conceito, portanto necessita retomar o tópico para concretizar o assunto em sua cabeça, e assim continua o ciclo da utilização dos flashcards do método em questão.



### Visão do processo
- Com relação a visão do processo, no âmbito do projeto, se tratando de um sistema desenvolvido na linguagem Python, não notamos essencialmente a necessidade de aplicar contundentemente qualquer conceito relacionado a partes dinâmicas (escalabilidade, distribuição e etc.), nosso projeto fará do uso, contudo, de simultaneidade por exemplo, para atender ao requisito de "animação" de virar um flashcard. Nessa animação será necessário a aplicação de Multithreading.

### Visão de desenvolvimento 
- Como visão de desenvolvimento, temos como intuito a utilização da tecnologia de implementação denominada Python. Escolhemos essa linguagem de programação devido buscarmos um projeto mais eficiente, dessa forma utilizaremos a nossa familiarização com a linguagem, e a disponibilidade e variedade de bibliotecas que nos auxiliarão no desenvolvimento do projeto, além disso utilizaremos um ambiente de desenvolvimento integrado chamado de Visual Studio Code devido a sua disponibilidade de ferramentas.
Na questão das necessidades do projeto, precisamos implementar a proposta Leitner com a utilização de flashcards, portanto deveremos programar a lógica do mesmo, levando em consideração que devemos necessariamente implementar os requisitos citados no início deste documento.
Para isso, vamos dividir o projeto em tarefas menores e atribuir prazos para cada uma delas. Isso nos ajudará a manter o projeto organizado e a garantir que estamos progredindo em um ritmo adequado. Além disso, decidimos que o modelo de processo que melhor se adaptará com o nosso projeto é a modelo Spiral, pois ele "fornece potencial para o rápido desenvolvimento de versões cada vez mais completas do software" (PRESSMAN, 2011, p.65), segue abaixo uma imagem do modelo:

![Figura 10: Modelo Spiral (PRESSMAN)](https://raw.githubusercontent.com/Julio-Cesar123/AS_Flashcards/screenshots/Modelo_Spiral.jpg)

### Visão física
- A visão física do projeto mostra-se bem simples por ser um projeto que funciona no computador unicamente, se tratando de um código em python que pode ser executado normalmente sem maiores requerimentos relacionados a hardware. Somente estamos descrevendo um arquivo executável gerado por compilação no próprio Visual Studio. Logo basta um computador para a versão de desktop e um celular android para a versão mobile.

## Modelagem de requisitos
### Casos de Uso
#### Estrutura dos casos de uso
Os casos de uso serão estruturados da seguinte maneira:
1. Objetivo
2. Pré-condições
3. Descrição
4. Pós-condições

Será considerado nos casos de usos como ator primário padrão o usuário final do sistema, ou seja, aquele usa os flashcards. Além disso, os casos de uso explicitados serão os do _"happy end"_ - casos de uso onde o processo ocorre conforme o esperado e sem variações.

#### Descrevendo alguns casos de uso
#### Criação de um novo flashcard
- Objetivo: ter um novo flashcard armazenado no aplicativo
- Pré-condições: N/A
- Descrição:
1. Usuário clica no botão de "criar novo flashcard"
2. Aparecem todos os flashcards existentes no sistema em uma nova interface
3. Na interface aparecem uma caixa de título do card e uma de descrição do card
4. O usuário coloca o título e a descrição do card
5. O usuário aperta o botão "adicionar card"
6. O flashcard é criado
7. Aparece o menu inicial
- Pós-condições: O flashcard fica armazenado no banco de dados com id único

#### Deletar um flashcard
- Objetivo: o usuário deseja excluir um flashcard do aplicativo
- Pré-condições: ter flashcards disponíveis no banco de dados
- Descrição:
1. Usuário clica no botão de "deletar um flashcard"
2. Aparecem todos os flashcards existentes no sistema em uma interface, com uma coluna permitindo selecionar flashcard
3. Na mesma interface, aparece uma caixa de texto requirindo o id do card a ser deletado.
4. O usuário coloca o id do card ou seleciona eles
5. O usuário aperta o botão "deletar card"
6. Aparece o menu inicial
7. Aparece um aviso mostrando que os flashcards foram deletados
8. O usuário clica em "Ok".
- Pós-condições: O flashcard é excluído do armazenamento

#### Ver todos os flashcards
- Objetivo: o usuário deseja visualizar todos os flashcards
- Pré-condições: devem existir flashcards existentes no sistema
- Descrição:
1. Usuário clica no botão de "mostrar todos os flashcards"
2. Aparecem todos os flashcards existentes no sistema em uma nova interface
3. O usuário aperta no botão de "X"
4. Aparece o menu inicial
- Pós-condições: N/A

#### Exportação de flashcards
- Objetivo: um arquivo com os flashcards selecionados serão colocados em um arquivo json
- Pré-condições: devem existir flashcards existentes no sistema
- Descrição:
1. Usuário clica no botão de "exportar flashcards" no menu inicial
2. Um arquivo json é armazenado no computador do usuário
3. Aparece uma tela de compartilhamento para compartilhar os flashcards com outro usuário (por meio do arquivo)
4. O usuário clica em cancelar
5. Aparece o menu inicial
- Pós-condições: O arquivo com os flashcards selecionados é armazenado no dispositivo

#### Importação de flashcards
- Objetivo: o aplicativo terá os flashcards do arquivo importado
- Pré-condições: devem existir um arquivo json no formato padrão do app no computador do usuário
- Descrição:
1. Usuário clica no botão de "importar flashcards" no menu inicial
2. Aparece o explorador de arquivos padrão do sistema
3. O usuário navega no explorador até achar o arquivo
4. O usuário seleciona o arquivo de flashcards
5. Os flashcards são lidos pelo sistema
6. Aparece um aviso dizendo que os arquivos foram importados
7. O usuário clica em "Ok"
8. Aparece o menu inicial
- Pós-condições: ter flashcards novos no sistema

#### Sessão de estudo
- Objetivo: a sessão de estudo com os flashcards será iniciada
- Pré-condições: devem existir pelo menos 10 flashcards no sistema
- Descrição:
1. Usuário clica no botão de "estudar" no menu inicial
2. Aparece uma interface com o flashcard sorteado no meio, e no canto inferior os botões "Fácil", "Médio", "Difícil" ou "Sair".
3. O usuário aperta no título do flashcard e aparece a descrição dele no meio da interface 
4. O usuário aperta em um dos botões conforme a necessidade
5. Aparece outro flashcard, repetindo o passo 2 até todos os flashcards serem usados
6. Aparece uma nova interface mostrando quantos flashcards o usuário corretamente se lembrou ou não
7. O usuário aperta no botão de voltar
8. Aparece o menu inicial
- Pós-condições: Os flashcards foram estudados e só poderão ser estudados novamente conforme o algoritmo do programa.

# Referências
- PRESSMAN, Roger S. Engenharia de Software: Uma Abordagem Profissional. 7 ed. Porto Alegre: AMGH, 2011.

- KRUCHTEN, Philippe.  Architectural Blueprints—The “4+1” View
Model of Software Architecture. The University of British Columbia, Vancouver, nov 1995. Disponível em: <https://www.cs.ubc.ca/~gregor/teaching/papers/4+1view-architecture.pdf> Acesso em: 01 abr. 2023.
