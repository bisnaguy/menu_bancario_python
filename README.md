# menu_bancario_python
Projeto do curso de python da DIO

~~~
menu = """

        [q] - Sair
        [d] - Depositar
        [s] - Sacar
        [e] - Extrato

"""

saldo = 0
quantidade_deposito = 0
quantidade_saque = 0
limite = 500
extrato = ''
LIMITE_SAQUES = 3

while True:
     
     opcao = input(menu)

     if opcao == "d":
          deposito = float(input("Qual valor você quer depositar: "))
          if deposito < 1:
               print("Valor de depósito inválido!")
          else:
               print(f"\n Depósito no valor de R$ {deposito:.2f} realizado com sucesso!")
               saldo = saldo + deposito
               quantidade_deposito = quantidade_deposito + 1
               extrato += f"Depósito: R${deposito:.2f}\n"

     elif opcao == "s":
          saque = float(input("Quanto você deseja sacar: "))
          if saque > limite:
               print("Você ultrapassou o limite de saque no valor de R$ 500,00")
          elif saque < 1:
               print("Valor de saque inválido!")
          elif saque > saldo:
               print("Você não tem saldo disponível para a operação!")
          elif quantidade_saque >= LIMITE_SAQUES:
               print("Você ultrapassou a quantidade de saque diária")
          else:
               print(f"\n Saque no valor de R$ {saque:.2f} realizado com sucesso!")
               saldo = saldo - saque
               quantidade_saque = quantidade_saque + 1
               extrato += f"Saque: R${saque:.2f}\n"

     elif opcao == "e":
          extra = "Extrato"
          print(extra.center(50,"-"))
          print(extrato)
          print(f"O seu saldo atual é de R$ {saldo:.2f} você realizaou {quantidade_deposito} depósitos e {quantidade_saque} saques")
          print(extra.center(50,"-"))

     elif opcao == "q":
          print("\n Você optou por sair, tenha um bom dia!")
          break
     else:
          print("\n Por favor, selecione uma das opções válidas")
            
          
          
               


~~~
