#Trabalho Estrutura de Dados - Atividade Ciclo3
#Estrutura de Árvore em Python:  

class No:    

    def __init__(self, valor):
        self.valor = valor
        self.esquerda = None 
        self.direita = None 

    def obtervalor(self):
        return self.valor

    def setesquerda(self, esquerda): 
        self.esquerda = esquerda

    def setdireita(self, direita):
        self.direita = direita 

    def obteresquerda(self):
        return self.esquerda

    def obterdireita(self):
        return self.direita

class ArvoreBinariaBusca: 
    def __init__(self): 
        self.raiz = None 

    def obterraiz(self):
        return self.raiz

    def insere(self, valor): #se estiver vazio, cria um valor inicial Raiz
        no = No(valor)
        if self.raiz == None: 
            self.raiz = no
        else: 
            no_atual = self.raiz
            no_pai = None 
            while True: 
                if no_atual != None: 
                    no_pai = no_atual
                    if no.obtervalor() < no_atual.obtervalor(): 
                        no_atual = no_atual.obteresquerda()
                    else: 
                        no_atual = no_atual.obterdireita()
                else: 
                    if no.obtervalor() < no_pai.obtervalor(): 
                        no_pai.setesquerda(no)
                    else: 
                        no_pai.setdireita(no)
                    break   

    def mostraarvore(self, no_atual): #percurso em ordem simetrica
        if no_atual != None: 
            self.mostraarvore(no_atual.obteresquerda())
            print (f'{no_atual.obtervalor()}', end= ' ')
            self.mostraarvore(no_atual.obterdireita())

t = ArvoreBinariaBusca()
t.insere(10)
t.insere(14)
t.insere(7)
t.insere(22)
t.insere(13)
t.insere(8)
t.insere(40)
t.insere(3)
t.insere(5)

t.mostraarvore(t.obterraiz())



