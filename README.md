# programa-examen-unidad-4
estudiantes = int(input("¿Cuantos estudiantes hay en total? "))
materias = int(input("¿Cuantas materias llevan? "))

matriz = []

print("\n--- Captura de calificaciones ---")
for i in range(estudiantes):
    fila = []
    print(f"\nEstudiante {i+1}:")
    for j in range(materias):
        while True:
            cal = float(input(f"  Calificacion de la materia {j+1}: "))
            if 0 <= cal <= 100:
                break
            print("   La calificacion debe de estar entre 0 y 100.")
        fila.append(cal)
    matriz.append(fila)

prom_estudiantes = [sum(fila) / materias for fila in matriz]

prom_materias = []
for j in range(materias):
    suma = sum(matriz[i][j] for i in range(estudiantes))
    prom_materias.append(suma / estudiantes)

max_cal = max(max(fila) for fila in matriz)
min_cal = min(min(fila) for fila in matriz)

print("\n--- RESULTADOS ---")

print("\nPromedio de cada estudiante:")
for i, prom in enumerate(prom_estudiantes):
    print(f"  Estudiante {i+1}: {prom:.2f}")

print("\nPromedio de cada materia:")
for j, prom in enumerate(prom_materias):
    print(f"  Materia {j+1}: {prom:.2f}")

print("\nCalificacion mas alta:", max_cal)
print("Calificacion mas baja:", min_cal)
