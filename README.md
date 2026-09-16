# shared_memory_in_parallel_code_

_Computadores ensinam bastante coisa! Por exemplo, o caso do fork().. Quando o processo filho é gerado com os.fork() , embora ele seja uma cópia do pai, ele é apenas uma cópia! Suas memórias são suas memórias - ou seja, nao compartilha dos endereços de memória do processo pai.. (veja exemplo abaixo)_

_Já com multi-threading....  As threads compartilham o mesmo espaço na memória! Isso gera condiçoes indesejaveis como deadlocks, racecondition (qnd dois ou mais processos acessam a mesma regiao da memoria) Etc...__ 

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

_Embora houve um append() em main_buffer a chamada à funçao print(main_buffer), do proc principal, continua com o mesmo conteudo_

NOTE: REVISAR TD ISSO AE.

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


....


_<b>(Pais e Filhos/Legiao Urbana)</b>_

<br>
<br>
