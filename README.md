  import statistics

def menu():
    print("\n===== CALCULADORA ESTATÍSTICA =====")
    print("1 - Adicionar número")
    print("2 - Mostrar relatório")
    print("3 - Listar números")
    print("4 - Sair")
    return input("Escolha uma opção: ")

def relatorio(numeros):
    if not numeros: 
        print("Nenhum número adicionado.")
        return

    media = statistics.mean(numeros)
    maior = max(numeros)
    menor = min(numeros)
    soma = sum(numeros)
    
    print("\n===== RELATÓRIO =====")
    print(f"Quantidade de números: {len(numeros)}")
    print(f"Média: {media:.2f}")
    print(f"Maior número: {maior}")
    print(f"Menor número: {menor}")
    print(f"Soma total: {soma}")

def listar_numeros(numeros):
    if not numeros:
        print("Nenhum número adicionado.")
    else:
        print("Números adicionados:", numeros)

def calculadora():
    numeros = []
    while True:
        opcao = menu()
        if opcao == "1":
            try:
                num = float(input("Digite um número: "))
                numeros.append(num)
                print(f"Número {num} adicionado.")
            except ValueError:
                print("Digite apenas números.")
        elif opcao == "2":
            relatorio(numeros)
        elif opcao == "3":
            listar_numeros(numeros)
        elif opcao == "4":
            print("Saindo da calculadora.")
            break
        else:
            print("Escolha uma opção.")

if __name__ == "__main__":
    calculadora()
