## Fundamentos-de-Python ##
Repositorio Completo de Código Puro sobre los Fundamentos del Lenguaje de Programación Python

# CONDICIONALES # (If - Elif - Else)
'''
1. Escribir un programa que reciba un número y muestre si es múltiplo de 3.
2. Escribir un programa que reciba un número e imprima diferentes salidas, en base a las siguientes condiciones:
-  El número es negativo.
-   El número es igual a 0.
-   El número está entre 0 y 5 o es mayor que 30.
-   El número está entre 5 y 30.
3. Escriba un programa que pida dos números y que conteste cuál es el menor y cuál el mayor o que escriba que son iguales.
4. Escriba un programa que pida un número par y, si no es correcto, muestre un aviso. En caso de ser correcto, le pedirá un número impar. En caso de que no sea correcto, mostrará un aviso.
5. Los alumnos de un curso se han dividido en dos grupos A y B de acuerdo al sexo y el nombre. El grupo A esta formado por las mujeres con un nombre anterior a la M y los hombres con un nombre posterior a la N y el grupo B por el resto. Escribir un programa que pregunte al usuario su nombre y sexo, y muestre por pantalla el grupo que le corresponde.
6. Escriba un programa que pida el año actual y un año cualquiera, y nos muestre por pantalla cuántos años han pasado desde ese año o cuántos años faltan para llegar a ese año.
'''
#1
MultDe3 = int(input("Introduce un número: "))
if MultDe3 % 3 == 0:
    print(f"{MultDe3} es múltiplo de 3")
else:
    print(f"{MultDe3} no es múltiplo de 3")
#2
DifSalidas = int(input("Introduce un número: "))
if DifSalidas < 0:
    print("Es negativo")
elif DifSalidas == 0:
    print("Es igual a 0")
elif DifSalidas > 0 and DifSalidas < 5 or DifSalidas > 30:
    print("Está entre 0 y 5 o es mayor que 30")
else:
    print("Está entre 5 y 30")
#3
Num1 = int(input("Introduce un número: "))
Num2 = int(input("Introduce otro número: "))
if Num1 > Num2:
    print("El primer número introducido es mayor que el segundo")
elif Num1 < Num2:
    print("El segundo número númeor introducido es mayor que el primero")
else:
    print("Los dos números introducidos son iguales")
#4
par = int(input("Introduce un número par: "))
impar = int(input("Introduce un número impar: "))
if par % 2 == 0:
    print("Correcto! El número introducido es par")
    impar
    if impar % 2 != 0:
        print("Correcto! El número introducido es impar")
    else:
        print("Vuelve a intentar introducir un número impar...")       
else:
    print("Vuelve a intentar introducir un número par...")
#5
print("Bienvenido al curso de Python de DELACUESTA! Contesta las preguntas para saber tu grupo de clase")
nombre = str(input("Introduce tu nombre: "))
sexo = str(input("Introduce tu sexo (M o F): "))
if sexo.lower() == "m" and nombre.lower()[0] in "nñrstuvwxyz":
    print(f"{nombre.capitalize()}, perteneces al Grupo A")
elif sexo.lower() == "f" and nombre.lower()[0] in "abcdefghijklm":
    print(f"{nombre}, perteneces al Grupo A")
elif sexo.lower() == "f" and nombre.lower()[0] in "nñrstuvwxyz":
    print(f"{nombre}, perteneces al Grupo B")
else:
    print(f"{nombre}, perteneces al Grupo B")
#6
NumActual = int(input("Introduce el año en el que nos encontramos: "))
NumCualquiera = int(input("Introduce un año cualquiera de la historia pasada o futura: "))    
if NumActual > NumCualquiera:
    pasado = (NumActual - NumCualquiera)
    print(f"Han pasado {pasado} años desde entonces")
elif NumActual < NumCualquiera:
    futuro = (NumCualquiera - NumActual)
    print(f"Faltan {futuro} años para llegar a esa fecha")
else:
    print("Son el mismo año")

# BUCLES #
# FOR #
'''
1. Escribir un programa que nos pida un número mayor que 0 y nos devuelva todos los valores múltiplos de 5 menores que el valor introducido.
Ejemplo:
  Valor introducido = 43
  Salida: 5 10 15 20 25 30 35 40
3. Escribir un programa que reciba una frase y nos cuente el número de vocales que contiene.
4. Escribir un programa que pida un número mayor que 1 y el programa nos diga si ese número es primo o no. Nota: número primo es aquel que solo es divisible entre 1 y entre sí mismo.
5. Escribir un programa que pida una frase y nos diga si ha encontrado algún acento, algún signo de puntuación (punto, coma, punto y coma, guión o paréntesis) y algún espacio mediante un bucle for.
6. Escribir un programa que reciba por teclado una cadena de texto y nos elimine los caracteres duplicadas, solo manteniendo la primera aparición.
Ejemplo:
  Entrada: "Hola, amigos de clase."
  Salida: "Hola, migsdec."
8. Escriba un programa al que le introduzcamos por teclado el tamaño de un tablero de ajedrez y nos devuelva cada posición del tablero en formato fila columna.
1-1 1-2 1-3...
2-1 2-2 2-3...
'''
#1
MultDe5 = int(input("Introduce un número mayor que 0 para comprobar sus múltiplos de 5: "))
if MultDe5 > 0:
    for i in range(MultDe5):
        if i % 5 == 0 and i != 0:
            print(i)
#2 (Método 1)
frase = str(input("introduce una frase para comprobar cuantas vocales que contiene: "))
vocales = 0
for i in frase.lower():
    if i in "aeiouáéíóú":
        vocales += 1
print(f"La frase contiene {vocales} vocales")
#2 (Método 2)
frase2 = str(input("Introduce una frase para conocer el número de vocales que incluye: "))
vocales = []
for i in frase.lower():
    if i in "aeiouáéíóú":
        vocales.append(i)
print(f"La frase contiene {len(vocales)} vocales")
#3
numero = int(input("Introduce un número mayor que 1 para comprobar si es primo: "))
primo = True
if numero >= 1:
    for i in range(2, numero):
        if numero % i == 0:
            primo = False
    if primo:
        print(f"{numero} es primo")
    else:
        print(f"{numero} no es primo")
#4
Frase = str(input("Introduce una frase para contar todos su signos de puntuación: "))
acentos = 0
SignosPuntuación = 0
espacios = 0
for i in Frase:
   if i in "áéíóú":
      acentos += 1
      continue
   elif i in ":;.,¡¿!?":
      SignosPuntuación += 1
      continue
   elif i in " ":
      espacios += 1
print(f"La frase contiene {acentos} acentos, {SignosPuntuación} signos de puntuación y {espacios} espacios")
#5
Frase2 = str(input("Introduce una frase y te la devuelvo sin caracteres duplicados: "))
Frase2Nueva = ""
for i in Frase2:
    if i not in Frase2Nueva:
        Frase2Nueva += i
print(Frase2Nueva)
#6
tablero = int(input("Introduce el tamaño de tu tablero: ")) 
for i in range(1, tablero + 1):
    # i = filas iterables
    secuenciaTablero = 0
    for j in range(1, tablero + 1):
        # j = columnas iterables
        secuenciaTablero = str(i) + "-" + str(j)
    print(secuenciaTablero)
# WHILE #
'''
1. Escriba un programa que le pregunte al usuario si quiere continuar en el programa o no (S o N). En el momento que conteste que no (N), el programa finalizará.
2. Escriba un programa en el que el usuario introduzca números hasta que introduzca un número negativo. En ese momento, mostrar el valor máximo introducido, mínimo y la suma de todos los valores introducidos.
3. Escriba un programa que seleccione un número aleatorio entre 0 y 10, y que el usuario tenga que adivinarlo. Nota: usar random.
4. Escriba un programa que pida al usuario una contraseña y vuelva a solicitarla hasta que las dos contraseñas coincidan. El programa finalizará cuando la adivine.
5. Escriba un programa que simule una hucha. El programa solicitará un objetivo de ahorro. Después, el usuario irá introduciendo cantidades que ha ahorrado. El programa finalizará cuando se haya cumplido el objetivo de ahorro.
6. Escriba un programa que pida al usuario una frase y devuelva el número de caracteres que tiene la primera palabra de la frase introducida.
'''
#1
SoN = str(input("¿Quieres continuar con el programa? Responde con S o N."))
while SoN.upper() != "N":
    if SoN.upper() not in "NS":
        print(f"Porfavor, contesta con N o S.")
        SoN = str(input("¿Quieres continuar con el programa? Responde con S o N."))
    else:
        print(f"De acuerdo!")
        SoN = str(input("¿Quieres continuar con el programa? Responde con S o N."))
else:
    print("El programa ha finalizado, adios!")
#2
numeros = int(input("Introduce un numero: "))
listadoNumeros = [ ]
sumaListado = 0
while numeros >= 0:
    listadoNumeros.append(numeros)
    sumaListado += numeros
    numeros = int(input("Introduce otro número: "))
else:
    listadoNumeros.sort()
    print("Valor no válido, el programa ha finalizado")
    print(f"{listadoNumeros[-1]} es el valor máximo, {listadoNumeros[0]} el mínimo y {sumaListado} la suma")
#3 (Juego 'Guess the Number')
import random
numero = int(input("Adivina el número (0-10): "))
numeroRandom = random.randint(0, 10)
while numero != numeroRandom:
    if numero > numeroRandom:
        print("Es más pequeño")
        numero = int(input("Adivina el número (0-10): "))
    else:
        print("Es más grande")
        numero = int(input("Adivina el número (0-10): "))
else:
    print(f"Has acertado! El número era {numeroRandom}")
#4 ('Sistema de Comprobación de Contraseña')
'Dificultad Extra: Pídele que la contraseña a crear sea segura (parámetros seguros)'

contraseña = str(input("Introduce una contraseña: "))

longitudContraseña = "12345678"
while len(contraseña) < len(longitudContraseña):
    print("La contraseña ha de tener un mínimo de 8 caracteres")
    contraseña = str(input("Introduce una contraseña: "))
else:
    seguridad = "*+-,.?¿¡!_"
    if contraseña not in seguridad:
        print("Haz una contraseña segura, pon al menos un carácter seguro (*+-,.?¿¡!_)")
        contraseña = str(input("Introduce una contraseña: "))
    else:
        print("Tu contraseña cumple los requisitos")
    contraseñaRepeat = str(input("Vuelve a escribir tu contraseña: "))
    while contraseña != contraseñaRepeat:
      print("Las contraseñas no coinciden")
      contraseñaRepeat = str(input("Vuelve a escribir tu contraseña: "))
    else:
      print("Las contraseñas coinciden, tu contraseña ha sido guardada correctamente")
      verContraseña = str(input("Quieres ver tu contraseña (Si / No): "))
      if verContraseña.capitalize() == "Si":
        print(f"Tu contraseña se ha guardado como: {contraseña}")
      else:
        breakpoint
#5 ('Sistema Financiero de Plan de Ahorro Simple')
meta = int(input("Define tu meta de ahorro: "))
ahorrado = 0

while ahorrado < meta:
    intenciónIngreso = str(input("¿Quieres hacer un ingreso a la cuenta ahorro? (Si / No): "))
    if intenciónIngreso.capitalize() == "Si": 
        ingreso = int(input("¿Cuánto quieres ingresar? "))
        ahorrado += ingreso
        print(f"Tu cantidad total ahorrada es de {ahorrado}/{meta}, te quedan {meta - ahorrado} para cumplir tu objetivo")
    else:
        print(f"De acuerdo! Tu ahorro total es de {ahorrado}/{meta}")
        break
else:
    print("Felicidades! Has alcanzado tu meta de ahorro")
    if ahorrado == meta:
        print(f"Tienes ahorrado el importe exacto de tu meta: {ahorrado} / {meta}")
    else:
        print(f"Has superado con creces tu meta de ahorro: {ahorrado} / {meta}, ahorraste {ahorrado - meta} de más")
#6
frase = str(input("Introduce una frase de la menos dos palabras: "))
palabraPrimera= 0

while palabraPrimera <= len(frase):
    for i in frase:
        if i != ",.:;":
           palabraPrimera += 1
        elif i == " ":
            break
            
print(f"La longitud de la primera palabra de tu frase es de {palabraPrimera} caracteres") 

## LISTAS ##
'''
1. Escriba un programa que multiplique por 5 todos los elementos de una lista, creando una nueva lista con el resultado.
2. Escriba un programa que guarde en una nueva lista los valores contenidos en las posiciones impares de la lista inicial.
3. Escriba un programa que pida un número, y a continuación escriba la lista de todos los divisores de ese número (incluido el 1 y él mismo).
4. Escriba un programa que pida el número de palabras que va a contener una lista. Después, el usuario introducirá tantas palabras como ha dicho que iba a tener. Finalmente el programa le pedirá al usuario una palabra y comprobará si está incluida en la lista creada.
5. Escribir un programa que almacene en una lista las asignaturas de un curso (por ejemplo Matemáticas, Lengua, Física, Química, Historia e Inglés),le pregunte al usuario la nota que ha sacado en cada asignatura y elimine de la lista aquellas asignaturas que ha aprobado. Al final, el programa debe mostrar por pantalla las asignaturas que el usuario tiene que repetir.
6. Escribir un programa que le pida al usuario una frase y devuelva por pantalla el número de veces que aparece cada vocal.
'''
#1
lista = [1, 3, 5, 2]
listaX5 = []
for i in range(len(lista)):
    lista[i] = lista[i] * 5
    listaX5.append(lista[i])
print(listaX5)
#2
lista = [1, 4, 8, 9, 2]
listaIndImpar = []
for i in range(len(lista)):
    if i % 2 != 0:
        listaIndImpar.append(lista[i])
print(listaIndImpar)
#3
numero = int(input("Introduce un número: "))
divisores = []
for i in range(1, numero + 1):
    if numero % i == 0:
        divisores.append(i)
print(divisores)
#4
nPalabras = int(input("¿Cuántas palabras ha de tener la lista a crear? "))
lPalabras = []
for i in range(nPalabras):
    palabras = str(input("Introduce tantas palabras como hayas solicitado: "))
    lPalabras.append(palabras)
print(lPalabras)
#5
asignaturas = ["matematicas", "lengua", "fisica", "quimica", "ingles"]
print(f"Éstas son tus asignaturas: {asignaturas}")
nAprobadas = int(input("¿Cuántas asignaturas has aprobado?"))
suspendidas = ["matematicas", "lengua", "fisica", "quimica", "ingles"]
for i in range(nAprobadas):
    aprobadas = str(input("Introduce una materia que hayas aprobado: "))
    suspendidas.remove(aprobadas)
print(f"Has suspendido: {suspendidas}")
#6
vocales = ["a", "e", "i", "o", "u", "á", "é", "í", "ó", "ú"]
frase = str(input("Introduce una frase para contabilizar sus vocales: "))
for i in range(len(frase)):
    if frase[i] in vocales:
        cuentaVocales = frase.count(frase[i])
print(f"La frase tiene {cuentaVocales} vocales")

## TUPLAS ##
'''
1. Escriba un programa que cambie el primer valor de la tupla por un 1.
2. Escriba un programa que cuente cuántas veces aparece un nombre en una tupla.
tupla = ("Ana", "Pedro", "María", "Ana", "Juan", "ana")
3. Escriba un programa que analice la tupla anterior de nombres y devuelva solo los elementos que tengan 5 caracteres o más.
4. Tenemos en una tupla guardadas una serie de recetas. En cada posición de la tupla tenemos una lista en la que guardamos el nombre de la comida, los gramos de aceite, los pellizcos de sal neesarios y los minutos que hay que cocinarlo. Escriba un programa que nos pida la comida que queremos cocinar y nos devuelva el aceite, la sal y el tiempo necesario de cocinado.
5. Tenemos en una tupla a los empleados de nuestra tienda, junto al número de televisiones que vendieron el día anterior y el importe total de sus ventas. Escriba un programa que nos devuelva el nombre del empleado que vendió más televisiones, el nombre del empleado que más facturó el día anterior y el nombre del empleado con el peor ticket medio del día (ticket medio = importe/numero).
'''
#1
tupla = ("v" ,1, 2, "a")
tupla = list(tupla)
tupla[0] = 1
print(tuple(tupla))
#2
nombres = ("Alejandro", "Richi", "Solete", "Paco", "Solete", "Paco", "Paco")
print(nombres)
nombre = str(input("Elige un nombre del listado: "))
nombre = nombre.capitalize()
nombres = list(nombres) 
aparicionesNombre = 0
for i in nombres:
    if i == nombre:
        aparicionesNombre += 1
print(f"El nombre {nombre} aparece {aparicionesNombre} veces")
#3
nombres = ("Alejandro", "Richi", "Solete", "Paco", "Solete", "Paco", "Paco")
# Método si queremos presentarlo en formato tupla
nombresLen5 = [] 
for i in nombres:
    if len(i) >= 5:
        nombresLen5.append(i)
nombresLen5 = tuple(nombresLen5)
print(f"Los nombres con 5 caracteres o más del listado son {nombresLen5}")
# Método si queremos presentarlo en prints sueltos
for i in nombres:
    if len(i) >= 5:
        print(i, " ")
#5
empleados = [("Jorge", 2, 700), ("Pablo", 4, 850), ("Rober", 5, 1800)]
ventas_count = [0, 0, 0]
importes_count = [0, 0, 0]
for i in range(3):
    for j in range(3):
        if empleados[i][1] > empleados[j][1]:
            ventas_count[i] += 1
        if empleados[i][2] > empleados[j][2]:
            importes_count[i] += 1
ventas = [empleados[i][0] for i, v in enumerate(ventas_count) if v == max(ventas_count)]
importes = [empleados[i][0] for i, v in enumerate(importes_count) if v == max(importes_count)]
ticket_medio = [empleados[i][2] / empleados[i][1] for i in range(3)]
peor_ticket_medio = empleados[ticket_medio.index(min(ticket_medio))][0]
ganador_ticket_medio = empleados[ticket_medio.index(max(ticket_medio))][0]
print(f"El empleado con más ventas ha sido {', '.join(ventas)}, el que más ha recaudado ha sido {', '.join(importes)}, el que ha logrado el mayor ticket medio {ganador_ticket_medio}, y el que peor ticket medio ha conseguido ha sido {peor_ticket_medio}")    























    





        



 








    




    




        



