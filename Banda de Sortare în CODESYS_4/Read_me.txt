**Platformă:** CODESYS V3.5 SP22  
**Limbaj de programare:** LD (Ladder Diagram / Diagramă cu contacte)  

---

## 1. Descrierea Proiectului
Acest proiect implementează logica de control pentru o linie industrială de sortare a pieselor în funcție de material (Metal, Plastic și piese Nesortate). Sistemul utilizează o bandă transportoare acționată electric, senzori de detectare/proximitate și două pistoane pneumatice pentru direcționarea pieselor în containerele corespunzătoare.

## 2. Logica de Funcționare
1. **Pornire/Oprire:** Sistemul este activat prin menținerea stării (automenținere) la apăsarea butonului `xButonStart` și oprit prin `xButonStop`.
2. **Control Bandă:** Motorul benzii (`xMotorBanda`) rulează doar dacă sistemul este pornit și nu există avarii.
3. **Sortare Metal:** Când piesa ajunge în dreptul senzorului 1 (`xSenzorPiston1`) și senzorul de material indică metal (`xSenzorTipPiesa` = TRUE), se activează un timer de tip TOF care menține pistonul 1 (`xPiston1`) extins timp de 1 secundă pentru a evacua piesa.
4. **Sortare Plastic:** Când piesa ajunge în dreptul senzorului 2 (`xSenzorPiston2`) și senzorul de material indică plastic (`xSenzorTipPiesa` = FALSE), pistonul 2 (`xPiston2`) se extinde pentru 1 secundă.
5. **Piese Nesortate:** Piesele care nu corespund criteriilor trec de pistoane și sunt înregistrate la capătul benzii de către `xSenzorEvacuare`.
