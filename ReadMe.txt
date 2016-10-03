Hello World
===========

Jednostavni primjer za pregled Visual Studio Solutiona, strukture kazala.
Pregled koda u IL Disassembleru, da se vidi �to je sve u modulu.


ClsCompliant1 i ClsCompliant2
=============================
Primjer zna�enja CLS compliant atributa

Sastoji se od dva modula:

1. ClsCompliant1 jest EXE pisan u VB.NET-u koji korisit modul ClsCompliant2

2. ClsCompliant2 jest DLL pisan u C# koji u sebi sadr�i klasu TimeProvider sa 
   stati�kim metodama:
   - Getdatetime(string ime)
   - GetDateTime()
   - GetDatetime()

   Druga i tre�a verzija metoda ne zadovoljavaju CLS, jer se nazivi razlikuju 
   samo po velikim/malim slovima.


VersionsExe i VersionsDLL
=========================
Primjer strogog verzioniranja.

Projekt VersionsExe koristi VersionsDLL, koji je "potpisan" sigurnosnim klju�em.
Promijenimo li verziju DLL-a, a Exe ne prevedemo ponovno za tu novu verziju,
VersionsExe �e se sru�iti (baciti iznimku).
