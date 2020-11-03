---
title: Was die Funktionen zur Verhinderung von Datenverlust (DLP) suchen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, worauf die Funktionen zur Verhinderung von Datenverlust (DLP) achten.
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841446"
---
# <a name="what-the-dlp-functions-look-for"></a>Wonach die DLP-Funktionen suchen

Datenverlust Verhinderung (DLP)-Richtlinien können vertrauliche Informationstypen verwenden, um vertrauliche Elemente zu identifizieren. Kreditkartennummer und EU-Debitkarten-Kartennummer sind Beispiele für vertrauliche Informationstypen. Typen vertraulicher Informationen suchen nach bestimmten Mustern. Vertrauliche Informationstypen validieren die Daten, indem Sie sich das Format, die Prüfsummen und die Suche nach relevanten Schlüsselwörtern oder anderen Informationen ansehen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind. Dadurch wird bestätigt, dass es sich bei einer Zahl um eine Kreditkartennummer handelt.
  
In diesem Artikel wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren. Weitere Informationen finden Sie unter [sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) .
  
## <a name="table-of-functions"></a>Funktionstabelle

|Funktionsname  |Function-Aktion  |ist ein Validator|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|erkennt und validiert den eindeutigen Steuerschlüssel für Argentinien|nein|
|Func_aba_routing|ermittelt die ABA-Routingnummer| ja|
|Func_alabama_drivers_license_number|erkennt Alabama-Führerscheinnummer|nein|
|Func_alaska_delaware_oregon_drivers_license_number|erkennt Alaska, Delaware, Oregon-Führerscheinnummer|nein|
|Func_alaska_drivers_license_number|erkennt Alaska-Führerscheinnummer|nein|
|Func_alberta_drivers_license_number|erkennt Alberta-Führerscheinnummer|nein|
|Func_Argentina_Unique_Tax_Key|erkennt Argentiniens eindeutigen Steuerschlüssel|nein|
|Func_arizona_drivers_license_number|erkennt Arizona-Führerscheinnummer|nein|
|Func_arkansas_drivers_license_number|erkennt Arkansas-Führerscheinnummer|nein|
|Func_australian_business_number|erkennt die Geschäftsnummer von Australien|nein|
|Func_Australian_Company_Number|erkennt australische Firmennummer|nein|
|Func_australian_medical_account_number|erkennt australische medizinische Kontonummer|nein|
|Func_australian_tax_file_number|erkennt Australien-Steuerdatei Nummer|ja|
|Func_austria_eu_ssn_or_equivalent|erkennt Österreichs Sozialversicherungsnummer|nein|
|Func_austria_eu_tax_file_number|ermittelt die Nummer der österreichischen Steuerdatei|nein|
|Func_Austria_Value_Added_Tax|erkennt Österreichs Mehrwertsteuer|nein|
|Func_belgium_national_number|ermittelt belgische nationale Nummer|nein|
|Func_belgium_value_added_tax_number|erkennt belgische Mehrwertsteuernummer|nein|
|Func_brazil_cnpj|ermittelt die Nummer der gesetzlichen Entität für Brasilien (CNPJ)|ja|
|Func_brazil_cpf|erkennt Brasilien CPF|ja|
|Func_brazil_rg|erkennt Brasilien RG|nein|
|Func_british_columbia_drivers_license_number|Erkennung der britischen Columbia-Führerscheinnummer|nein|
|Func_bulgaria_eu_national_id_card|erkennt Bulgarien Uniform Civil Number|nein|
|Func_california_drivers_license_number|erkennt California-Führerscheinnummer|nein|
|Func_canadian_sin|erkennt Canada Sin|ja|
|Func_chile_id_card|erkennt Chile-ID-Karte|nein|
|Func_china_resident_id|erkennt China-Resident ID|nein|
|Func_colorado_drivers_license_number|erkennt Colorado-Führerscheinnummer|nein|
|Func_connecticut_drivers_license_number|erkennt Connecticut-Führerscheinnummer|nein|
|Func_credit_card|erkennt Kreditkarte|ja|nein|
|Func_croatia_id_card|erkennt Kroatien-ID-Karte|nein|
|Func_croatia_oib_number|erkennt kroatische OIB-Nummer|nein|
|Func_cyprus_eu_tax_file_number|erkennt Zypern-Steuerdatei Nummer|nein|
|Func_czech_id_card|erkennt Tschechisch-ID-Karte|nein|
|Func_czech_id_card_new_format|erkennt die Tschechische ID-Karte im neuen Format|nein|
|Func_dea_number|erkennt DEA-Nummer|ja|
|Func_denmark_eu_tax_file_number|erkennt dänische persönliche Identifikationsnummer|nein|
|Func_district_of_columbia_drivers_license_number|erkennt District of Columbia-Führerscheinnummer|nein|
|Func_estonia_eu_national_id_card|erkennt Estland Personal Identification Code|nein|
|Func_eu_debit_card|erkennt EU Debit Card|nein|
|Func_finnish_national_id|erkennt finnische nationale ID|nein|
|Func_florida_drivers_license_number|erkennt Florida-Führerscheinnummer|nein|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|erkennt Florida, Maryland, Michigan, Minnesota Führerscheinnummer|nein|
|Func_formatted_itin|erkennt formatierte US-Itin|ja|
|Func_fr_insee|erkennt Frankreich Insee|nein|
|Func_fr_passport|erkennt Frankreich Passport|nein|
|Func_france_eu_tax_file_number|erkennt Frankreich-Steuerdatei Nummer|nein|
|Func_france_value_added_tax_number|erkennt Frankreich Mehrwertsteuernummer|nein|
|Func_french_drivers_license|erkennt französischer Führerschein|nein|
|Func_french_insee|erkennt französisches Insee|nein|
|Func_georgia_drivers_license_number|erkennt Georgien-Führerscheinnummer|nein|
|Func_german_drivers_license|erkennt Deutschland-Führerschein|nein|
|Func_german_passport|erkennt Deutschland Passport|nein|
|Func_german_passport_data|erkennt Deutschland Passport|nein|
|Func_germany_eu_tax_file_number|erkennt Deutschland Steuerdatei Nummer|nein|
|Func_germany_value_added_tax_number|ermittelt Deutschland Mehrwertsteuernummer|nein|
|Func_greece_eu_ssn|erkennt Griechenland Sin (AMKA)|nein|
|Func_hawaii_drivers_license_number|erkennt die Lizenznummer des Hawaii-Führerscheins|nein|
|Func_hong_kong_id_card |erkennt Hong Kong ID Card|nein|
|Func_hungarian_value_added_tax_number|erkennt Ungarn Mehrwertsteuernummer|nein|
|Func_hungary_eu_national_id_card|ermittelt Ungarns persönliche Identifikationsnummer|nein|
|Func_hungary_eu_ssn_or_equivalent|ermittelt Ungarn Sozialversicherungsnummer|nein|
|Func_hungary_eu_tax_file_number|ermittelt die Nummer der Steuerdatei für Ungarn|nein|
|Func_iban|erkennt IBAN|ja|
|Func_idaho_drivers_license_number|erkennt Idaho-Führerscheinnummer|nein|
|Func_illinois_drivers_license_number|erkennt Illinois-Führerscheinnummer|nein|
|Func_india_aadhaar|erkennt India aadhaar|ja|
|Func_indiana_drivers_license_number|erkennt Indiana-Führerscheinnummer|nein|
|Func_iowa_drivers_license_number|erkennt Iowa-Führerscheinnummer|nein|
|Func_ireland_pps|erkennt Irland PPS|nein|
|Func_israeli_national_id_number|erkennt israelische nationale ID-Nummer|nein|
|Func_italy_eu_national_id_card |erkennt Italien-Steuercode|nein|
|Func_italy_value_added_tax_number|erkennt Italien Mehrwertsteuernummer|nein|
|Func_japanese_my_number_corporate|erkennt Japan meine Nummer Corporate|ja|
|Func_japanese_my_number_personal|erkennt Japan meine Nummer persönlich|ja|
|Func_jp_bank_account|erkennt Japan Bank Konto|nein|
|Func_jp_bank_account_branch_code|erkennt Japans Bank Konto Zweig Code|nein|
|Func_jp_drivers_license_number|erkennt japanische Führerscheinnummer|nein|
|Func_jp_passport|erkennt Japan Passport|nein|
|Func_jp_resident_registration_number|erkennt eine in Japan ansässige Registrierungsnummer|nein|
|Func_jp_sin|erkennt Japan Sin|nein|
|Func_jp_sin_pre_1997|erkennt Japan Sin vor 1997|nein|
|Func_kansas_drivers_license_number|erkennt Kansas-Führerscheinnummer|nein|
|Func_kentucky_drivers_license_number|erkennt Kentucky-Führerscheinnummer|nein|
|Func_kentucky_massachusetts_virginia_drivers_license_number|erkennt Kentucky, Massachusetts, Virginia-Führerscheinnummer|nein|
|Func_latvia_eu_national_id_card|erkennt lettischen persönlichen Code|nein|
|Func_lithuania_eu_tax_file_number|erkennt litauischen persönlichen Code|nein|
|Func_louisiana_drivers_license_number|erkennt Louisiana-Führerscheinnummer|nein|
|Func_luxemburg_eu_tax_file_number|erkennt luxemburgische nationale Identifikationsnummer (natürliche Personen)|nein|
|Func_luxemburg_eu_tax_file_number_non_natural|erkennt luxemburgische nationale Identifikationsnummer (nicht natürliche Personen)|nein|
|Func_maine_drivers_license_number|erkennt Maine-Führerscheinnummer|nein|
|Func_manitoba_drivers_license_number|erkennt Manitoba-Führerscheinnummer|nein|
|Func_maryland_drivers_license_number|erkennt die Lizenznummer des Maryland-Führerscheins|nein|
|Func_massachusetts_drivers_license_number|erkennt Massachusetts-Führerscheinnummer|nein|
|Func_mexico_population_registry_code|erkennt den Registrierungscode "Mexico-Auffüllung"|nein|
|Func_michigan_minnesota_drivers_license_number|erkennt Michigan, Minnesota Führerscheinnummer|nein|
|Func_minnesota_drivers_license_number|erkennt Minnesota-Führerscheinnummer|nein|
|Func_mississippi_oklahoma_drivers_license_number|erkennt Mississippi, Oklahoma-Führerscheinnummer|nein|
|Func_missouri_drivers_license_number|erkennt Missouri-Führerscheinnummer|nein|
|Func_montana_drivers_license_number|erkennt Montana-Führerscheinnummer|nein|
|Func_nebraska_drivers_license_number|erkennt Nebraska-Führerscheinnummer|nein|
|Func_netherlands_bsn|erkennt niederländische BSN|nein|
|Func_netherlands_eu_tax_file_number|ermittelt niederländische Steuerdatei Nummer|nein|
|Func_netherlands_value_added_tax_number|ermittelt niederländische Mehrwertsteuernummer|nein|
|Func_nevada_drivers_license_number|erkennt Nevada-Führerscheinnummer|nein|
|Func_new_brunswick_drivers_license_number|erkennt neue Brunswick-Führerscheinnummer|nein|
|Func_new_hampshire_drivers_license_number|erkennt neue Hampshire-Führerscheinnummer|nein|
|Func_new_jersey_drivers_license_number |erkennt die Lizenznummer des New Jersey-Treibers.|nein|
|Func_new_mexico_drivers_license_number |erkennt New Mexico-Führerscheinnummer|nein|
|Func_new_york_drivers_license_number   |erkennt New Yorker Führerscheinnummer|nein|
|Func_new_zealand_bank_account_number   |ermittelt die neuseeländische Bank Kontonummer|nein|
|Func_new_zealand_inland_revenue_number |ermittelt Neuseeland-Inlandsumsatz Nummer|nein|
|Func_new_zealand_ministry_of_health_number|erkennt neuseeländisches Ministerium für Gesundheits Nummer|nein|
|Func_newfoundland_labrador_drivers_license_number|ermittelt die Lizenznummer für Neufundland Labrador-Treiber|nein|
|Func_newzealand_driver_license_number  |erkennt neuseeländische Führerscheinnummer|nein|
|Func_newzealand_social_welfare_number  |erkennt neuseeländische Sozialversicherungsnummer|nein|
|Func_north_carolina_drivers_license_number|erkennt die Lizenznummer des North Carolina-Führerscheins|nein|
|Func_north_dakota_drivers_license_number|erkennt North Dakota-Führerscheinnummer|nein|
|Func_norway_id_number  |ermittelt Norwegen-ID-Nummer|nein|
|Func_nova_scotia_drivers_license_number|erkennt die Lizenznummer des Nova Scotia-Führers|nein|
|Func_ohio_drivers_license_number   |erkennt Ohio-Führerscheinnummer|nein|
|Func_ontario_drivers_license_number    |erkennt Ontario-Führerscheinnummer|nein|
|Func_pennsylvania_drivers_license_number|erkennt Pennsylvania-Führerscheinnummer|nein|
|Func_pesel_identification_number   |erkennt polnische nationale ID (PESEL)|nein|
|Func_poland_eu_tax_file_number |erkennt polnische Steuerdatei Nummer|nein|
|Func_polish_national_id    |erkennt den polnischen Identitätsausweis|nein|
|Func_polish_passport_number    |erkennt polnische Passport-Nummer|nein|
|Func_polish_regon_number   |ermittelt polnische REGON-Nummer|nein|
|Func_portugal_eu_tax_file_number|erkennt portugiesische Steueridentifikationsnummer|nein|
|Func_prince_edward_island_drivers_license_number|erkennt Prince Edward Island-Führerscheinnummer|nein|
|Func_quebec_drivers_license_number |erkennt Quebec-Führerscheinnummer|nein|
|Func_randomized_formatted_ssn  |ermittelt randomisierte formatierte US-SSN|ja|
|Func_randomized_unformatted_ssn|erkennt randomisierte, unformatierte US-SSN|ja|
|Func_rhode_island_drivers_license_number|erkennt Rhode Island-Führerscheinnummer|nein|
|Func_romania_eu_national_id_card   |ermittelt rumänischen persönlichen numerischen Code (CNP)|nein|
|Func_saskatchewan_drivers_license_number|erkennt Saskatchewan-Führerscheinnummer|nein|
|Func_slovakia_eu_national_id_card  |ermittelt die persönliche Nummer der Slowakei.|nein|
|Func_slovenia_eu_national_id_card  |erkennt Slowenien Unique Master Citizen Number|nein|
|Func_slovenia_eu_tax_file_number   |erkennt Slowenien-Steuerdatei Nummer|nein|
|Func_south_africa_identification_number|Erkennung der südafrikanischen Identifikationsnummer|ja|
|Func_south_carolina_drivers_license_number|erkennt die Lizenznummer des South Carolina-Führerscheins|nein|
|Func_south_dakota_drivers_license_number|erkennt South Dakota-Führerscheinnummer|nein|
|Func_south_korea_resident_number   |ermittelt Südkoreas Resident Number|nein|
|Func_spain_eu_DL_and_NI_number_citizen |erkennt Spanien DL und NI-Bürger der Nummer|nein|
|Func_spain_eu_DL_and_NI_number_foreigner|erkennt Spanien DL und NI-Nummer Ausländer|nein|
|Func_spain_eu_driver ' s_license_number  |erkennt Spaniens Führerscheinnummer|nein|
|Func_spain_eu_tax_file_number  |erkennt Spaniens Steuerdatei Nummer|nein|
|Func_spanish_social_security_number|erkennt spanische Sozialversicherungsnummer|nein|
|Func_ssn   |Funktion zum erkennen nicht randomisierter formatierter US-SSN|ja|
|Func_sweden_eu_tax_file_number|erkennt schwedische Steuerdatei Nummer|nein|
|Func_swedish_national_identifier|erkennt schwedische nationale ID|ja|
|Func_swiss_social_security_number_ahv|ermittelt die AHV-Sozialversicherungsnummer|nein|
|Func_taiwanese_national_id |erkennt taiwanesische nationale ID|nein|
|Func_tennessee_drivers_license_number|erkennt Tennessee-Führerscheinnummer|nein|
|Func_texas_drivers_license_number  |erkennt Texas-Führerscheinnummer|nein|
|Func_Thai_Citizen_Id   |erkennt thailändische Bürger-ID|nein|
|Func_Turkish_National_Id|erkennt türkische nationale ID|ja|
|Func_uk_drivers_license|erkennt UK-Führerschein|nein|
|Func_uk_eu_tax_file_number|erkennt die eindeutige Nummer des britischen Steuerzahlers|nein|
|Func_uk_nhs_number |erkennt UK NHS-Nummer|ja|
|Func_uk_nino   |erkennt UK Nino|nein|
|Func_unformatted_canadian_sin|erkennt unformatierte kanadische Sünden|nein|
|Func_unformatted_itin  |erkennt unformatierte US-Itin|ja|
|Func_unformatted_ssn   |erkennt nicht randomisierte, nicht formatierte US-SSN|ja|
|Func_usa_uk_passport   |erkennt USA und UK Passport|ja|
|Func_utah_drivers_license_number|erkennt Utah-Führerscheinnummer|nein|
|Func_vermont_drivers_license_number|erkennt Vermont-Führerscheinnummer|nein|
|Func_virginia_drivers_license_number|erkennt Virginia-Führerscheinnummer|nein|
|Func_washington_drivers_license_number|erkennt Washington-Führerscheinnummer|nein|
|Func_west_virginia_drivers_license_number|erkennt West Virginia-Führerscheinnummer|nein|
|Func_wisconsin_drivers_license_number  |erkennt Wisconsin-Führerscheinnummer|nein|
|Func_wyoming_drivers_license_number    |erkennt Wyoming-Führerscheinnummer|nein|


## <a name="func_us_date"></a>Func_us_date

Func_us_date sucht nach Datumsangaben in gängigen US-Formaten. Die gängigen Formate sind "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet. 
  
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

Fund_eu_dates sucht nach Datumsangaben in der allgemeinen EU Formate (und die meisten Orte außerhalb der USA), wie "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.
  
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
> Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der  `Func_eu_date` obigen Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird. Das Format für diese Funktion ist identisch mit der  `Func_eu_date` Unterschiede nur in der verwendeten Sprache.
  
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
> Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der  `Func_eu_date` obigen Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird. Das Format für diese Funktion ist identisch mit der  `Func_eu_date` Unterschiede nur in der verwendeten Sprache.
  
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
    
  - Jan Feb maart Apr Mei Jun Jul Aug Sep Sept. Okt Nov Dez
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date sucht nach Datumsangaben in Formaten, die häufig von Kredit-und Debitkarten verwendet werden. Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen. Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.
  
Beispiele:
  
- MM/jj--zum Beispiel 01/11 oder 1/11
    
- MM/jjjj--zum Beispiel 01/2011 oder 1/2011
    
- MM-jj--zum Beispiel 01-22 oder 1-11
    
- MM-yyyy--zum Beispiel 01-2000 oder 1-2000
    
Die folgenden Formate unterstützen JJ oder yyyy:
  
- Monat-yyyy--zum Beispiel Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10
    
- Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"
    
- Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"
    
- Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl. Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind. Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.
  
Beispiele:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
