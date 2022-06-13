# Implementando-Pilha-em-C-
Algoritmo de gerenciamento de pilha em memória;
Trabalho feito na faculdade em linguagem C, Compilado no ambiente Dev c++;
Usei duas Struct uma para anexar os dados do item ( nome, id) e outra para armazenar esses dados em pilha;


#include <locale.h>
struct pilha{
    char nomeprog[50];
    char opppa[50];
    char cnomeprog[50];
     int pid; 
  
};
struct pilha pilha[tamanho];
	int op, i, ctp, oop; 	
	

int main(){

	op=1;
	ctp=0;
	oop=0;
	setlocale(LC_ALL,"portuguese");
	void inserir();
	void remover();
	void esvaziar();
	void menu();
	void imprimir();
    
    
	do{	system("cls");
    	imprimir();
		menu();
		
		scanf("%d",&op);
		switch (op){
			case 1: inserir();
			break;
			case 2:remover();
			break;
			case 3: esvaziar();
			break;
		}	
	}	while (op!=0);	
	return(0);
}


	void inserir(){
		if(ctp==tamanho){
			printf("pilha está cheia, impossível empilhar mais elementos  ");
			system ("pause");
		}
		else{ 
         int r;
			printf("digite o nome do programa a ser empilhado  ");
	   	fflush (stdin);
		 gets(pilha[i].nomeprog);
    	 r= rand ()%100+1000;
		 pilha[i].pid=rand()%100+1000;
		 printf(" \n PID- %d   | COMANDO- %s ,  foram empilhados    ",pilha[i].pid,pilha[i].nomeprog);
		 fflush(stdin);
		 i++;
		 ctp=ctp+1;		
		 system ("pause");
		 
	}
}
   void remover(){
   	if (ctp==0){
   		printf(" pilha vazia, impossível desempilhar elementos  ");
   		system("pause");
	   }
	   else{
	  
	  	oop= pilha[i-1].pid;
	  	strcpy(pilha[i-1].cnomeprog,pilha[i-1].nomeprog);
    	strcpy(pilha[i-1].nomeprog ,pilha[i-1].opppa);                                          
	  		pilha[i-1].pid=0;
	 	printf(" PID  -%d  |  COMANDO -%s , foram removidos   ", oop,pilha[i-1].cnomeprog);
	 	i--;
	    ctp=ctp-1;
	  	system ("pause");
   }
}

   
   void menu(){
	printf("\n\nEscolha uma opção:\n\n");
	printf("1 - Inserir um elemento na pilha\n");
	printf("2 - Remover um elemento da pilha\n");
	printf("3 - Esvaziar a pilha\n");
	printf("0 - Encerrar o programa\n");
	printf("\n Opção: ");
}
void esvaziar(){
		if (ctp==0){
		printf("\nApilha esta vazia, impossível desempilhar elementos!   \n");
		system ("pause");
	}
	else{
		
			while(ctp!=0) {
		strcpy(pilha[i-1].nomeprog ,pilha[i-1].opppa);	
		pilha[i-1].pid=0;
		i--;
		ctp--;
	    printf("      \n       esvaziando pilha        ");
	
	      
	     }
	 
		system("pause");
    }
}
	

	void  imprimir(){
	int y;
	 
		printf(  "      \n PID               |         COMANDO");
	 

    for( y=5;y>0;y--){
   printf("     \n          [%d]  ",pilha[y-1].pid);
   printf("           [%s]  ",pilha[y-1].nomeprog);
    if (y==ctp){
   	   printf("     <= topo");
		  }
	}

   }

