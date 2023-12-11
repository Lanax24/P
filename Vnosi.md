# P
def vnos_seznama():
    seznam = input("Vnesite elemente seznama, ločene z vejico: ").split(',')
    return [element.strip() for element in seznam]

def izpis_seznama(seznam):
    print("Seznam:")
    for indeks, vrednost in enumerate(seznam):
        print(f"{indeks}: {vrednost}")

def brisanje_vrednosti(seznam, vrednost):
    try:
        seznam.remove(vrednost)
        print(f"Vrednost {vrednost} uspešno izbrisana iz seznama.")
    except ValueError:
        print(f"Vrednost {vrednost} ni bila najdena v seznamu.")

def dodajanje_na_mesto(seznam, vrednost, indeks):
    seznam.insert(indeks, vrednost)
    print(f"Vrednost {vrednost} dodana na mesto {indeks} v seznamu.")

def sprememba_vrednosti(seznam, vrednost, indeks):
    try:
        seznam[indeks] = vrednost
        print(f"Vrednost na mestu {indeks} uspešno spremenjena na {vrednost}.")
    except IndexError:
        print(f"Napaka: Indeks {indeks} ni veljaven za seznam dolžine {len(seznam)}.")





Vnos seznama 2 Izpis seznama - vseh vrednosti v seznamu skupaj z njihovimi indeksi. 3 Brisanje izbrane vrednosti iz seznama. 4 Dodajanje vrednosti na poljubno mesto v seznamu. 5 Spremembo vrednosti na poljubnem mestu v seznamu. Vse zgornje funkcije združite v en program, tako da bo omogocal izvedbo katerekoli izmed zgoraj naštetih možnosti ˇ (vnos seznama, dodajanje, dodajanje na izbran mesto, izpis, izbris, spremembo).

import math

def vsota(seznam):
    return sum(seznam)

def povprecje(seznam):
    if not seznam:
        return 0
    return sum(seznam) / len(seznam)

def standardni_odklon(seznam):
    if len(seznam) < 2:
        return 0
    povp = povprecje(seznam)
    vsota_kvadratov = sum((x - povp) ** 2 for x in seznam)
    return math.sqrt(vsota_kvadratov / (len(seznam) - 1))

def glavni_program():
    seznam = []
