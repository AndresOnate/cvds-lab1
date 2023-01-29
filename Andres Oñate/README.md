# Laboratorio 1 - Introducción GIT
---
## Andrés Camilo Oñate Quimbayo

### Datos Personales
 - **Carrera**: Ingenieria de sistemas
 - **Plan de estudios**: ISIS-14
 - **Correo Institucional**: `andres.onate@mail.escuelaing.edu.co`
 - **LinkedIn**: [Andres Camilo Oñate Quimbayo](https://co.linkedin.com/in/andr%C3%A9s-camilo-o%C3%B1ate-quimbayo-022332151/en?trk=people-guest_people_search-card)
 
### Intereses

![Image](https://definicion.de/wp-content/uploads/2009/03/ingenieria-de-sistemas.jpg)

  1. Seguridad Informatica 
  2. Desarollo de software
  3. Algoritmos y estructuras de datos
  4. Computación cuantica
  5. Programación competitiva
---
### Programacíon Competitiva

![ICPC](https://icpc.global/community/world-finals-champions/ICPCNews_2019_Storybox.jpg)

Son competencias donde se mide las habilidades de programación y algoritmia de los participantes para resolver un conjunto de problemas lógicos y matemáticos.

_De entre 135 equipos de tres elegidos de un campo de 52,709 concursantes de 3,233 universidades en 110 países en seis continentes en la 43ª Final Mundial del Concurso Internacional Anual de Programación Colegial el 4 de abril de 2019, en Oporto, Portugal._ 

Tomado de [ICPC World Champion Hall of Fame](https://icpc.global/community/world-finals-champions)

---
### Computación Cuantica

La computación cuántica o informática cuántica1​ es un paradigma de computación distinto al de la informática clásica o computación clásica. Se basa en el uso de cubits, una especial combinación de unos y ceros. Los bits de la computación clásica pueden estar en 1 o en 0, pero solo un estado a la vez, en tanto que el cubits puede tener los dos estados simultáneamente. Esto da lugar a nuevas puertas lógicas que hacen posibles nuevos algoritmos.

![Anatomia](https://user-images.githubusercontent.com/63562181/215297737-1b08a6a3-3fe3-4bd9-b586-264683dfaccf.PNG)

Tomado de [¿Para qué sirve en realidad una computadora cuántica?](https://www.dw.com/es/para-qu%C3%A9-sirve-en-realidad-una-computadora-cu%C3%A1ntica/a-50991735)

#### Algoritmos de Factorización

Los números RSA son un conjunto de semiprimos (números con exactamente dos factores primos) grandes que son parte de la competición de factorización RSA. La
competición consistía en encontrar factores primos, pero en 2007 se declaró inactiva. Fue creada por el laboratorio RSA en marzo de 1991 para fomentar la
investigación en la teoría de números computacional y la dificultad de factorizar números enteros grandes.

##### Método de Fermat

El método de factorización de Fermat se basa en la observación de que la búsqueda de factores de un número entero impar (notemos que los números pares son fácilmente reconocibles y por lo tanto se les puede dividir entre dos fácilmente encontrando factores) es equivalente a obtener soluciones enteras para 𝑥,𝑦 de la ecuación: `n = x^2 − y^2`

_**Implementación en python:**_
```
import math as m

def isqrt(n):
    '''Función que calcula la raíz cuadrada y devuelve
       su parte entera.
    '''
    return int(m.sqrt(n))

def fermat(n):
    ''' Función que determina los valores p,q de un número n de la forma
        n = pq
    '''
    x = isqrt(n) + 1 # Se inicializa x en la raiz de n
    count = 0
    y = isqrt((x*x)-n) # Se depeja y
    while (y*y) != ((x*x)-n):
        count += 1
        x = x + count
        y = isqrt((x*x)-n) 
    p = x + y
    q = x - y 
    return p,q
                
def main():             
    n = int(input('Ingrese el número a factorizar:'))
    p,q = fermat(n)
    print("Primer Factor:",int(p))
    print("Segundo Factor:",int(q))
    
main()
