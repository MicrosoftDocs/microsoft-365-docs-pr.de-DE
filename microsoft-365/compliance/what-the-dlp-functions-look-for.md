---
title: Wonach die DLP-Funktionen suchen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Die Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.
ms.openlocfilehash: 86ce1c9d546f776e239fdaca76219129c24a73e8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601202"
---
# <a name="what-the-dlp-functions-look-for"></a>Wonach die DLP-Funktionen suchen

Die Verhinderung von Datenverlust (DLP) umfasst vertrauliche Informationstypen wie Kreditkartennummer und EU-Debitkarten-Nummer, die Sie in ihren DLP-Richtlinien verwenden können. Diese Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind, um zu bestätigen, dass eine Zahl eine Kreditkartennummer ist.
  
In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren. Weitere Informationen finden Sie unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="func_us_date"></a>Func_us_date

Diese Funktion sucht nach einem Datum in dem Format, das in den USA häufig verwendet wird. Dies umfasst die Formate "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet. 
  
Beispiele:
  
- 2. Dezember 2016
    
- 2. Dezember 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dez-2-2016
    
- 12-2-16
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
## <a name="func_eu_date"></a>Func_eu_date

Diese Funktion sucht nach einem Datum in dem Format, das in der EU häufig verwendet wird. (und die meisten Orte außerhalb der USA). Dies umfasst die Formate "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.
  
Beispiele:
  
- 2. Dez. 2016
    
- 02 Dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Niederländisch
    
  - Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember
    
  - Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez
    
- Französisch
    
  - janvier, février, Mars, Avril, Mai, Juni juillet, août, September, Oktober, Novembre, Novembre
    
  - janv. févr. Mars Avril Mai Juni juil. août Sept. OAT. Nov. déc.
    
- Deutsch
    
  - Januar, Februar, März, April, Mai, Juni Juli, August, September, Oktober, November, Dezember
    
  - Jan./Jän. Februar März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Italienisch
    
  - gennaio, febbraio, Marzo, Aprile, Maggio, Juni, Juli, Agosto, Settembre, ottobre, Novembre, Dezember
    
  - Genn. febbr. Mrz. Apr. Magg. Juni Juli AG. Sett. Ott. Nov. DIC.
    
- Portugiesisch
    
  - Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro
    
  - Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez
    
- Spanisch
    
  - enero, Febrero, Marzo, Abril, Mayo, junio, Julio, Agosto, Septiembre, Octubre, Noviembre, Diciembre
    
  - enero Feb. Marzo-ABR. Mayo Jun. Juli. Agosto Sept./Set. OAT. Nov. DIC.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der `Func_eu_date` obigen Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird. Das Format für diese Funktion ist identisch `Func_eu_date`mit der Unterschiede nur in der verwendeten Sprache.
  
Beispiele:
  
- 2 Dez 2016
    
- 02 Dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Portugiesisch
    
  - Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro
    
  - Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der `Func_eu_date` obigen Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird. Das Format für diese Funktion ist identisch `Func_eu_date`mit der Unterschiede nur in der verwendeten Sprache.
  
Beispiele:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Niederländisch
    
  - Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember
    
  - Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez
    
## <a name="func_expiration_date"></a>Func_expiration_date

Diese Funktion sucht nach einem Datum in den Formaten, die häufig von Kredit-und Debitkarten verwendet werden, wodurch Tage zugunsten von Monaten ausgeschlossen werden. Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen. Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.
  
Beispiele:
  
- MM/jj--zum Beispiel 01/11 oder 1/11
    
- MM/jjjj--zum Beispiel 01/2011 oder 1/2011
    
- MM-jj--zum Beispiel 01-22 oder 1-11
    
- MM-yyyy--zum Beispiel 01-2000 oder 1-2000
    
Die folgenden Formate unterstützen JJ oder yyyy:
  
- Monat-yyyy--zum Beispiel. Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10
    
- Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"
    
- Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"
    
- Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez
    
## <a name="func_us_address"></a>Func_us_address

Diese Funktion sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl, genauso wie Sie in Postadressen verwendet werden. Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind. Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.
  
Beispiele:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

