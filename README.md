# Monogame---First-Project

Repositório Original ::
 ->> https://github.com/LubiiiCZ/DevQuickie.git

Grupo :: 
 ->> João Ribeiro // 27926
 ->> Martim Moreira // 22354
 ->> Gonçalo Veloso // 22348

INDICE - 

1 - Descrição

2 - Condição de Derrota

3 - Condição de Vitoria

4 - Geração do Mapa

_________________________________________________________________________________

 1 - Descrição ::

O jogo chama-se Frogger.

Neste jogo o jogador controla o sapo, e tenta chegar no final do nível.

O Nível tem 2 partes.

Na primeira parte o jogador tem que desviar de quadrados que passam na tela a alta velocidade, se colidir com algum o jogador perde e reinicia o nível.
Na segunda parte, o jogador não pode ter a sua totalidade da hitbox em cima da água.

A condição de vitória deste jogo será o jogador conseguir chegar ao fim do nível.

_________________________________________________________________________________

2 - Como o jogador Perde

No jogo o jogador pode perder de duas formas: ser atingido por um carro ou cair no rio.

Colisão com Carros 

O jogador, representado pelo objeto Froggy, tem de evitar colidir com os carros que se movem horizontalmente através do mapa. A classe ThingManager contém um método chamado CheckCollision() que itera por todos os carros presentes no ecrã. Se for detectada uma colisão entre o sapo e qualquer carro, o jogo considera isso uma derrota.

![1](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/aecc1f05-c3b8-4f88-95d7-79360972e173)

Cair no Rio

O jogo apresenta troncos flutuantes que o sapo pode usar para atravessar o rio. No entanto, com o método CheckLogCollision() na classe ThingManager se o sapo tocar na água o jogo considera isso uma derrota.

Com este código 

![2](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/27d97e55-7ea2-49b9-b66f-32dd410f29df)

O jogo está constantemente a realizar as verificações de colisões. Se estas retornarem verdadeiras é chamado o método reset

![3](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/1b9eb292-160d-4c26-bd9e-b6794ed5989b)

_________________________________________________________________________________

3 - Condição de Vitória :

A condição de vitória em Frogger ocorre quando o sapo alcança o fim da tela. Quando o sapo chega a essa área, o jogo dá “freeze” e o jogador é considerado vitorioso. Isso é verificado durante a atualização do jogo, onde uma função verifica se o sapo está na área final. Se sim, o jogo muda para o estado de fim do jogo, indicando que o jogador venceu.

É verificado na classe “PlayState”.

![4](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/80df7001-fecb-4750-b67a-2894b2ce6d04)

Esta linha de código verifica se o sapo (GM.Froggy) está na área “InFinish” do jogo, usando a função InFinish() da classe Background.

![5](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/2adb0098-cdf6-48d9-a17e-dc70841d4d51)

Se o sapo estiver na área de chegada, o estado do jogo é alterado para EndState, indicando que o jogador venceu.

_________________________________________________________________________________

4 - Movimento

No jogo, o movimento é gerido através de entrada do teclado e atualizações regulares de estado.

Controlos

O jogador utiliza as teclas de seta do teclado para controlar o movimento do sapo: 
- Seta para cima: Move o sapo para cima. 
- Seta para baixo: Move o sapo para baixo. 
- Seta para a esquerda: Move o sapo para a esquerda. 
- Seta para a direita: Move o sapo para a direita.

![6](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/c69aece0-1e1e-4065-b1e0-de86ac44bf96)


Atualização do movimento

A atualização do movimento do sapo é gerida pela classe Frog. Esta verifica se o sapo está a mover-se e atualiza a sua posição de acordo com a direção e velocidade definidas.

Se o sapo estiver sobre um tronco flutuante, o movimento é sincronizado com o movimento do tronco. 
Isso permite que o jogador se mova pelo ambiente do jogo de forma dinâmica e interativa.

![7](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/8275572b-b030-45c4-8b80-974f77189733) ![8](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/4e20a11d-ba43-4d05-be87-f088c72c955b)

_________________________________________________________________________________

 5 - Criação do Mapa : 
	
  A classe “BackgroundManager.cs” é responsável por criar o cenário onde o jogo ocorre, 
  
![9](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/bed34172-3091-44d0-8941-689e2a617575)

_river = new(posiçãoX, Globals.TileSize * posiçãoY, Globals.WindowSize.X, Globals.TileSize * altura);

posiçãoX ->> posição horizontal do objeto, como todos são definidos como 0 indica que todos começam no lado esquerdo do tabuleiro 

posiçãoY ->> posição vertical do objeto 

Globals.WindowSize.X ->> comprimento horizontal do objeto, neste caso o objeto está definido para se
estender por toda a tela

altura ->> altura do objeto 


esta função é responsável por definir a o tamanho e a posição das formas que definem o cenário e a função “Draw” é responsável por dar a essas doramas uma cor 

![10](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/233bc1ba-848e-4cad-99f9-1c3420ccb8e3)

A classe “ThingsManager.cs” é responsável por criar todos os objetos pertencentes ao cenário do jogo, e para isso tem duas funções “GenerateLogs” e “GenerateCars”, que são executadas ao iniciar o jogo.

![11](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/51837583-59b7-474e-a76c-37bd44d24fe2) 

(função responsável por criar os troncos) 

![12](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/3ac8e8e7-08a4-4930-9ab7-241b8deaa594)

(função responsável por criar os carros)




   Add(new(new(Globals.TileSize * X, Globals.TileSize * Y, Globals.TileSize * Z, Globals.TileSize),     
        velocidade, new(direção X, direção Y), Color.color))
	
X e Y ->> são a posição da peça 

Z ->> é o tamanho da peça 

velocidade ->> é a velocidade com que a peça de movimenta

direção X e direção Y ->> é a direção do movimento da peça

color ->> é a cor da peça


Sempre que o jogador perde a função “Reset” é responsável por limpar o mapa, 

![13](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/9b24ba3b-5463-428f-ae38-486c01fe729d)

estas linha são responsáveis por limpar as variáveis que armazenam os objetos,

![14](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/e398c16e-24fc-47fa-b641-3ebef8313ddd)

e executar as funções “GenerateLogs” e “GenerateCars” novamente para construir o mapa original.

![15](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/b8b35958-1c24-42f1-8df4-4e5a49cf476f)


















