# Proiect_AWJ
. Introducere:
       Aplicația a fost realizată în Eclipse, cu Java. Aplicația preia numele unei imagini și calea către folderul în care se află, pe care o rotește cu 90, 180 sau 270 de grade și scrie noua imagine în fișierul selectat tot prin calea de acces.
2. Descrierea aplicației:
  Pentru implementare am folosit java.awt.image.BufferedImage. 
Structura: Aplicația conține 2 pachete unul de bază (default package) și celălalt Algoritm. Pachetul default conține 3 clase (ReadClass, WriteClass și ImageProc) iar pachetul Algoritm conține interfața Algoritm și alte 4 clase (RotateImage, RotateImage90, RotateImage180, RotateImage270).
ReadClass este o clasă abstractă în care este menționată metoda abstractă readImage de tip BufferedImage cu parametrul path, reprezentând calea fișierului de intrare în care se află imaginea.
WriteClass, clasă abstractă, moștenește clasa ReadClass, implementează metoda readImage, pentru citirea imaginii, (Override) și conține metoda abstractă writeImage de tip void, cu parametrii path și image, imaginea care trebuie rotită și calea către fișierul de ieșire.
ImageProc, moștenește WriteClass, implementează metodele abstracte writeImage (pentru scrierea imaginii) și readImage (Override) și conține main, unde se preiau datele de la tastatură, din linia de comandă: numele imaginii, calea fișierului de intrare unde află imaginea, calea fișierului de ieșire, unde se scrie imaginea rotită, numărul de grade cu care se rotește imaginea. Tot în main se creează obiectele necesare și se calculează timpii de citire, aplicare a algoritmului și scriere a imaginii.
Algoritm este interfața și conține declarată metoda void applyAlgoritm.
RotateImage este o clasă abstractă care implementează Algoritm, conține variabilele private bufferedImage și rotatedImage care au metodele get și set, specifice încapsulării ce are loc. De asemenea conține funcția sum cu număr de argumente variabil (varargs), metoda abstractă void Rotate, iar metoda applyAlgoritm este implementată.
RotateImage90, RotateImage180, RotateImage270 moștenesc clasa RotateImage și implementează metoda Rotate, în care se realizează efectiv rotirea imaginii. Acestea sunt instanțe ale clasei abstracte RotateImage, au funcția abstractă Rotate și astfel apare Polimorfismul.
3. Cerințele aplicației :
1. Imaginea este un fișier BMP.
2. A fost folosit cod low level.
3. Include conceptele POO: 
- Încapsulare: Aplicația este structurată pe clase (una într-un fișier) fiecare cu metodele ei. 
- Moștenire: WriteClass moștenește ReadClass, ImageProc moștenește WriteClass și  RotateImage90, RotateImage180, RotateImage270 moștenesc clasa RotateImage. 
- Polimorfism: RotateImage90, RotateImage180, RotateImage270 cu RotateImage. 
- Abstractizare: au fost folosite numeroase clase abstracte și metode abstracte.
4. Codul sursă este comentat.
5. Operații de lucru cu fișiere: Imaginea este preluată și scrisă în fișier.
6. În main, în ImageProc, sunt preluate datele necesare de la tastatură: numărul de grade, numele imaginii, calea fișierului de intrare și calea fișierului de ieșire.
7. 3 niveluri de moștenire: ReadClass, WriteClass, ImageProc.
8. Include varargs în RotateImage la funcția sum.
9. Clasa abstractă RotateImage cu metoda abstractă Rotate și altele după cum am menționat mai sus.
10. Tratarea excepțiilor cu try-catch în readImage și writeImage.

4. Concluzii
Timpii de decodificare, aplicare a algoritmului și scriere a imaginii sunt diferiți pentru unghiurile alese (destul de apropiați totuși), dar sunt în același timp diferiți pentru fiecare rulare chiar dacă este ales același unghi aplicat aceleiași imagini. Timpul de decodificare este în general în jur de 100 de milisecunde, 120, timpul de aplicare a algoritmului în jur de 50-60 de milisecunde și cel de scriere a imaginii 120-140. Aceste valori au fost depășite substanțial în cadrul unor rulări în care poza avea o rezoluție substantial de mare (de exemplu 4K), dar majoritatea au fost în intervalele precizate.
5. Bibliografie 
https://docs.oracle.com/javase/8/docs/api/?java/io/FileOutputStream.html
https://en.wikipedia.org/wiki/BMP_file_format
https://docs.oracle.com/javase/8/docs/api/?java/io/FileInputStream.html
https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/
https://www.wavemetrics.com/products/igorpro/imageprocessing/imagetransforms/imagerotation
