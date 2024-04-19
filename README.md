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


 1 - Descrição ::

O jogo chama-se Frogger.

Neste jogo o jogador controla o sapo, e tenta chegar no final do nível.

O Nível tem 2 partes.

Na primeira parte o jogador tem que desviar de quadrados que passam na tela a alta velocidade, se colidir com algum o jogador perde e reinicia o nível.
Na segunda parte, o jogador não pode ter a sua totalidade da hitbox em cima da água.

A condição de vitória deste jogo será o jogador conseguir chegar ao fim do nível.

2 - Como o jogador Perde

No jogo o jogador pode perder de duas formas: ser atingido por um carro ou cair no rio.

	Colisão com Carro

O jogador, representado pelo objeto Froggy, tem de evitar colidir com os carros que se movem horizontalmente através do mapa. A classe ThingManager contém um método chamado CheckCollision() que itera por todos os carros presentes no ecrã. Se for detectada uma colisão entre o sapo e qualquer carro, o jogo considera isso uma derrota.

![1](https://github.com/DigitalGameDevTeam/Monogame---First-Project/assets/148542897/aecc1f05-c3b8-4f88-95d7-79360972e173)



