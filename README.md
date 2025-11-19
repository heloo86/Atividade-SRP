# Atividade-SRP
**Cenário:** Sistema de Gerenciamento de Pedidos

## Contextualização
A empresa fictícia "TechStore" utiliza uma única classe, a ProcessadorDePedido,
para lidar com todo o ciclo de vida de um pedido de um cliente. Isso inclui desde a
verificação inicial do estoque, o cálculo de taxas complexas e a notificação de
sistemas externos (como o gateway de pagamento e o sistema de logística).

O time de desenvolvimento percebeu que esta classe é a mais instável do sistema:
qualquer mudança na regra de frete, no parceiro de pagamento ou na lógica de
notificação obriga a alterá-la, gerando alto risco de quebrar o fluxo de pagamento.

### O Problema: Violação do SRP na ProcessadorDePedido:
Esta classe viola o SRP ao assumir quatro responsabilidades primárias:
1. Validação de Negócio/Disponibilidade (Verificar estoque).
2. Cálculo de Domínio Complexo (Cálculo de frete e impostos).
3. Comunicação Externa/Persistência (Salvar no banco de dados).
4. Comunicação Externa/Integração (Notificar o serviço de e-mail).
