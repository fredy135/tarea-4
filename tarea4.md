# Tarea 4
    def calcularSubsidio(numero_hijos, edades_escolares, es_viuda):
        monto_base = 0
        monto_por_hijo = 0

        # Calcular el monto base según la cantidad de hijos
        if numero_hijos <= 2:
            monto_base = 70
        elif numero_hijos <= 5:
            monto_base = 90
        else:
            monto_base = 120

        #Calcular el monto adicional por hijo en edad escolar
        for edad in edades_escolares:
            if 6 <= edad <= 18:
                monto_por_hijo += 10

        # Monto adicional por ser viuda (si/no)
        if es_viuda:
            monto_base += 20

        # Calcula el monto total
        monto_total = monto_base + monto_por_hijo

        return monto_total

    numero_hijos = int(input("Ingrese el número de hijos: "))
    edades_escolares = []
    num_edades = int(input("Ingrese el número de hijos que esten en edad escolar: "))
    for i in range(num_edades):
        edad = int(input(f"Ingrese la edad del hijo {i+1}: "))
        edades_escolares.append(edad)

    es_viuda = input("¿Es viuda la madre de familia? (Sí/No): ").lower() == "sí"

    monto_subsidio = calcularSubsidio(numero_hijos, edades_escolares, es_viuda)
    print(f"El monto mensual que recibirá la familia es: Q.{monto_subsidio}")
