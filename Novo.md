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
