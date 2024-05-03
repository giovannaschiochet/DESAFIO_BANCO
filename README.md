# DESAFIO_BANCO
Desafio de criação de um sitema bancario

menu= """

[1] Depositar
[2] Sacar
[3] Extrato
[4] Sair

"""

saldo= 0
limite= 500
extrato= ""
numero_saque= 0
LIMITE_SAQUE= 3

while True:
    
    opcao = input(menu)

    if opcao == "1":
        valor= float(input("Digite o valor de depósito: "))

        if valor > 0:
            saldo += valor
            extrato+= f"Depósito: R$ {valor: .2f}\n"
        
        else:
            print("Valor informado inválido.")

    elif opcao == "2":
        valor= float(input("Digite o valor do saque: "))
        excedeu_saques = numero_saque>= LIMITE_SAQUE
        
        if valor > saldo:
            print("Saldo insuficiente.")
        elif valor > limite:
            print("Limite insuficiente.")
        elif excedeu_saques:
            print("Excedeu o limite de saques.")
        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor: .2f}\n"
            numero_saque += 1
        else:
            print("Operação falhou!")

    elif opcao == "3":
        print("_______EXTRATO______")
        print("Sem movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo: .2f}")
        print("_____________________")
    elif opcao== "4":
        break

    else:
        print("Opção invalida")
