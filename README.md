# shared_memory_in_parallel_code_

_Computadores ensinam bastante coisa! Por exemplo, no caso do fork(), o processo filho, embora seja uma cópia do pai, ele é apenas uma cópia! Suas memórias são agora -- após child_pid = os.fork() -- suas memórias! Já com multi-threading as threads compartilham o mesmo espaço na memória. O q gera condiçoes indesejaveis como deadlocks, racecondition (qnd dois processos acessam a mesma regiao da memoria) e td mais...__

<br>

Exemplo: <br>

```python
import os

def main():
    main_buffer = ["AAAAAAAAAAAAAAAAAAAAAAA"]   
    child_pid = os.fork()
    
    if child_pid == 0:
        main_buffer.append("FFFFFFFFFFFFFFFFFFFFFF")
        os._exit(0)
        
    os.waitpid(child_pid, 0) 
    print(main_buffer)     # <---- Irá imprimir AAAAAAAAAAAAAAAAAAAAAAA

```
<br>

# " <br>
_Estátuas e cofres_ <br>
_E paredes pintadas_ <br> 
_Ninguém sabe o que aconteceu_ <br>
_Uhm, uhm, ela se jogou da janela do quinto andar_ <br>
_Nada é fácil de entender_ <br>
<br>
_Dorme agora, uhm, uhm, uhm_ <br>
_É só o vento lá fora_ <br>
<br>
_Quero colo, vou fugir de casa_ <br>
_Posso dormir aqui com vocês?_ <br>
_Estou com medo, tive um pesadelo_ <br>
_Só vou voltar depois das três_ <br>
_Meu filho vai ter nome de Santo_ <br>
_Quero o nome mais bonito_ <br>
<br>
_É preciso amar_ <br>
_As pessoas como se não houvesse amanhã_<br>
_Porque se você parar pra pensar_<br>
_Na verdade não há_<br>
<br>
_Me diz por que que o céu é azul_<br>
_Explica a grande fúria do mundo_<br>
_São meus filhos que tomam conta de mim_<br>
<br>
_Eu moro com a minha mãe_<br>
_Mas meu pai vem me visitar_<br>
_Eu moro na rua, não tenho ninguém_<br>
_Eu moro em qualquer lugar_<br>
_Já morei em tanta casa, que nem me lembro mais_<br>
_Eu moro com os meus pais_<br>
_Oh, oh, oh_<br>
<br>
_É preciso amar_<br>
_As pessoas como se não houvesse amanhã_<br>
_Porque se você parar pra pensar_<br>
_Na verdade não há_<br>
<br>
_Sou uma gota d'água_<br>
_Sou um grão de areia_<br>
_Você me diz que seus pais não lhe entendem_<br>
_Mas você não entende seus pais_<br>
_Você culpa seus pais por tudo_<br>
_E isso é absurdo_<br>
_São crianças como você_<br>
_O que você vai ser_<br>
_Quando você crescer?_
" <br>

_<b>(Pais e Filhos/Legiao Urbana)</b>_

<br>
<br>
