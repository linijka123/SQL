# SQL

W bazie danych TRPrzychodnia, zrobić zestawienie wizyt z 22.04.2013, w których brali udział pacjenci urodzeni po roku 1987 a lekarz był kobietą. W zestawieniu powinny się znajdować następujące dane: nazwisko i imię pacjenta, numer ewidencyjny lekarza oraz kwota opłaty za wizytę. Wynik uporządkować według nazwiska pacjenta malejąco.


SELECT 
     P.Nazwisko,
	 P.Imie,
	 L.NrEwid,
	 W.Oplata
from Pacjenci as P INNER JOIN Wizyty as W ON P.IdPacjenta = W.IdPacjenta
                   INNER JOIN Lekarze as L ON L.IdLekarza = W.IdLekarza
Where W.DataWizyty = '2013-04-22' and 
      P.DataUrodzenia > '19871231'  and
	  L.CzyKobieta = 1
order by P.Nazwisko desc



