
datos = {"Alumnos": []}
opcion = 0
while opcion != 5:
    print("--- MENU ---")
    print("1. Ver alumnos")
    print("2. Agregar alumno")
    print("3. Modificar alumno")
    print("4. Expulsar alumno")
    print("5. Salir")
    
    opcion = int(input("Elija un numero: "))

    if opcion == 1:
        lista = datos["Alumnos"]
        i = 0
        while i < len(lista):
            alumno = lista[i]
            print("Indice:", i)
            print("Nombre:", alumno["Nombre"], alumno["Apellido"])
            print("DNI:", alumno["DNI"])
            print("Notas:", alumno["Notas"])
            print("----------------")
            i = i + 1

    if opcion == 2:
        nuevo_alumno = {
            "Nombre": input("Nombre: "),
            "Apellido": input("Apellido: "),
            "DNI": input("DNI: "),
            "Fecha de nacimiento": input("Fecha nacimiento: "),
            "Tutor": input("Tutor: "),
            "Notas": [],
            "Faltas": 0,
            "amonestaciones": 0
        }
        datos["Alumnos"].append(nuevo_alumno)
        print("Alumno guardado.")

    if opcion == 3:
        indice = int(input("Ingrese el numero de indice del alumno: "))
        alumno = datos["Alumnos"][indice]
        
        print("1. Cambiar Nombre")
        print("2. Agregar Nota")
        sub_opcion = int(input("Que desea hacer?: "))
        
        if sub_opcion == 1:
            alumno["Nombre"] = input("Nuevo nombre: ")
        if sub_opcion == 2:
            nueva_nota = int(input("Nota nueva: "))
            alumno["Notas"].append(nueva_nota)

    if opcion == 4:
        indice = int(input("Ingrese el numero de indice a eliminar: "))
        datos["Alumnos"].pop(indice)
        print("Alumno eliminado.")

print("Programa finalizado.")
