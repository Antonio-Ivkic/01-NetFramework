Hello World
===========

Jednostavni primjer za pregled u IL Disassembleru, da se vidi �to je sve u modulu.


ConfigurationFile
=================

Ilustrira kako se pomo�u konfiguracijske datoteke App.config (koju prevoditelj 
automatski preimenuje u ConfigurationFile.exe.config i preslika u izvedbeno 
kazalo) mo�e odrediti koja �e se verzija .NET okru�enja koristiti tijekom 
izvo�enja. 
Ako .config datoteke nema, pokrenut �e se .NET okru�enje za koje je aplikacija
generirana; ako nema te verzije, tra�i se najvi�a verzija, ve�a od ciljane.

NAPOMENA: .NET 3.0 i .NET 3.5 aplikacije se pokre�e s CLR 2.0.50727.


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

Projek VersionsExe koristi VersionsDLL, koji je "potpisan" sigurnosnim klju�em.
Promijenimo li verziju DLL-a, a Exe ne prevedemo ponovno za tu novu verziju,
VersionsExe �e se sru�iti (baciti iznimku).


Izbjegavanje koda
=================

Budu�i da prilikom izvo�enja programa JIT prevoditelj k�d prevodi u strojni jezik 
metodu po metodu, mogu�e je sprije�iti izvo�enje ako se program izvodi pod
neodgovaraju�om verzijom .NET okru�enja.
MetodaKojuPozivamo() provjerava je li verzija CLR-a ve�a od 3.5 i samo u tom
slu�aju poziva metodu MetodaKoju�elimoIzbje�i(). (verziju CLR-a mo�emo 
kontrolirati pomo�u konfiguracijske datoteke).