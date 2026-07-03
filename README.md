[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/9AsqjP2W)
# Parcial 2 ComisiÃ³n 1â€“ Objetos 1 â€“ Unahur â€“ 2025 â€“ Primer Cuatrimestre

# ** Mortal Wollokombat**

Este documento describe las especificaciones para el simulador de pelea Mortal Wollokombat, donde todos los peleadores van a enfrentarse.

---

## **Peleador**

Los peleadores son las protagonistas que participan en las batallas del Torneo.

### **Atributos Generales**

Todos los peleadores tienen:

- **`experiencia`**: Un valor numérico que representa su experiencia.
- **`puntos de salud (PS)`**: Comienzan con 100 PS.
- **`ataques`**: Los ataques que conocen. Solo pueden tener tres como máximo

### **Ataques**

Los ataques se caracterizan por el **valor del daño** que generan.

### **Comportamiento General**

- Un peleador puede atacar si tiene **más de 1 punto de salud**.
- Los peleadores ya poseen una colección de ataques. 

---

## **Tipos de Peleadores**

Los peleadores **siempre** pertenecen a un elemento. Por ahora conocemos cuatro elementos, cada uno con comportamientos únicos, pero podrían sumarse nuevos en el futuro.

### **1. Peleador tipo Fuego**

- **Daño que efectúa**: La **suma** de los daños de todos sus ataques.
- **Atributo especial**: `Velocidad del fuego`. Mientras más rápido sea este, menos daño hará. Se calcula que hace un tercio del daño siempre que la velocidad sea mayor a 60.
---

### **2. Peleador tipo Aire**

- **Atributo especial**: `viento cortante`.
- **Puede atacar**: Si cumple la condición general (PS > 1) y además su `viento cortante` es **mayor a 20**.
- **Daño que efectúa**: El valor de su `viento cortante` + el daño de su **mejor ataque** (aquel que genera mayor daño).

---

### **3. Peleador tipo Rayo**

- Todos los peleadores Eléctricos dependen de los combos activos. Se consideran `cargados` cuando el valor del combo actual sea **mayor a 80**.
- **Puede atacar**: Si cumple la condición general (PS > 10) y además está `cargado`.
- **Daño que efectúa**:
  - Si está `cargado`: Aplica el daño del **primer ataque** de su lista.
  - Si no está `cargado`: No aplica ningún daño (0) y debe añadir diez (10) puntos de carga.

---

### **4. Peleador tipo Legendario**

Los peleadores Legendarios son un tipo especial de peleador de **Aire**, pero poseen una `Marca` que potencia su ataque.

- **Daño que efectúa**: El daño definido para los Aire, más un aumento proporcionado por su `Marca`.

#### **Tipos de Marcas**

- ** Marca Roja**:
  - Si `viento cortante` > 20: Aumenta el daño en **10**.
  - De lo contrario: Aumenta el daño en **5**.
- ** Marca Azul**: Aumenta el daño en **8** siempre.
- ** Marca Verde**: No aumenta el daño a efectuar.

---

## ** Requerimientos (Wollomon)**

- Saber si un peleador puede atacar o no.
- Obtener el daño que efectúa un peleador al atacar.
- Hacer que un peleador pueda decir su primer ataque.
- Añadir un nuevo ataque para el peleador.

### **Lógica de Test**

**Objetivo:** Validar que la función "Daño que efectúa" de los peleadores de sea el daño correcto.

> ** Dado:**
>
> - Participante 1: **`Liu Kang`** de tipo fuego con 15 de experiencia, y dos ataques. 
> - Participante 2: **`Subzero`** de tipo aire con 30 de experiencia, y tres ataques. 
> - Participante 3: **`Tomás`**  de tipo rayo con 10 de experiencia, un ataque y 30 de vida. 
>
> ** Cuando:**
>
> - Se ejecuta la función "Daño que efectúa".
>
> ** Entonces (Resultado):**
>
