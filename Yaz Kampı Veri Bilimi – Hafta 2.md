# Haftalık Ödev – Yaz Kampı: Veri Bilimi – Hafta 2
Hedef
• Koşullu durumları (if/elif/else) uygulamak
• Döngüler (for, while) ile veri işlemek
• String metotları ve listeler üzerinde alıştırmalar yapmak
• Temel veri işleme becerilerini geliştirmek

# Soru 1 – Sayı Analizi


```python
x = int(input("lütfen sayı giriniz."))
if x>0:
    if x%2==0:
        print("pozitif çift")
    else:
        print("pozitif tek")

elif x<0:
    if x%2==0:
        print("pozitif çift")
    else:
        print("pozitif tek")
else:
    print("sıfır")
```

    lütfen sayı giriniz. -5
    

    pozitif tek
    

# Soru 2 – Harf Frekansı (String)


```python
kelime = input("lütfen bir kelime giriniz.")
harf_sayilari = {}
for harf in kelime:
    if harf in harf_sayilari:
        harf_sayilari[harf] += 1
    else:
        harf_sayilari[harf] = 1
print(harf_sayilari)
```

    lütfen bir kelime giriniz. ala
    

    {'a': 2, 'l': 1}
    

# Soru 3 – Şifre Kontrolü (String Metotları)


```python
sifre = input("Lütfen bir şifre giriniz.")
# Koşulları kontrol et
uzunluk_kontrol = len(sifre) >= 8
buyuk_harf_kontrol = any(harf.isupper() for harf in sifre)
rakam_kontrol = any(harf.isdigit() for harf in sifre)
#Python’da any() fonksiyonu, verilen bir iterable (liste, string, tuple vb.) içindeki elemanlardan en az biri True ise True döner.
if uzunluk_kontrol and buyuk_harf_kontrol and rakam_kontrol:
    print("Şifre geçerli!")
else:
    print("Şifre geçersiz! Lütfen şu koşulları sağlayın:")
    if not uzunluk_kontrol:
        print("- En az 8 karakter olmalı.")
    if not buyuk_harf_kontrol:
        print("- En az 1 büyük harf içermeli.")
    if not rakam_kontrol:
        print("- En az 1 rakam içermeli.")
```

    Lütfen bir şifre giriniz. awda4
    

    Şifre geçersiz! Lütfen şu koşulları sağlayın:
    - En az 8 karakter olmalı.
    - En az 1 büyük harf içermeli.
    

# Soru 4 – Liste İşlemleri


```python
sayilar = [12, 4, 9, 25, 30, 7, 18]
ortalama = sum(sayilar) / len(sayilar)
buyukler = [sayi for sayi in sayilar if sayi > ortalama]
print("Liste:", sayilar)
print("Ortalama:", ortalama)
print("Ortalamadan büyük sayılar:", buyukler)
```

    Liste: [12, 4, 9, 25, 30, 7, 18]
    Ortalama: 15.0
    Ortalamadan büyük sayılar: [25, 30, 18]
    

# Soru 5 – Nested Loop (Desen)


```python
for i in range(1, 6):
    print("*" * i)
```

    *
    **
    ***
    ****
    *****
    

# Soru 6 – While Döngüsü


```python
toplam = 0
adet = 0

while True:
    sayi = int(input("Bir sayı giriniz (0 = çıkış): "))
    
    if sayi == 0:
        break
    
    toplam += sayi
    adet += 1
    
if adet > 0:
    ortalama = toplam / adet
    print("Girilen sayıların toplamı:", toplam)
    print("Girilen sayıların ortalaması:", ortalama)
else:
    print("Hiç sayı girilmedi.")

```

    Bir sayı giriniz (0 = çıkış):  0
    

    Hiç sayı girilmedi.
    

# Soru 7 – Palindrom Kontrolü


```python
kelime = input("Bir kelime giriniz: ")
if kelime == kelime[::-1]:
    print("Palindrom")
else:
    print("Palindrom değil")
```

    Bir kelime giriniz:  asa
    

    Palindrom
    

# Soru 8 – List Comprehension


```python
liste = [x**2 for x in range(1,101) if x%3==0 and x%5==0]
print(liste)
```

    [225, 900, 2025, 3600, 5625, 8100]
    

# Soru 9 – String İşlemleri


```python
cumle = input("Bir cümle giriniz: ")
kelimeler = cumle.split()
yeni_kelimeler = [kelime.capitalize() for kelime in kelimeler]
yeni_cumle = " ".join(yeni_kelimeler)
print(yeni_cumle)
```

    Bir cümle giriniz:  lo lo lo loasa
    

    Lo Lo Lo Loasa
    

# Mini Proje – Film Yorumu Analizi


```python
yorumlar = []
n = int(input("Kaç yorum gireceksiniz? "))

for i in range(n):
    yorum = input(f"{i+1}. yorumu giriniz: ")
    yorumlar.append(yorum)

uzunluklar = [len(y) for y in yorumlar]

iyi_sayisi = sum(1 for y in yorumlar if "iyi" in y.lower())

en_uzun = max(yorumlar, key=len)
en_kisa = min(yorumlar, key=len)

ortalama = sum(uzunluklar) / len(yorumlar)

print("Toplam yorum sayısı:", len(yorumlar))
print('"iyi" geçen yorum sayısı:', iyi_sayisi)
print("En uzun yorum:", en_uzun)
print("En kısa yorum:", en_kisa)
print("Ortalama uzunluk:", round(ortalama, 1), "karakter")
```

    Kaç yorum gireceksiniz?  2
    1. yorumu giriniz:  iyi olmuş
    2. yorumu giriniz:  kotuydu
    

    Toplam yorum sayısı: 2
    "iyi" geçen yorum sayısı: 1
    En uzun yorum: iyi olmuş
    En kısa yorum: kotuydu
    Ortalama uzunluk: 8.0 karakter
    

# Ayşe Atmaca


```python

```
