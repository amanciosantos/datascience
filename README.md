# datascience
import xlrd
x = 1 

def xlread(arq_xls):
    xls = xlrd.open_workbook(arq_xls)   #  abre o arquivo para leitura
    plan = xls.sheets()[0]              # pega a primeira linha do arquivo
  
    for i in xrange(plan.nrows):
        yield plan.row_values(i)   # ler cada valor da linha

while x != 0:
    soma = 0
    x = str(input("qual estado?:"))   #interção para rastrear a produção individual de um estado 
 
    for line in xlread('a.xls'):
        #a=line[0]
        #b=line[8]    #formas diferentes de print
        #print(a,b)
      
        if line[0] == x:
            soma = soma + line[8]  #se o valor encontrado na linha for igual ao oferecido ele armazena e soma os valores da produção do estado solicitado
            
    print(x,'producao = ',soma)  #formatação de saída
    
#com esse código que lê um arquivo .xls pode-se formatar diferentes saidas,não só como todos os valores mas também valores isolados.

































    
