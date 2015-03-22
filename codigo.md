#include <stdio.h>
#include <stdlib.h>

#define MAXNUMVERTICES 100
#define MAXNUMARESTAS  10000
#define XUXA 0

typedef struct arestas
{
    int vertice;
    int dist;
    int mut;
    int distmultiplicada;
    struct arestas* prox;
}arestas;

void inserir(arestas* vet[], int cd1, int cd2, int dist)
{
    arestas* point;
    arestas* vertice;

    point = vet[cd1];

    if(point != NULL)
    {
        vertice = (arestas*) malloc (sizeof(arestas));
    }

}

int main(int argc, char* argv)
{
    int i, j;
    int nvert, narest;
    int cd1, cd2, dist;
    int aux;

    printf("Numero de vertices, numero de arestas\n");
    scanf("%d", &nvert);
    scanf("%d", &narest);

    arestas *vet[nvert];


    // vetor apontando para null
    // nenhuma aresta inserida
    for(i = 0; i<nvert; i++)
        vet[i] = NULL;


    for(i=0; i<narest; i++)
    {
        scanf("%d", &cd1);
        scanf("%d", &cd2);
        scanf("%d", &dist);
        // no nosso algoritmo, o caminho é sempre visto do vertice
        // menor para o maior
        if(cd1 > cd2)
        {
            aux = cd1;
            cd1 = cd2;
            cd2 = aux;
        }
        inserir(vet, cd1, cd2, dist);
    }



    return XUXA;
}
