/*Agenda de contatos- Nome/endereço/email/telefone;
Adicionar/buscar/remover/exibir contatos;

Passo a passo:

Armazenar dados dentro da structe
Usar constante para a agenda armazenar apenas 100 contatos;
Usar funções para adicionar/buscar/remover/exibir contatos;
Exibir o menu;
Fazer a chamada das funções na int main() e exibir os resultados esperados;
*/

#include <iostream>
#include <string>
using namespace std;

const int Contato_Maximo = 100; // constante para definir o numero maximo de contatos

struct Contato{       
    string Nome;
    string Cidade;
    string Email;
    string Telefone;
};

void ExibirMenu(){
    cout << "\n --Agenda de Contatos--\n";
    cout << "1- Adicionar contato" << endl;
    cout << "2- Remover contato" << endl;
    cout << "3- Buscar contato" << endl;
    cout << "4- Exibir contatos" << endl;
    cout << "5- Sair." << endl;
    cout << "Escolha uma opcao:" << endl;
}

void AdicionarContato(Contato agenda[], int& totalContatos) {  // int& --> utilizado para passar a variável como referência
    if(totalContatos >= Contato_Maximo) {
        cout << "A agenda está cheia!" << endl;
        return;  // usado para encerrar a execução desta parte da função
    }

    Contato NovoContato;
    cout << "Digite o nome: " << endl;
    cin.ignore(); // Limpar o buffer de entrada após ler a opção
    getline(cin, NovoContato.Nome);
    cout << "Digite a cidade: " << endl;
    getline(cin, NovoContato.Cidade);
    cout << "Digite o email: " << endl;
    getline(cin, NovoContato.Email);
    cout << "Digite o telefone: " << endl;
    getline(cin, NovoContato.Telefone);

    agenda[totalContatos] = NovoContato;
    totalContatos++;
    cout << "Contato adicionado!" << endl;
} // cin.ignore() serve para limpar o buffer e armazena-los para depois resgatá-los e escrever com o getline(cin)

void BuscarContato(Contato agenda[], int totalContatos) {
    if(totalContatos == 0) {
        cout << "A agenda está vazia!" << endl;
        return; // Retorna se a agenda estiver vazia
    }

    string Buscar_Nome;
    cout << "Digite o nome a ser buscado: " << endl;
    cin.ignore(); // Limpar o buffer antes de usar getline
    getline(cin, Buscar_Nome);

    for(int i = 0; i < totalContatos; i++) {
        if (agenda[i].Nome == Buscar_Nome) {
            cout << "Encontramos o contato: " << endl;
            cout << "Nome: " << agenda[i].Nome << endl;
            cout << "Cidade: " << agenda[i].Cidade << endl;
            cout << "Email: " << agenda[i].Email << endl;
            cout << "Telefone: " << agenda[i].Telefone << endl;
            return; // Retorna assim que encontrar o contato
        }
    }

    cout << "Contato nao encontrado!" << endl;
}

void RemoverContato(Contato agenda[], int& totalContatos) {
    if (totalContatos == 0) {
        cout << "A agenda está vazia!" << endl;
        return; // Retorna se a agenda estiver vazia
    }

    string Remover_Nome;
    cout << "Digite o nome do contato a ser removido: " << endl;
    cin.ignore(); // Limpar o buffer antes de usar getline
    getline(cin, Remover_Nome);
    
    /* O for foi utilizado para preencher o espaço vazio do vetor deixado após remover um contato
    o if irá percorrer o vetor para achar qual é o nome a ser removido
    depois, o for percorre o vetor fazendo todos os valores "pularem" para a esquerda a fim de preencher o vetor vazio*/
     
    for (int i = 0; i < totalContatos; i++) {    
        if (agenda[i].Nome == Remover_Nome) {
            for (int j = i; j < totalContatos - 1; j++) {
                agenda[j] = agenda[j + 1];  // Desloca os contatos para a esquerda
            }
            totalContatos--;
            cout << "Contato removido com sucesso!" << endl;
            return; // Retorna assim que o contato for removido
        }
    }

    cout << "Contato nao encontrado!" << endl;
    /* Esse for é utilizado para percorrer o vetor e procurar o índice [i] que no caso seria o nome a ser removido
    Para cada contato, verifica se o nome atual é igual ao que queremos que seja removido */
}

void ExibirContatos(Contato agenda[], int totalContatos) {
    if(totalContatos == 0) {
        cout << "A agenda está vazia!" << endl;
        return; // Retorna se a agenda estiver vazia
    }

    cout << "-- Lista de Contatos --" << endl;  
    for(int i = 0; i < totalContatos; i++) {
        cout << "Nome: " << agenda[i].Nome << endl;
        cout << "Cidade: " << agenda[i].Cidade << endl;
        cout << "Email: " << agenda[i].Email << endl;
        cout << "Telefone: " << agenda[i].Telefone << endl;
    }
    // Exibe todos os contatos dentro do vetor agenda com seus respectivos dados
}
  
int main() {
    Contato agenda[Contato_Maximo];
    int totalContatos = 0;
    int opcao;
     
    do {
        ExibirMenu();  
        cin >> opcao;  

        switch (opcao) {
        case 1:
            AdicionarContato(agenda, totalContatos);  
            break;
        case 2:
            RemoverContato(agenda, totalContatos);    
            break;
        case 3:
            BuscarContato(agenda, totalContatos);    
            break;
        case 4:
            ExibirContatos(agenda, totalContatos);   
            break;
        case 5:
            cout << "\nSaindo da agenda!" << endl;  
            break;
        default:
            cout << "\n Opcao invalida! Tente novamente.\n";  
    }
} while (opcao != 5);  // Uso do while para fazer o loop continuar até o usuário escolher a opção 5
    
    return 0;
}
