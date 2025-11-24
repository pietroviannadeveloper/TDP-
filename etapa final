#include <stdio.h>



// Declaração de variáveis e criação da estrutura Tarefa

struct Tarefa {

  char titulos[100];

  char descricoes[150];

  int prioridades;

  int diasRestantes;

};



// Declaração das Funções

void cadastrarTarefas(struct Tarefa tarefas[], int *quantidade);

void listarTarefas(struct Tarefa tarefas[], int quantidade);

void editarTarefa(struct Tarefa tarefas[], int quantidade);

void removerTarefa(struct Tarefa tarefas[], int *quantidade);



// Programa para exibição do menu

int main() {

  struct Tarefa tarefas[50];

  int quantidade = 0;

  int num;



  do {

    printf("\n----- MENU DE OPCOES -----\n");

    printf("1 - Cadastrar tarefas\n");

    printf("2 - Listar tarefas\n");

    printf("3 - Editar tarefa\n");

    printf("4 - Remover tarefa\n");

    printf("5 - Finalizar\n");

    printf("Escolha uma opcao (1 a 5): ");

    scanf("%d", &num);



    switch(num) {

      case 1:

        cadastrarTarefas(tarefas, &quantidade);

        break;



      case 2:

        listarTarefas(tarefas, quantidade);

        break;



      case 3:

        editarTarefa(tarefas, quantidade);

        break;



      case 4:

        removerTarefa(tarefas, &quantidade);

        break;



      case 5:

        printf("Finalizado.\n");

        break;



      default:

        printf("Opcao invalida!\n");

    }

  } while(num != 5);



  return 0;

}



// Função para cadastrar tarefas

void cadastrarTarefas(struct Tarefa tarefas[], int *quantidade) {

  int num, qtd;



  // Pergunta quantas tarefas deseja cadastrar

  printf("\nQuantas tarefas deseja cadastrar? ");

  scanf("%d", &qtd);



  // Estrutura de repetição para cadastrar várias tarefas

  for (num = *quantidade; num < *quantidade + qtd; num++) {

    printf("\nCadastro da Tarefa %d\n", num + 1);



    printf("Digite o título: ");

    scanf("%s", tarefas[num].titulos);



    printf("Digite a descrição: ");

    scanf("%s", tarefas[num].descricoes);



    printf("Digite a prioridade (1-Baixa, 2-Média, 3-Alta): ");

    scanf("%d", &tarefas[num].prioridades);



    printf("Digite os dias restantes: ");

    scanf("%d", &tarefas[num].diasRestantes);

  }



  *quantidade += qtd;

}



// Função de listar para exibir as tarefas cadastradas

void listarTarefas(struct Tarefa tarefas[], int quantidade) {

  if (quantidade == 0) {

    printf("\nNenhuma tarefa cadastrada, adicione para aparecer!\n");

    return;

  }



  int num;



  printf("\n----- Lista de Tarefas -----\n");



  for (num = 0; num < quantidade; num++) {

    printf("\nTarefa %d:\n", num + 1);

    printf("Título: %s\n", tarefas[num].titulos);

    printf("Descrição: %s\n", tarefas[num].descricoes);

    printf("Prioridade: %d\n", tarefas[num].prioridades);

    printf("Dias restantes: %d\n", tarefas[num].diasRestantes);



    printf("\n");



    //Exibição do status da tarefa

    printf("Status da Tarefa: ");

     

    switch (tarefas[num].prioridades) {

      case 1: 

        printf("Tarefa de baixa prioridade.\n"); 

        break;

      case 2: 

        printf("Tarefa de média prioridade.\n"); 

        break;

      case 3: 

        printf("Tarefa de alta prioridade.\n"); 

        break;

      default: 

        printf("Declaração de prioridade inválida, escreva um número de 1-3.\n"); 

        break;

    }



    //Vencimento do prazo

    if (tarefas[num].diasRestantes <= 0) {

      printf("O prazo de entrega está vencido.\n");

    } else {

      printf("%d dia/s para a entrega da tarefa.\n", tarefas[num].diasRestantes);

    }

  }

}



// Função para editar a tarefa

void editarTarefa(struct Tarefa tarefas[], int quantidade) {

  int num_id;



  if (quantidade == 0) {

    printf("\nNao existem tarefas para editar.\n");

    return;

  }



  listarTarefas(tarefas, quantidade); //Exibição de listagem de tarefas



  printf("\nDigite o número da tarefa que deseja editar: ");

  scanf("%d", &num_id);



  if (num_id < 1 || num_id > quantidade) {

    printf("Tarefa inválida!\n");

    return;

  }



  // Estrutura para editar tarefa

  num_id--; 



  printf("\nNovo título: ");

  scanf("%s", tarefas[num_id].titulos);



  printf("Nova descrição: ");

  scanf("%s", tarefas[num_id].descricoes);



  printf("Nova prioridade (1-Baixa, 2-Média, 3-Alta): ");

  scanf("%d", &tarefas[num_id].prioridades);



  printf("Novos dias restantes: ");

  scanf("%d", &tarefas[num_id].diasRestantes);



  printf("Tarefa atualizada com sucesso!\n");

}



// Função para remover tarefa cadastrada

void removerTarefa(struct Tarefa tarefas[], int *quantidade) {

  int num_id;



  if (*quantidade == 0) {

    printf("\nNao existem tarefas para remover.\n");

    return;

  }



  listarTarefas(tarefas, *quantidade); //Exibição de listagem de tarefas



  printf("\nDigite o número da tarefa que deseja remover: ");

  scanf("%d", &num_id);



  if (num_id < 1 || num_id > *quantidade) {

    printf("Tarefa inválida!\n");

    return;

  }



  num_id--;

   

  int i;



  for (i = num_id; i < *quantidade - 1; i++) {

    tarefas[i] = tarefas[i + 1];

  }



  (*quantidade)--;



  printf("Tarefa removida com sucesso!\n");

}
