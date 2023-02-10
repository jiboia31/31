# 31
310313
#include <stdio.h>
#include <string.h>

#define MAX_NAME_LENGTH 50
#define MAX_BIRTHDATE_LENGTH 10
#define MAX_ADDRESS_LENGTH 50
#define MAX_NEIGHBORHOOD_LENGTH 50
#define MAX_PHONE_LENGTH 15
#define MAX_CPF_LENGTH 11

struct Registry {
  char name[MAX_NAME_LENGTH + 1];
  char birthdate[MAX_BIRTHDATE_LENGTH + 1];
  char address[MAX_ADDRESS_LENGTH + 1];
  char neighborhood[MAX_NEIGHBORHOOD_LENGTH + 1];
  char phone[MAX_PHONE_LENGTH + 1];
  char cpf[MAX_CPF_LENGTH + 1];
};

int main() {
  struct Registry registries[100];
  int registryCount = 0;

  while (1) {
    printf("1. Adicionar Registro\n");
    printf("2. Exibir Registros\n");
    printf("3. Sair\n");
    printf("Escolha uma opção: ");

    int option;
    scanf("%d", &option);

    if (option == 1) {
      printf("Nome: ");
      scanf("%s", registries[registryCount].name);
      printf("Data de Nascimento (DD/MM/YYYY): ");
      scanf("%s", registries[registryCount].birthdate);
      printf("Rua/N: ");
      scanf("%s", registries[registryCount].address);
      printf("Bairro: ");
      scanf("%s", registries[registryCount].neighborhood);
      printf("Telefone (somente números): ");
      scanf("%s", registries[registryCount].phone);
      printf("CPF (somente números): ");
      scanf("%s", registries[registryCount].cpf);
      registryCount++;
    } else if (option == 2) {
      printf("%-*s %-*s %-*s %-*s %-*s %-*s\n", MAX_NAME_LENGTH, "Nome", MAX_BIRTHDATE_LENGTH, "Data de Nascimento", MAX_ADDRESS_LENGTH, "Rua/N", MAX_NEIGHBORHOOD_LENGTH, "Bairro", MAX_PHONE_LENGTH, "Telefone", MAX_CPF_LENGTH, "CPF");
      for (int i = 0; i < registryCount; i++) {
        printf("%-*s %-*s %-*s %-*s %-*s %-*s\n", MAX_NAME_LENGTH, registries[i].name, MAX_BIRTHDATE_LENGTH, registries[i].birthdate, MAX_ADDRESS_LENGTH, registries[i].address, MAX_NEIGHBORHOOD_LENGTH, registries[i].neighborhood, MAX_PHONE_LENGTH, registries[i].phone, MAX_CPF_LENGTH, registries[i].cpf);
}
} else if (option == 3) {
break;
} else {
printf("Opção inválida, tente novamente.\n");
}
}

return 0;
}
