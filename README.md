<img width="407" height="348" alt="image" src="https://github.com/user-attachments/assets/79f0bb90-c36e-4420-93bb-6d514aa0f84f" />


# Autonomi1Seguridad

#Reflexión: ¿qué pasa si la contraseña tiene 8+ caracteres y usa mayúsculas, números y símbolos?

Si la contraseña tiene muchos digitos el programa se demora mas en decifrar la contraseña


import itertools
import time
alfabeto = "qwertyuiopñlkjhgfdsazxcvbnmQWERTYUIOPÑLKJHGFDSAZXCVBNM123456789!#$%&/()=?¡:;.,{[}]+*'¿"
contraseña = "aaaaaS"

def generar_combinaciones(longitud):
    return itertools.product(alfabeto, repeat=longitud)

def fuerza_bruta(contraseña_objetivo):
    intentos = 0
    tiempo_inicio = time.time()

    for longitud in range(1, len(contraseña_objetivo) + 1):
        for combinacion in generar_combinaciones(longitud):
            intentos += 1
            intento = ''.join(combinacion)
            if intento == contraseña_objetivo:
                tiempo_fin = time.time()
                print("Contraseña encontrada: ", intento)
                print("Intentos realizados: ", intentos)
                print("Tiempo de ejecución: ", tiempo_fin - tiempo_inicio, "segundos")
                return

if __name__ == "__main__":
    fuerza_bruta(contraseña)

