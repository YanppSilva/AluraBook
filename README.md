**API - Interface de Progamação de Aplicações:**

Ela permite que dois componentes de software se comuniquem. Chamamos esses dois lados de cliente e servidor. Então, a API fica no meio fazendo a conexão. O cliente faz uma solicitação para essa API, ela faz os trâmites e pede ao servidor para retornar a resposta. Sua arquitetura geralmente é explicada em termos de cliente e servidor. A aplicação que envia a solicitação é chamada de cliente e a aplicação que envia a resposta é chamada de servidor.

**Fetch:**
método é assíncrono e tem como parâmetro obrigatório a URL da API(sempre retorna uma PROMISE)

        # Sintaxe:

            var consultaCEP = fetch('https://viacep.com.br/ws/01001000/json/');
            console.log(consultaCEP)

**Promise:** 
Assim como sua tradução, é uma promessa de que algo vai acontecer. Como retorno , ela pode ser resolvida ou rejeitada. isso permite que métodos assíncronos se tornem síncronos. Ou seja, ao invés de retornar um valor específico, o valor final, como ainda não chegou lá, ele retorna uma promessa que esse valor uma hora vai chegar,
        
        # Sintaxe:

            const entrega = new Promise(function
                (resolve, reject) {
                    if (recebeu == true) {
                        resolve('Ana recebeu a encomenda!')
                    } else {
                        reject('Não foi possível receber a encomanda!')
                    }
                })

            //é composta por uma função com os parâmetros Resolve e Reject. Se essa promessa foi resolvida, ela vai ser chamada de função Resolve e enviará uma mensagem ou fará alguma ação que você definiu que fosse acontecer. Se ele não recebeu, chamamos a função de Reject e enviamos uma mensagem indicando que não foi possível essa entrega.

            # Promise all();

            O método Promise.all(iterable) retorna uma única Promise que resolve quando todas as promises no argumento iterável forem resolvidas ou quando o iterável passado como argumento não contém promises. É rejeitado com o motivo da primeira promise que foi rejeitada.

                Promise.all(iterable);


**Catch**
O método catch retorna uma Promise e lida apenas com casos rejeitados. Ele possui o mesmo comportamento de quando chamamos Promise.prototype.then(undefined, onRejected)

        # Sintaxe
            
            p.catch(onRejected);

            p.catch(function(motivo) {
                // rejeição
            });

        //o metodo pega(catch) o dado que foi lançado(throw Error) como rejeitado e lança uma mensagem de erro para o user

**Finally**
O método finally retorna uma promise. Quando a promise for estabelecida, tenha ela sido realizada ou rejeitada, executa-se a função callback especificada. Isso permite a execução de uma código que acontecerá indepedentemente da promise ter sido realizada (com sucesso) ou rejeitada (com falha)

**async await**
Async/Await foi declarada pela ES em 2017 para facilitar a leitura dos códigos assíncronos. Porque, apesar de ser assíncrono, ele é construído como um código síncrono. Ou seja, parece que é feito linha por linha, mesmo que, no fundo, ele esteja esperando uma coisa acontecer antes de fazer a outra. Apenas definindo a função como async, podemos usar essa palavra await. Ou seja, se você tentar colocar esse await em qualquer lugar que não seja uma função assíncrona, vai dar problema. Ele vai te cobrar que ela só é aceita dentro de uma função assíncrona.

        # Sintaxe

            async function nome([param[, param[, ... param]]]) {
                instruções
            }

        //Uma função assíncrona pode conter uma expressão await, que pausa a execução da função assíncrona e espera pela resolução da Promise passada, e depois retoma a execução da função assíncrona e retorna o valor resolvido.