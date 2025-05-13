# vanessaFinalExam

Este es un programa en Python para administrar el inventario de una tienda. Puedes agregar, consultar, actualizar, eliminar productos y calcular el valor total del inventario.

 Requisitos
Tener instalado Python 3

Cómo usar
Descarga el archivo Pruebavanessagomez.py
descomprimirlo
despues de tener el archivo descomprimido abrir en tu editor de codigo preferido
elegir el archivo del codigo propuesto y inicializar haciendo un debug en la terminal dedicada 
correr programa

ejemplos de salida y entrada de datos serian los siguientes:

    while True:
    # menu inventary
    print("\nmenu inventary")
    print("1. add product inventary shop epic") 
    print("2. consult product inventary shop epic") 
    print("3. update price de product shop epic") 
    print("4. remove product inventary shop epic") 
    print("5. calculate total value calculate") 
    print("6. go out")  

    #option = input("selection option (1-6): ")
    if option == '1':
        name = input("name product add : ")
        if name in inventary: 
            print("product exist")
        else:
            try:
                price = float(input("price product: "))
                stock = int(input("stock product: "))
                if price < 0 or stock < 0:
                    raise ValueError
                inventary[name] = (price, stock)
                print(f"product '{name}' correct")
            except ValueError:
                print(f"mistake")

    #option 2: consult product inventary shop epic
    elif option == '2':
        name = input(" name product consult: ").strip()
        if name in inventary:
            price, stock= inventary[name]
            print(f"product found: ")
            print(f"name: {name}")
            print(f"price: ${inventary[name]['price']}")
            print(f"stock: {inventary[name]['stock']}")
        else:
            print(f"product not found")


    # option 3: update price de product shop epic
    elif option == '3':
        name = input("name product update: ")
        if name in inventary:
            try:
                new_price = float(input("new price: "))
                if new_price < 0:
                    raise ValueError
                inventary[name] = (new_price)
                print("price updated correct")
            except ValueError:
                print("price incorrect")
        else:
            print("product incorrect")

    # option 4: remove product inventary shop epic
    elif option == '4':
        name = input("name product remove: ")
        if name in inventary:
            del inventary[name] 
            print(f"product '{name}'remove correct")
        else:
            print("product incorrect")
    # option 5: calculate total value calculate
    elif option == '5':
        total = sum(map(lambda item: item['price'] * item['price'], inventary.values()))
        print(f"worth total value inventary: ${round(total, 2)}")

    # option 6: go out
    elif option == '6':
        print("go out")
        break
    else:
        print("option incorrect")
