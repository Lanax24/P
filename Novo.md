Ta funkcija najprej preveri, ali je daljši niz vsaj tako dolg kot krajši niz. Nato z zanko preveri vsak možen podniz daljšega niza in primerja s krajšim nizom. Če najde ujemanje, dodajo indeks v seznam. Na koncu vrne seznam indeksov, kjer se začne krajši niz v daljšem nizu. V primeru, da krajši niz ni vsebovan v daljšem, vrne prazen seznam.

def najdi_indekse(d, k):
    if len(d) < len(k):
        raise ValueError("Daljši niz mora biti vsaj tako dolg kot krajši niz.")
    
    i = []
    
    for x in range(len(d) - len(k) + 1):
        if d[x:x+len(k)] == k:
            i.append(x)
    
    return i

daljsi_niz = "Tralala"
krajsi_niz = "la"
rezultat = najdi_indekse(daljsi_niz, krajsi_niz)
print(rezultat)

še en testni tprimer
Python
def je_v(niz1, niz2):
  if len(niz2) > len(niz1):
    return False
  return any(niz1[i:i + len(niz2)] == niz2 for i in range(len(niz1) - len(niz2) + 1))
Use code with caution. Learn more
Ta funkcija uporablja funkcijo any(), ki vrne True, če je vsaj eden od elementov v seznamu True. Funkcija najprej preveri, če je drugi niz daljši od prvega. Če je, funkcija vrne False.

Če je drugi niz krajši ali enako dolg kot prvi niz, funkcija začne iterirati po prvem nizu. Za vsako mesto v prvem nizu funkcija primerja naslednjih len(niz2) številk v prvem nizu z drugim nizom. Če so številke enake, funkcija vrne True.

Na primer, naslednji kodo:

Python
niz1 = [1, 2, 3, 4, 5]
niz2 = [2, 3, 4]

print(je_v(niz1, niz2))
Use code with caution. Learn more
vrne:

True
Ker se niz niz2 nahaja v nizu niz1, funkcija vrne True.

Tukaj je še en primer:

Python
niz1 = [1, 2, 3, 4, 5]
niz2 = [1, 2, 3]

print(je_v(niz1, niz2))
Use code with caution. Learn more
vrne:

False
Ker se niz niz2 ne nahaja v nizu niz1, funkcija vrne False.



