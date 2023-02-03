# :money_with_wings: Sistema de fila para compra de ingressos :money_with_wings:
Um sistema de compra de ingressos online é projetado para gerenciar a demanda por ingressos para eventos e garantir que a compra de ingressos seja justa e equilibrada. 

## :pencil2: Diagrama de Caso de Uso 
![alt text](https://github.com/samyiuel/Diagrama-de-Compras/blob/main/diagrama_de_caso_uso_sistema_compra_de_ingressos.jpeg)

## :page_with_curl: Levantamento de requisitos

- *Funcionalidades de compra de ingressos:* O sistema deve permitir que os usuários comprem ingressos para o evento, selecionando a data, horário e setor desejado. Deve ser possível escolher a quantidade de ingressos a serem comprados e verificar a disponibilidade de ingressos antes da finalização da compra.

- *Cadastro de usuários:* O sistema deve permitir que os usuários criem uma conta com informações pessoais, incluindo endereço de e-mail e informações de pagamento. Isso deve permitir que o usuário acesse seus ingressos comprados anteriormente e faça compras futuras com mais facilidade.

- *Métodos de pagamento:* O sistema deve oferecer várias opções de pagamento, incluindo cartões de crédito, débito e boletos bancários. Deve ser possível verificar o status da transação de pagamento e receber confirmações por e-mail.

- *Gerenciamento de ingressos:* O sistema deve permitir que os usuários administradores gerencie esses ingresos.

- *Fila de espera:* Quando há muitos usuários tentando comprar ingressos ao mesmo tempo, o sistema coloca esses usuários em uma fila de espera. A fila é processada em ordem cronológica, garantindo que todos tenham a chance de comprar ingressos.

- *Contador de tempo:* O sistema conta o tempo que cada usuário passa na fila de espera e garante que eles tenham um tempo limitado para completar a compra de ingressos. Se o tempo limite expirar antes que o usuário complete a compra, o sistema o remove da fila e permite que o próximo usuário avance.

- *Notificações em tempo real:* O sistema envia notificações em tempo real para os usuários na fila de espera e quando a compra é realizada.

##  :bulb: Outros requisitos que também são legais

- *Gerenciamento de estoque:* O sistema deve ser capaz de monitorar a quantidade de ingressos disponíveis e atualizar a fila de espera de acordo com a disponibilidade. Isso garante que não haja overbooking e que todos tenham a chance de comprar ingressos enquanto houver disponibilidade.

- *Segurança de dados:* O sistema deve implementar medidas de segurança para proteger as informações pessoais dos usuários, incluindo informações de pagamento. Deve ser criptografado e ter autenticação de usuários para garantir que somente o usuário autorizado tenha acesso a sua conta e informações de compra.

- *Relatórios e análises:* O sistema deve oferecer relatórios e análises para a equipe de eventos, incluindo estatísticas de venda de ingressos, distribuição de ingressos por setor e outras informações relevantes.

- *Suporte ao usuário:* O sistema deve oferecer suporte ao usuário, incluindo ajuda com questões técnicas, problemas de pagamento e questões gerais sobre a compra de ingressos.

## :computer: Algoritmo em python com a lógica pensada:

```python

queue = []

def buy_ticket(name):
    queue.append(name)
    return f"{name} adicionado à fila com sucesso."

def next_customer():
    if len(queue) == 0:
        return "Não há mais clientes na fila."
    else:
        next_person = queue.pop(0)
        return f"Próximo cliente na fila é {next_person}."

```
        
Este algoritmo define duas funções: buy_ticket e next_customer. A função buy_ticket adiciona um nome à fila (representada pela lista queue) e retorna uma mensagem de confirmação. A função next_customer retorna o próximo cliente na fila (removido da lista) ou uma mensagem indicando que a fila está vazia.
