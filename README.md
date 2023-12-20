def decomposition(X):
    A = int(X / 100)
    B = int((X - 100 * A) / 10)
    C = int(X - (A * 100 + B * 10))
    return A, B, C

def decroissant(A, B, C):
    if A < B:
        A, B = B, A
    if B < C:
        B, C = C, B
    if A < B:
        A, B = B, A
    return A, B, C

def calcule(A, B, C):
    return A * 100 + B * 10 + C - (C * 100 + B * 10 + A)

def Utilisateur():
    X = int(input("Veuillez entrer un nombre à 3 chiffres (ne pas prendre un nombre avec 3 chiffres identiques ou avec un zéro) : "))

    A, B, C = decomposition(X)
    print("Nombre A :", A)
    print("Nombre B :", B)
    print("Nombre C :", C)

    A, B, C = decroissant(A, B, C)
    print("Nombre décroissant :", A, B, C)

    while X != 495:
        X = calcule(A, B, C)
        A, B, C = decomposition(X)
        A, B, C = decroissant(A, B, C)
        print("Nombre T :", X)

if __name__ == "__main__":
    Utilisateur()
