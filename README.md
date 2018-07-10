Sebastian Cojocariu 311CB UPB ACS

				            Paranthesis Problem Data Structure

Vom descrie modul de implementare al functiilor folosite:
1)TLista AlocaCelula(TInfo *info):Aloca o TLista cu info dat ca parametru(pointerul catre info,defapt).
Daca nu se poate aloca returneaza NULL.

2&3)push_stiva(TStiva *stiva , TLista celula) ,push_coada(TCoada *coada , TLista celula):
   Ambele primesc ca unul din parametri o TLista pe care trebuie sa o adauge in stiva/coada.

4&5)PUSH_STIVA(TStiva **a,FILE *in),PUSH_COADA(TCoada **a,FILE *in):
   Ambele apeleaza functiile omoloage.Citesc din fisierul in dat ca parametru id_stiva/coada si tip_paranteza
pe care le adauga intr-un *TInfo,cel din urma find adaugat intr-o celula si in cele din urma in stiva/coada dorita
(in functie si de id_stiva/coada citit in main)

6&7)pop_stiva(TStiva *a),pop_coada(TCoada *coada):
   Ambele functii ajuta la extragerea unui element din stiva sau coada,dupa caz(varful pt stiva,inceputul pt coada)

8&9)transfer_celula_2_cozi(TCoada *coada_primitoare,TCoada*coada_donatoare)
    transfer_celula_2_stive(TStiva *stiva_primitoare,TStiva *stiva_donatoare)
   
   Ambele functii sunt folosite pentru a transfera o celula dintr-o stiva intr-o alta stiva sau dintr-o coada intr-o alta coada

10&11)afisare_stiva(TStiva *stiva,FILE *out),afisare_coada(TCoada *coada,FILE *out):
   Ambele functii afiseaza o stiva/coada(dupa caz) in fisierul out,respectand formatul din enunt

12)compara(TLista a,TLista b)
   Functie care permite compararea a 2 TListe in vederea sortarii crescatoare a unei stive dupa id_paranteza
=0 daca id-urile sunt egale
<0daca id_paranteza lui b e mai mare decat id_paranteza lui a
>0 altfel

13)sort_stiva(TStiva *a)
   Sorteaza o stiva data ca parametru dupa algoritmul:
Se initializeaza o stiva auxiliara.Se extrage rand pe rand varful stivei "mama"(fie el celula_varf).Daca stiva_aux e nula se pune celula extrasa
in stiva_aux.Altfel se compara cu elementele din stiva_aux,pe care le extragem din aceasta si le bagam inapoi in stiva mama pana cand
celula_varf are id_paranteza >=ce vf stivei_aux.Se repeta procesul pana cand stiva e goala.Complexitate:O(n^2);

14)sort_coada(TCoada *coada)
   Sorteaza o coada dupa id_paranteza.Apeland functia compara se foloseste sortarea pe stiva astfel:
se transfera coada intr-o stiva.Se face sort pe aceasta stiva
stiva sortata se transfera intr-o alta stiva1
stiva1 se transfera in coada (am facut acest lucru pentru a intra elementele
in coada in ordinea corecta

15&16) transfer_din_coada_in_stiva,transfer_din_stiva_in_coada
   Transfera o coada intr-o stiva sau invers.

17)corect_stiva(Algoritm):
   Luam o stiva auxiliara in care inseram parantezele inchise si scoatem parantezele deschise. Astfel putem verifica daca
parantezele formeaza un drum. Luam inca o stiva in care tinem lungimile drumului format pana acum.
Cele doua stive sunt sincronizate (cand facem o operatie pe o stiva facem si pe cealalta). Lungimea drumului este comparata 
la fiecare pas cu lungimea maxima si aceasta este actualizata. Cand ajungem la un caracter care nu poate continua drumul,
golim stiva auxiliara si cea de lungimi ca sa incepem un nou drum. Cu ajutorul stivei putem sa "rupem" un drum in orice 
moment daca ajungem la un caracter nepotrivit, ceea ce nu este posibil folosind o variabila simpla.

18)corect_coada
   Folosim functia corect_stiva,creand pentru fiecare celula din coada o dublura
pe care o inseram intr-o stiva auxiliara.Functia returneaza corect_stiva(stiva auxiliara);

19&20)afisare_vector_de_stive,afisare_vector_de_cozi
Folosesc functiile de afisare stiva/coada pentru a afisa tot vectorul de stive/cozi in fisierul out primit ca parametru

Main:Se citesc n(nr de operatii),s,c.Se initializeaza vectori de stive/cozi.Cu un for se citeste toate operatiile si se apeleaza
functiile corespunzatoare





