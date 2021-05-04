---
title: So sehen die Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) aus
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
recommendations: false
description: Erfahren Sie, wie die Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) aussehen.
ms.openlocfilehash: 47eda79470fd131939c493ac4f66af6efea01dd6
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086512"
---
# <a name="what-the-dlp-functions-look-for"></a>Wonach die DLP-Funktionen suchen

Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können vertrauliche Informationstypen verwenden, um vertrauliche Elemente zu identifizieren. Kreditkartennummer und EU-Debitkartennummer sind Beispiele für Typen vertraulicher Informationen. Typen vertraulicher Informationen suchen nach bestimmten Mustern. Typen vertraulicher Informationen überprüfen die Daten, indem sie sich das Format, die Prüfsummen und relevante Schlüsselwörter oder andere Informationen anschauen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. Beispielsweise verwendet der Typ vertrauliche Kreditkartennummer eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind. Dadurch wird bestätigt, dass es sich bei einer Zahl um eine Kreditkartennummer handelt.
  
In diesem Artikel wird erläutert, wie diese Funktionen aussehen, um zu verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren. Weitere Informationen finden Sie unter [Entitätsdefinitionen des Typs "Vertrauliche Informationen".](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Funktionsverzeichnis

|Funktionsname  |Funktionsaktion  |ist ein Validator|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|Erkennt und überprüft argentinien eindeutigen Steuerschlüssel|nein|
|Func_aba_routing|Erkennt die ABA-Routingnummer| ja|
|Func_alabama_drivers_license_number|Erkennt die Lizenznummer des Alabama-Treibers|nein|
|Func_alaska_delaware_oregon_drivers_license_number|Erkennt die Lizenznummer des Alaska-, Delaware- und Oregon-Führerscheins|nein|
|Func_alaska_drivers_license_number|Erkennt die Lizenznummer des Alaska-Treibers|nein|
|Func_alberta_drivers_license_number|Erkennt die Lizenznummer des Alberta-Treibers|nein|
|Func_Argentina_Unique_Tax_Key|Erkennt Argentinien Eindeutiger Steuerschlüssel|nein|
|Func_arizona_drivers_license_number|Erkennt die Lizenznummer des Arizona-Treibers|nein|
|Func_arkansas_drivers_license_number|Erkennt die Lizenznummer des Arkansas-Treibers|nein|
|Func_australian_business_number|Erkennt die Australische Geschäftsnummer|nein|
|Func_Australian_Company_Number|Erkennt die Australische Firmennummer|nein|
|Func_australian_medical_account_number|Erkennt australische Kontonummer für medizinisches Konto|nein|
|Func_australian_tax_file_number|Erkennt die Australische Steuerdateinummer|ja|
|Func_austria_eu_ssn_or_equivalent|Erkennt Die Nummer der sozialen Sicherheit in Österreich|nein|
|Func_austria_eu_tax_file_number|Erkennt die Steuerdateinummer für Österreich|nein|
|Func_Austria_Value_Added_Tax|Erkennt Die Mehrwertsteuer für Österreich|nein|
|Func_belgium_national_number|erkennt belgische nationale Nummer|nein|
|Func_belgium_value_added_tax_number|Erkennt die Belgische Umsatzsteuernummer|nein|
|Func_brazil_cnpj|Erkennt die Nummer der juristischen Person in Brasilien (CNPJ)|ja|
|Func_brazil_cpf|erkennt Brasilien CPF|ja|
|Func_brazil_rg|erkennt Brasilien RG|nein|
|Func_british_columbia_drivers_license_number|Erkennt die Lizenznummer des British -Columbia-Treibers|nein|
|Func_bulgaria_eu_national_id_card|Erkennt eine einheitliche zivile Nummer für Bulgarien|nein|
|Func_california_drivers_license_number|Erkennt die Lizenznummer des California-Treibers|nein|
|Func_canadian_sin|Erkennt kanadasündige|ja|
|Func_chile_id_card|Erkennt Chile-ID-Karte|nein|
|Func_china_resident_id|Erkennt chinaansässige ID|nein|
|Func_colorado_drivers_license_number|Erkennt die Führerscheinnummer des Colorado-Treibers|nein|
|Func_connecticut_drivers_license_number|Erkennt die Führerscheinnummer des Treibers von "Connecticut".|nein|
|Func_credit_card|Erkennt Kreditkarte|ja|nein|
|Func_croatia_id_card|Erkennt kroatien-ID-Karte|nein|
|Func_croatia_oib_number|erkennt kroatien-OIB-Nummer|nein|
|Func_cyprus_eu_tax_file_number|Erkennt die Steuerdateinummer für Zypern|nein|
|Func_czech_id_card|Erkennt tschechische ID-Karte|nein|
|Func_czech_id_card_new_format|Erkennt die tschechische ID-Karte im neuen Format|nein|
|Func_dea_number|Erkennt die DEA-Nummer|ja|
|Func_denmark_eu_tax_file_number|Erkennt dänemarks persönliche Identifikationsnummer|nein|
|Func_district_of_columbia_drivers_license_number|Erkennt die Führerscheinnummer des District of Columbia|nein|
|Func_estonia_eu_national_id_card|Erkennt den persönlichen Identifikationscode für Estland|nein|
|Func_eu_debit_card|Erkennt die EU-Debitkarte|nein|
|Func_finnish_national_id|erkennt die nationale finnische ID|nein|
|Func_florida_drivers_license_number|Erkennt die Lizenznummer des Florida-Treibers|nein|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|Erkennt die Lizenznummer des Führerscheins von "Florida", "Maryland", "Detroit", "Minnesota" und "Minnesota".|nein|
|Func_formatted_itin|erkennt formatiertes US ITIN|ja|
|Func_fr_insee|erkennt France INSEE|nein|
|Func_fr_passport|Erkennt Frankreich-Pass|nein|
|Func_france_eu_tax_file_number|Erkennt die Französische Steuerdateinummer|nein|
|Func_france_value_added_tax_number|Erkennt frankreichs Umsatzsteuernummer|nein|
|Func_french_drivers_license|Erkennt den französischen Führerschein|nein|
|Func_french_insee|erkennt französischer INSEE|nein|
|Func_georgia_drivers_license_number|Erkennt die Lizenznummer des Georgia-Treibers|nein|
|Func_german_drivers_license|Erkennt den Deutschen Führerschein|nein|
|Func_german_passport|Erkennt Deutschlandpass|nein|
|Func_german_passport_data|Erkennt Deutschlandpass|nein|
|Func_germany_eu_tax_file_number|Erkennt die Deutsche Steuerdateinummer|nein|
|Func_germany_value_added_tax_number|Erkennt die Deutsche Umsatzsteuernummer|nein|
|Func_greece_eu_ssn|Erkennt die Griechenlandsünde (AMKA)|nein|
|Func_hawaii_drivers_license_number|Erkennt die Lizenznummer des Hawaii-Treibers|nein|
|Func_hong_kong_id_card |Erkennt Hongkong-ID-Karte|nein|
|Func_hungarian_value_added_tax_number|Erkennt die Mehrwertsteuernummer für Ungarn|nein|
|Func_hungary_eu_national_id_card|Erkennt die persönliche Identifikationsnummer für Ungarn|nein|
|Func_hungary_eu_ssn_or_equivalent|Erkennt Die Nummer der sozialen Sicherheit in Ungarn|nein|
|Func_hungary_eu_tax_file_number|Erkennt die Steuerdateinummer für Ungarn|nein|
|Func_iban|Erkennt IBAN|ja|
|Func_idaho_drivers_license_number|Erkennt die Lizenznummer des Idaho-Treibers|nein|
|Func_illinois_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Chicago".|nein|
|Func_india_aadhaar|erkennt Indien aadhaar|ja|
|Func_indiana_drivers_license_number|Erkennt die Führerscheinnummer des Indiana-Treibers|nein|
|Func_iowa_drivers_license_number|Erkennt die Lizenznummer des Iowa-Treibers|nein|
|Func_ireland_pps|erkennt Irland PPS|nein|
|Func_israeli_national_id_number|erkennt die nationale ID-Nummer Israels|nein|
|Func_italy_eu_national_id_card |Erkennt den Steuercode für Italien|nein|
|Func_italy_value_added_tax_number|Erkennt die Mehrwertsteuernummer für Italien|nein|
|Func_japanese_my_number_corporate|Erkennt Japan my number corporate|ja|
|Func_japanese_my_number_personal|erkennt Japan meine Nummer persönlich|ja|
|Func_jp_bank_account|Erkennt das japanische Bankkonto|nein|
|Func_jp_bank_account_branch_code|Erkennt die Japanische Bankkonto-Zweigstellennummer|nein|
|Func_jp_drivers_license_number|Erkennt die Japanische Führerscheinnummer|nein|
|Func_jp_passport|Erkennt den japanischen Reisepass|nein|
|Func_jp_resident_registration_number|Erkennt die registrierungsnummer für japanansässige Einwohner|nein|
|Func_jp_sin|erkennt Japan SIN|nein|
|Func_jp_sin_pre_1997|erkennt Japanische Sin vor 1997|nein|
|Func_kansas_drivers_license_number|Erkennt die Lizenznummer des Kansas-Treibers|nein|
|Func_kentucky_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Kentucky".|nein|
|Func_kentucky_massachusetts_virginia_drivers_license_number|Erkennt die Lizenznummer des Führerscheins von "Kentucky", "Massachusetts" und "Virginia".|nein|
|Func_latvia_eu_national_id_card|Erkennt den persönlichen Code für Lettland|nein|
|Func_lithuania_eu_tax_file_number|Erkennt den persönlichen Code für Litauen|nein|
|Func_louisiana_drivers_license_number|Erkennt die Lizenznummer des Louisiana-Treibers|nein|
|Func_luxemburg_eu_tax_file_number|erkennt luxemburgische nationale Identifikationsnummer (natürliche Personen)|nein|
|Func_luxemburg_eu_tax_file_number_non_natural|erkennt luxemburgische nationale Identifikationsnummer (nicht natürliche Personen)|nein|
|Func_maine_drivers_license_number|Erkennt die Führerscheinnummer des Maine-Treibers|nein|
|Func_manitoba_drivers_license_number|Erkennt die Lizenznummer des Manitoba-Treibers|nein|
|Func_maryland_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Maryland".|nein|
|Func_massachusetts_drivers_license_number|Erkennt die Führerscheinnummer des Massachusetts-Treibers|nein|
|Func_mexico_population_registry_code|Erkennt Mexiko-Registrierungscode für die Bevölkerung|nein|
|Func_michigan_minnesota_drivers_license_number|Erkennt die Lizenznummer des Autolenkers in "Detroit" (Minnesota).|nein|
|Func_minnesota_drivers_license_number|Erkennt die Führerscheinnummer des Minnesota-Treibers|nein|
|Func_mississippi_oklahoma_drivers_license_number|Erkennt die Führerscheinnummer von "Mississippi", "Oklahoma".|nein|
|Func_missouri_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Missouri".|nein|
|Func_montana_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Montana".|nein|
|Func_nebraska_drivers_license_number|Erkennt die Lizenznummer des Nebraska-Treibers|nein|
|Func_netherlands_bsn|erkennt niederländischen BSN|nein|
|Func_netherlands_eu_tax_file_number|Erkennt die Niederländische Steuerdateinummer|nein|
|Func_netherlands_value_added_tax_number|Erkennt niederländische Umsatzsteuernummer|nein|
|Func_nevada_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Nevada".|nein|
|Func_new_brunswick_drivers_license_number|Erkennt die Führerscheinnummer des New Brunswick-Treibers|nein|
|Func_new_hampshire_drivers_license_number|Erkennt die Führerscheinnummer des New -Hampshire-Treibers|nein|
|Func_new_jersey_drivers_license_number |Erkennt die Führerscheinnummer des New Jersey-Treibers|nein|
|Func_new_mexico_drivers_license_number |Erkennt die Führerscheinnummer des New Mexico-Treibers|nein|
|Func_new_york_drivers_license_number   |Erkennt die Führerscheinnummer des New Yorker Treibers|nein|
|Func_new_zealand_bank_account_number   |Erkennt die Nummer des Neuseeländischen Bankkontos|nein|
|Func_new_zealand_inland_revenue_number |Erkennt die Inlandsumsatznummer neuseelands|nein|
|Func_new_zealand_ministry_of_health_number|erkennt die Gesundheitsnummer des neuseeländischen Gesundheitsministeriums|nein|
|Func_newfoundland_labrador_drivers_license_number|Erkennt die Lizenznummer des Newfoundland Labrador-Treibers|nein|
|Func_newzealand_driver_license_number  |Erkennt die Neuseeländische Führerscheinnummer|nein|
|Func_newzealand_social_welfare_number  |erkennt Die Nummer für soziales Wohl in Neuseeland|nein|
|Func_north_carolina_drivers_license_number|Erkennt die Lizenznummer des North Carolina-Treibers|nein|
|Func_north_dakota_drivers_license_number|Erkennt die Lizenznummer des North -Dakota-Treibers|nein|
|Func_norway_id_number  |Erkennt norwegen-ID-Nummer|nein|
|Func_nova_scotia_drivers_license_number|Erkennt die Lizenznummer des Treibers von "NovaSchottland".|nein|
|Func_ohio_drivers_license_number   |Erkennt die Führerscheinnummer des Ohio-Treibers|nein|
|Func_ontario_drivers_license_number    |Erkennt die Lizenznummer des Kanadischen Führerscheins|nein|
|Func_pennsylvania_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Pennsylvania".|nein|
|Func_pesel_identification_number   |Erkennt die nationale POLNISCHE ID (PESEL)|nein|
|Func_poland_eu_tax_file_number |Erkennt die Polnische Steuerdateinummer|nein|
|Func_polish_national_id    |Erkennt Polen-Identitätskarte|nein|
|Func_polish_passport_number    |Erkennt polnische Reisepassnummer|nein|
|Func_polish_regon_number   |Erkennt polnische REGON-Nummer|nein|
|Func_portugal_eu_tax_file_number|Erkennt Portugals Steueridentifikationsnummer|nein|
|Func_prince_edward_island_drivers_license_number|Erkennt die Lizenznummer des Prince Edward Island-Treibers|nein|
|Func_quebec_drivers_license_number |Erkennt die Lizenznummer des Quebec-Treibers|nein|
|Func_randomized_formatted_ssn  |erkennt randomisierte formatierte US-SSN|ja|
|Func_randomized_unformatted_ssn|erkennt zufällige unformatierte US-SSN|ja|
|Func_rhode_island_drivers_license_number|Erkennt die Lizenznummer des Rhode Island-Treibers|nein|
|Func_romania_eu_national_id_card   |erkennt Rumänien persönlichen numerischen Code (CNP)|nein|
|Func_saskatchewan_drivers_license_number|Erkennt die Lizenznummer des Saskatchewan-Treibers|nein|
|Func_slovakia_eu_national_id_card  |Erkennt die persönliche Nummer der Slowakei|nein|
|Func_slovenia_eu_national_id_card  |Erkennt die eindeutige Master Citizen Number für Slowenien|nein|
|Func_slovenia_eu_tax_file_number   |Erkennt die Steuerdateinummer für Slowenien|nein|
|Func_south_africa_identification_number|Erkennt südafrikanische Identifikationsnummer|ja|
|Func_south_carolina_drivers_license_number|Erkennt die Führerscheinnummer des South Carolina-Treibers|nein|
|Func_south_dakota_drivers_license_number|Erkennt die Lizenznummer des South -Dakota-Treibers|nein|
|Func_south_korea_resident_number   |Erkennt die Südkoreanernummer|nein|
|Func_spain_eu_DL_and_NI_number_citizen |erkennt Spanien DL- und NI-Nummer-Bürger|nein|
|Func_spain_eu_DL_and_NI_number_foreigner|erkennt Spanien DL- und NI-Nummern-Fremden|nein|
|Func_spain_eu_driver's_license_number  |Erkennt die Lizenznummer des Spanien-Führerscheins|nein|
|Func_spain_eu_tax_file_number  |Erkennt spanien-Steuerdateinummer|nein|
|Func_spanish_social_security_number|Erkennt spanische Sozialversicherungsnummer|nein|
|Func_ssn   |Funktion zum Erkennen nicht zufällig formatierter US-SSN|ja|
|Func_sweden_eu_tax_file_number|Erkennt die Steuerdateinummer für Schweden|nein|
|Func_swedish_national_identifier|erkennt schwedische nationale ID|ja|
|Func_swiss_social_security_number_ahv|Erkennt die Schweizerische Sozialversicherungsnummer AHV|nein|
|Func_taiwanese_national_id |erkennt taiwanesische nationale ID|nein|
|Func_tennessee_drivers_license_number|Erkennt die Lizenznummer des Treibers von "Tennessee".|nein|
|Func_texas_drivers_license_number  |Erkennt die Führerscheinnummer des Texaners|nein|
|Func_Thai_Citizen_Id   |Erkennt thailändische Citizen-ID|nein|
|Func_Turkish_National_Id|Erkennt die nationale ID der Türkei|ja|
|Func_uk_drivers_license|Erkennt den Führerschein des Vereinigten Königreiches|nein|
|Func_uk_eu_tax_file_number|Erkennt die eindeutige Nummer des britischen Steuerzahlers|nein|
|Func_uk_nhs_number |erkennt die BRITISCHE NHS-Nummer|ja|
|Func_uk_nino   |erkennt UK NINO|nein|
|Func_unformatted_canadian_sin|Erkennt unformatierte kanadische SIN|nein|
|Func_unformatted_itin  |Erkennt unformatiertes US ITIN|ja|
|Func_unformatted_ssn   |erkennt nicht zufällige unformatierte US-SSN|ja|
|Func_usa_uk_passport   |Erkennt usa und uk passport|ja|
|Func_utah_drivers_license_number|Erkennt die Führerscheinnummer des Utah-Treibers|nein|
|Func_vermont_drivers_license_number|Erkennt die Lizenznummer des Vermont-Treibers|nein|
|Func_virginia_drivers_license_number|Erkennt die Lizenznummer des Virginia-Treibers|nein|
|Func_washington_drivers_license_number|Erkennt die Führerscheinnummer des Washingtoner Treibers|nein|
|Func_west_virginia_drivers_license_number|Erkennt die Lizenznummer des West -Virginia-Treibers|nein|
|Func_wisconsin_drivers_license_number  |Erkennt die Lizenznummer des Wisconsin-Treibers|nein|
|Func_wyoming_drivers_license_number    |Erkennt die Lizenznummer des Wyoming-Treibers|nein|


## <a name="func_us_date"></a>Func_us_date

Func_us_date sucht nach Datumsangaben in gängigen US-Formaten. Die gängigen Formate sind "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr". Die Namen oder Abkürzungen von Monaten werden nicht zwischen Klein- und Kleinschreibung beachtet. 
  
Beispiele:
  
- 2. Dezember 2016
    
- 02.12.16
    
- 02.12.16
    
- 12/2/2016
    
- 12/02/16
    
- 2. Dezember 2016
    
- 12-2-16
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates sucht nach Datumsangaben in allgemeinen E.U. Formate (und die meisten Orte außerhalb der USA), z. B. "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Jahr des Tagesmonats". Die Namen oder Abkürzungen von Monaten werden nicht zwischen Klein- und Kleinschreibung beachtet.
  
Beispiele:
  
- 2. Dezember 2016
    
- 02.12.16
    
- 2. Dezember 16
    
- 2/12/2016
    
- 02/12/16
    
- 2.12.2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
- Niederländisch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul sep sept okt okt nov dec
    
- Französisch
    
  - janvier, février, mars, avril, mai, juin juillet, aoūt, septembre, octobre, novembre, décembre
    
  - janv. févr. mars util mai juin juil. aoūt sept. okt. nov. déc.
    
- Deutsch
    
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Juli August. Sept. Okt. Nov. Dez.
    
- Italienisch
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
    
- Portugiesisch
    
  - janeiro, fiebereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Spanisch
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, novembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. okt. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da sie nur portugiesische Monatsnamen unterstützt, die jetzt in der obigen  `Func_eu_date` Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum im format, das häufig in Portugiesisch verwendet wird. Das Format für diese Funktion ist identisch mit , unterschiedliche nur  `Func_eu_date` in der verwendeten Sprache.
  
Beispiele:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Portugiesisch
    
  - janeiro, fiebereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da sie nur niederländische Monatsnamen unterstützt, die nun in der obigen  `Func_eu_date` Funktion enthalten sind. 
  
Diese Funktion sucht nach einem Datum im format, das häufig in Niederländisch verwendet wird. Das Format für diese Funktion ist identisch mit , unterschiedliche nur  `Func_eu_date` in der verwendeten Sprache.
  
Beispiele:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Akzeptierte Monatsnamen:
  
- Niederländisch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul sep sept out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date sucht nach Datumsangaben in Formaten, die häufig von Kredit- und Debitkarten verwendet werden. Diese Funktion wird Datumsangaben im Format "Monat/Jahr", "Monat-Jahr", "[Monatsname] Jahr" und "[Monatsabkürzung] Jahr" entsprechen. Die Namen oder Abkürzungen von Monaten werden nicht zwischen Klein- und Kleinschreibung beachtet.
  
Beispiele:
  
- MM/YY – z. B. 11.01. oder 1.11.
    
- MM/YYYYY – z. B. 01/2011 oder 1/2011
    
- MM-YYY – z. B. 01-22 oder 1-11
    
- MM-YYYYY – z. B. 01-2000 oder 1-2000
    
Die folgenden Formate unterstützen YY oder YYYY:
  
- Monat-JJJJ – z. B. Jan-2010 oder Januar-2010 oder Jan-10 oder 10. Januar
    
- Monat JJJJ – z. B. "Januar 2010" oder "Jan 2010" oder "10. Januar" oder "10. Januar"
    
- MonthYYYY – z. B. "januar2010" oder "Jan2010" oder "januar10" oder "Jan10"
    
- Monat/JJJJ – z. B. "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"
    
Akzeptierte Monatsnamen:
  
- Englisch
    
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
    
  - Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address nach einem US-Bundesstaatsnamen oder einer Postabkürzung gefolgt von einer gültigen Postleitzahl. Die Postleitzahl muss eine der korrekten Postleitzahlen sein, die dem Us.S.-Statusnamen oder der Abkürzung zugeordnet sind. Der Name des US-Bundesstaats und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.
  
Beispiele:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
