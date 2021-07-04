---
title: Wonach die Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) suchen
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
description: Erfahren Sie, wonach die Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) suchen.
ms.openlocfilehash: 787abc1e7fb4c95392a76f7514ceffd3f7f4dda0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288095"
---
# <a name="what-the-dlp-functions-look-for"></a>Wonach die DLP-Funktionen suchen

Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können vertrauliche Informationstypen verwenden, um vertrauliche Elemente zu identifizieren. Kreditkartennummer und EU-Debitkartennummer sind Beispiele für Typen vertraulicher Informationen. Typen vertraulicher Informationen suchen nach bestimmten Mustern. Typen vertraulicher Informationen überprüfen die Daten, indem sie ihr Format, ihre Prüfsummen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. Der Typ vertraulicher Kreditkartennummern verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind. Dies hilft zu bestätigen, dass es sich bei einer Zahl um eine Kreditkartennummer handelt.

In diesem Artikel wird erläutert, wonach diese Funktionen suchen, um zu verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren. Weitere Informationen finden Sie unter [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>Tabelle der Funktionen

<br>

****

|Funktionsname|Funktionsaktion|ist ein Validator|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|Erkennt und überprüft den eindeutigen Steuerschlüssel Argentiniens|Nein|
|Func_aba_routing|Erkennt die ABA-Routingnummer|ja|
|Func_alabama_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_alaska_delaware_oregon_drivers_license_number|erkennt Die Führerscheinnummer von Einerz, Delaware und Einer|Nein|
|Func_alaska_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_alberta_drivers_license_number|Erkennt Die Führerscheinnummer von Einera|Nein|
|Func_Argentina_Unique_Tax_Key|Erkennt den eindeutigen Steuerschlüssel Argentiniens|Nein|
|Func_arizona_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_arkansas_drivers_license_number|Erkennt die Arkansas-Führerscheinnummer|Nein|
|Func_australian_business_number|Erkennt die Geschäftliche Nummer Australiens|Nein|
|Func_Australian_Company_Number|Erkennt die Firmennummer Australiens|Nein|
|Func_australian_medical_account_number|erkennt die Kontonummer des medizinischen Kontos für Australien|Nein|
|Func_australian_tax_file_number|Erkennt die Australische Steuernummer|ja|
|Func_austria_eu_ssn_or_equivalent|erkennt die Sozialversicherungsnummer Österreichs|Nein|
|Func_austria_eu_tax_file_number|Erkennt die Steuernummer Österreichs|Nein|
|Func_Austria_Value_Added_Tax|erkennt Die Umsatzsteuer für Österreich|Nein|
|Func_belgium_national_number|Erkennt die nationale Zahl Belgiens|Nein|
|Func_belgium_value_added_tax_number|erkennt die Umsatzsteuernummer Belgiens|Nein|
|Func_brazil_cnpj|erkennt die Juristische Personennummer Brasiliens (CNPJ)|ja|
|Func_brazil_cpf|erkennt Brasilien CPF|ja|
|Func_brazil_rg|erkennt Brasilien RG|Nein|
|Func_british_columbia_drivers_license_number|Erkennt die Lizenznummer des britischen Führerscheins|Nein|
|Func_bulgaria_eu_national_id_card|erkennt uniforme Uniform-Notrufnummer für Ungarn|Nein|
|Func_california_drivers_license_number|Erkennt die California-Führerscheinnummer|Nein|
|Func_canadian_sin|erkennt Kanadas Sin|ja|
|Func_chile_id_card|Erkennt die Chile-ID-Karte|Nein|
|Func_china_resident_id|Erkennt die in China ansässigen IDs|Nein|
|Func_colorado_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_connecticut_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_credit_card|erkennt Kreditkarte|ja|
|Func_croatia_id_card|Erkennt die Kroatien-ID-Karte|Nein|
|Func_croatia_oib_number|erkennt die OIB-Nummer für Kroatien|Nein|
|Func_cyprus_eu_tax_file_number|erkennt Steuernummer des Steuersyntaxs|Nein|
|Func_czech_id_card|Erkennt die tschechische ID-Karte|Nein|
|Func_czech_id_card_new_format|Erkennt die tschechische ID-Karte im neuen Format|Nein|
|Func_dea_number|Erkennt die DEA-Nummer|ja|
|Func_denmark_eu_tax_file_number|erkennt die persönliche Identifikationsnummer Dänemarks|Nein|
|Func_district_of_columbia_drivers_license_number|Erkennt die Führerscheinnummer des Schulbezirks|Nein|
|Func_estonia_eu_national_id_card|erkennt den persönlichen Identifikationscode für Estnisch|Nein|
|Func_eu_debit_card|Erkennt EU-Debitkarte|Nein|
|Func_finnish_national_id|Erkennt die nationale finnisch-ID|Nein|
|Func_florida_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detects Minnesota, Minnesota, Minnesota driver's license number|Nein|
|Func_formatted_itin|Erkennt formatierte US-ITIN|ja|
|Func_fr_insee|erkennt Frankreich INSEE|Nein|
|Func_fr_passport|erkennt Frankreich-Passport|Nein|
|Func_france_eu_tax_file_number|Erkennt die Steuernummer frankreichs|Nein|
|Func_france_value_added_tax_number|erkennt die Französische Umsatzsteuernummer|Nein|
|Func_french_drivers_license|Erkennt den französischen Führerschein|Nein|
|Func_french_insee|erkennt französischen INSEE|Nein|
|Func_georgia_drivers_license_number|Erkennt die Lizenznummer des georgischen Führerscheins|Nein|
|Func_german_drivers_license|Erkennt deutschlandweiten Führerschein|Nein|
|Func_german_passport|erkennt Deutschland Passport|Nein|
|Func_german_passport_data|erkennt Deutschland Passport|Nein|
|Func_germany_eu_tax_file_number|erkennt Steuernummer für Deutschland|Nein|
|Func_germany_value_added_tax_number|erkennt die Umsatzsteuernummer in Deutschland|Nein|
|Func_greece_eu_ssn|erkennt Die Sin von Griechenland (AMKA)|Nein|
|Func_hawaii_drivers_license_number|erkennt die Lizenznummer des Führerscheins|Nein|
|Func_hong_kong_id_card|Erkennt die Hongkong-ID-Karte|Nein|
|Func_hungarian_value_added_tax_number|erkennt die Umsatzsteuernummer für Ungarn|Nein|
|Func_hungary_eu_national_id_card|erkennt die persönliche Identifikationsnummer Ungarns|Nein|
|Func_hungary_eu_ssn_or_equivalent|erkennt Ungarn sozialversicherungsnummern|Nein|
|Func_hungary_eu_tax_file_number|erkennt steuerdateinummer für Ungarn|Nein|
|Func_iban|erkennt IBAN|ja|
|Func_idaho_drivers_license_number|Erkennt die Idaho-Führerscheinnummer|Nein|
|Func_illinois_drivers_license_number|Erkennt die Lizenznummer des Computers|Nein|
|Func_india_aadhaar|detects India aadala|ja|
|Func_indiana_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_iowa_drivers_license_number|Erkennt die Iowa-Führerscheinnummer|Nein|
|Func_ireland_pps|erkennt Irland PPS|Nein|
|Func_israeli_national_id_number|erkennt die nationale ID-Nummer von Israel|Nein|
|Func_italy_eu_national_id_card|Erkennt den Finanzcode Italiens|Nein|
|Func_italy_value_added_tax_number|erkennt die Umsatzsteuernummer für Italien|Nein|
|Func_japanese_my_number_corporate|erkennt Japan meine Nummer "Unternehmensnummer"|ja|
|Func_japanese_my_number_personal|erkennt Japan meine persönliche Nummer|ja|
|Func_jp_bank_account|erkennt Japan-Bankkonto|Nein|
|Func_jp_bank_account_branch_code|Erkennt die Bankverbindungscode für Japan-Konten|Nein|
|Func_jp_drivers_license_number|Erkennt die Japanische Führerscheinnummer|Nein|
|Func_jp_passport|erkennt Japan Passport|Nein|
|Func_jp_resident_registration_number|erkennt die in Japan ansässigen Registrierungsnummer|Nein|
|Func_jp_sin|erkennt Japan SIN|Nein|
|Func_jp_sin_pre_1997|erkennt Japans Sin vor 1997|Nein|
|Func_kansas_drivers_license_number|Erkennt die Lizenznummer des Computers|Nein|
|Func_kentucky_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detects, Massachusetts, Countys driver's license number|Nein|
|Func_latvia_eu_national_id_card|erkennt persönlichen Code für Lettisch|Nein|
|Func_lithuania_eu_tax_file_number|erkennt persönlichen Code für Litauen|Nein|
|Func_louisiana_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_luxemburg_eu_tax_file_number|erkennt die nationale Identifikationsnummer Luxemburgs (natürliche Personen)|Nein|
|Func_luxemburg_eu_tax_file_number_non_natural|erkennt die nationale Identifikationsnummer von Luxemburg (nicht natürliche Personen)|Nein|
|Func_maine_drivers_license_number|Erkennt die Maine-Führerscheinnummer|Nein|
|Func_manitoba_drivers_license_number|Erkennt die Manitoba-Führerscheinnummer|Nein|
|Func_maryland_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_massachusetts_drivers_license_number|erkennt die Führerscheinnummer von Massachusetts|Nein|
|Func_mexico_population_registry_code|Erkennt den Registrierungscode der Mexiko-Population|Nein|
|Func_michigan_minnesota_drivers_license_number|erkennt Die Führerscheinnummer von Minnesota.|Nein|
|Func_minnesota_drivers_license_number|Erkennt die Lizenznummer des Minnesota-Führerscheins.|Nein|
|Func_mississippi_oklahoma_drivers_license_number|erkennt Die Lizenznummer des Führerscheins|Nein|
|Func_missouri_drivers_license_number|Erkennt die Lizenznummer des Computers|Nein|
|Func_montana_drivers_license_number|Erkennt die Lizenznummer des Unternehmens.|Nein|
|Func_nebraska_drivers_license_number|erkennt Nebraska-Führerscheinnummer|Nein|
|Func_netherlands_bsn|erkennt den niederländischen BSN|Nein|
|Func_netherlands_eu_tax_file_number|erkennt die Steuernummer der Niederlande|Nein|
|Func_netherlands_value_added_tax_number|erkennt die Umsatzsteuernummer der Niederlande|Nein|
|Func_nevada_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_new_brunswick_drivers_license_number|erkennt die Neue Brunswick-Führerscheinnummer|Nein|
|Func_new_hampshire_drivers_license_number|Erkennt die Lizenznummer des neuen Lenkungsmoduls|Nein|
|Func_new_jersey_drivers_license_number|Erkennt die New Jersey-Führerscheinnummer|Nein|
|Func_new_mexico_drivers_license_number|Erkennt die New-Mexiko-Führerscheinnummer|Nein|
|Func_new_york_drivers_license_number|Erkennt die New York-Führerscheinnummer|Nein|
|Func_new_zealand_bank_account_number|erkennt die Neuseeländische Bankkontonummer|Nein|
|Func_new_zealand_inland_revenue_number|erkennt die Neuseeländische Inlandsumsatznummer|Nein|
|Func_new_zealand_ministry_of_health_number|erkennt neuseelandländische Gesundheitsnummer|Nein|
|Func_newfoundland_labrador_drivers_license_number|erkennt die Newfoundland Labrador-Führerscheinnummer|Nein|
|Func_newzealand_driver_license_number|erkennt die Neuseeländische Führerscheinnummer|Nein|
|Func_newzealand_social_welfare_number|erkennt Neuseeland soziale Netzwerke Zahlen|Nein|
|Func_north_carolina_drivers_license_number|Erkennt die North-North-Pilot-Lizenznummer|Nein|
|Func_north_dakota_drivers_license_number|Erkennt die North-North-Lizenznummer|Nein|
|Func_norway_id_number|erkennt Norwegen-ID-Nummer|Nein|
|Func_nova_scotia_drivers_license_number|Erkennt die Lizenznummer des Nova Scotia-Treibers|Nein|
|Func_ohio_drivers_license_number|Erkennt die Lizenznummer des Führerscheins in Derz|Nein|
|Func_ontario_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_pennsylvania_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_pesel_identification_number|detects Poland National ID (PESEL)|Nein|
|Func_poland_eu_tax_file_number|erkennt die Steuernummer Polens|Nein|
|Func_polish_national_id|Erkennt die Polen-Identitätskarte|Nein|
|Func_polish_passport_number|erkennt die nummer des reisepasses für Polen|Nein|
|Func_polish_regon_number|erkennt die regon-Nummer des Polen|Nein|
|Func_portugal_eu_tax_file_number|erkennt Portugals Steueridentifikationsnummer|Nein|
|Func_prince_edward_island_drivers_license_number|erkennt Die Führerscheinnummer der Insel 2013|Nein|
|Func_quebec_drivers_license_number|Erkennt die Lizenznummer des Quebec-Treibers|Nein|
|Func_randomized_formatted_ssn|erkennt zufällig formatierte US-SSN|ja|
|Func_randomized_unformatted_ssn|erkennt zufällige unformatierte US-SSN|ja|
|Func_rhode_island_drivers_license_number|Erkennt die Lizenznummer der Insel".|Nein|
|Func_romania_eu_national_id_card|erkennt persönlichen numerischen Code (Personal Numeric Code, CNP) für Rumänien|Nein|
|Func_saskatchewan_drivers_license_number|erkennt die Saskatchewan-Führerscheinnummer|Nein|
|Func_slovakia_eu_national_id_card|Erkennt die persönliche Nummer der Slowakei|Nein|
|Func_slovenia_eu_national_id_card|Erkennt die eindeutige Master-Citizen-Nummer Für Slowenien|Nein|
|Func_slovenia_eu_tax_file_number|Erkennt die Steuernummer Sloweniens|Nein|
|Func_south_africa_identification_number|erkennt südafrikanische Identifikationsnummer|ja|
|Func_south_carolina_drivers_license_number|Erkennt die Lizenznummer des Süd-Endpunkts|Nein|
|Func_south_dakota_drivers_license_number|Erkennt die Lizenznummer des South-Computers|Nein|
|Func_south_korea_resident_number|erkennt die gebietsansässige Nummer Südkoreas|Nein|
|Func_spain_eu_DL_and_NI_number_citizen|erkennt die Dl- und NI-Nummern in Spanien|Nein|
|Func_spain_eu_DL_and_NI_number_foreigner|erkennt spaniens DL- und NI-Nummer des Fremden|Nein|
|s_license_number Func_spain_eu_driver|Erkennt die Spanische Führerscheinnummer|Nein|
|Func_spain_eu_tax_file_number|Erkennt die Steuernummer Spaniens|Nein|
|Func_spanish_social_security_number|Erkennt die spanische Sozialversicherungsnummer|Nein|
|Func_ssn|Funktion zum Erkennen eines nicht zufällig formatierten US-SSN|ja|
|Func_sweden_eu_tax_file_number|Erkennt die Steuernummer Schwedens|Nein|
|Func_swedish_national_identifier|Erkennt den nationalen bezeichner Für Schwedisch|ja|
|Func_swiss_social_security_number_ahv|erkennt die Sozialversicherungsnummer AHV in der Schweiz|Nein|
|Func_taiwanese_national_id|erkennt taiwanesische National-ID|Nein|
|Func_tennessee_drivers_license_number|Erkennt die Führerscheinnummer des Unternehmens|Nein|
|Func_texas_drivers_license_number|Erkennt die Texaner-Führerscheinnummer|Nein|
|Func_Thai_Citizen_Id|Erkennt die thailändische Citizen ID|Nein|
|Func_Turkish_National_Id|Erkennt die türkisch-national-ID|ja|
|Func_uk_drivers_license|erkennt uk-Führerschein|Nein|
|Func_uk_eu_tax_file_number|erkennt eindeutige Steuernummer im Vereinigten Königreich|Nein|
|Func_uk_nhs_number|erkennt UK NHS-Nummer|ja|
|Func_uk_nino|erkennt UK NINO|Nein|
|Func_unformatted_canadian_sin|erkennt unformatierte kanadische SIN|Nein|
|Func_unformatted_itin|erkennt unformatierte US-ITIN|ja|
|Func_unformatted_ssn|erkennt nicht zufällige unformatierte US-SSN|ja|
|Func_usa_uk_passport|erkennt US- und UK-Passport|ja|
|Func_utah_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_vermont_drivers_license_number|Erkennt die Lizenznummer des Verassisters|Nein|
|Func_virginia_drivers_license_number|Erkennt die Lizenznummer des Führerscheins|Nein|
|Func_washington_drivers_license_number|Erkennt die Washington-Führerscheinnummer|Nein|
|Func_west_virginia_drivers_license_number|Erkennt die Lizenznummer des West-Endpunkts|Nein|
|Func_wisconsin_drivers_license_number|Erkennt die Lizenznummer des Computers|Nein|
|Func_wyoming_drivers_license_number|Erkennt die Wyoming-Führerscheinnummer|Nein|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date sucht nach Datumsangaben in gängigen US-Formaten. Die gängigen Formate sind "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.

Beispiele:

- 2. Dezember 2016
- 2. Dezember 2016
- 02. Dezember 2016
- 12/2/2016
- 12/02/16
- 2. Dezember 2016
- 12-2-16

Akzeptierte Monatsnamen:

- Englisch
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
  - Jan. Februar Mrz. Apr. Mai Juli August Sept. Okt. November. Dezember.

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates sucht nach Datumsangaben in der EU Format (und die meisten Orte außerhalb der USA), z. B. "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag-Monat-Jahr". Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.

Beispiele:

- 2. Dezember 2016
- 02. Dezember 2016
- 2. Dezember 16
- 2/12/2016
- 02/12/16
- 2.12.2016
- 2-12-16

Akzeptierte Monatsnamen:

- Englisch
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
  - Jan. Februar Mrz. Apr. Mai Juli August Sept. Okt. November. Dezember.
- Niederländisch
  - januari, februari, maart, April, mei, juni, juli, augustus, september, ocktober, October, November, December
  - jan feb maart apr kel jun jul aug sep sept okt nov dec
- Französisch
  - janvier, février, mars, avril, mai, juin juillet, aoūt, septembre, octobre, novembre, décembre
  - janv. févr. mars avril mai juin juil. aoūt sept. Okt. nov. Déc.
- Deutsch
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
  - Jan./Jän. Februar März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
- Italienisch
  - gennaio, febbraio, marzo, aprile, maggio, giugno, lugio, agosto, settembre, datasetbre, novembre, dicembre
  - Genn. febbr. mr. apr. Magg. giugno luglio ag. sett. Ott. nov. Dic.
- Portugiesisch
  - thes,eiro, março, marc, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez
- Spanisch
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, mayembre, diciembre
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. Okt. nov. Dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da sie nur die portugiesischen Monatsnamen unterstützt, die jetzt in der obigen Funktion enthalten  `Func_eu_date` sind.

Diese Funktion sucht nach einem Datum in dem format, das häufig in Portugiesisch verwendet wird. Das Format für diese Funktion ist identisch mit  `Func_eu_date` , das sich nur in der verwendeten Sprache unterscheidet.

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
  - thes,eiro, março, marc, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (veraltet)

> [!NOTE]
> Diese Funktion ist veraltet, da sie nur niederländische Monatsnamen unterstützt, die jetzt in der obigen Funktion enthalten  `Func_eu_date` sind.

Diese Funktion sucht nach einem Datum in dem format, das häufig in Niederländisch verwendet wird. Das Format für diese Funktion ist identisch mit  `Func_eu_date` , das sich nur in der verwendeten Sprache unterscheidet.

Beispiele:

- 2 Mei 2016
- 02* 2016
- 2 Mei 16
- 2/12/2016
- 02/12/16
- 2-Mei-2016
- 2-12-16

Akzeptierte Monatsnamen:

- Niederländisch
  - januari, februari, maart, April, mei, juni, juli, augustus, september, ocktober, October, November, December
  - jan feb maart apr kel jun jul aug sep sept out okt nov dec

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date sucht nach Datumsangaben in Formaten, die häufig von Kredit- und Debitkarten verwendet werden. Diese Funktion gleicht Datumsangaben im Format "Monat/Jahr", "Monat-Jahr", "[Monatsname] Jahr" und "[Monatsabkürzung] Jahr" ab. Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.

Beispiele:

- MM/JJ - z. B. 11.01. oder 1.11.
- MM/JJJJ – z. B. 01/2011 oder 1/2011
- MM-JJ - z. B. 01-22 oder 1-11
- MM-JJJJ - z. B. 01-2000 oder 1-2000

Die folgenden Formate unterstützen JJJ oder JJJJ:

- Monat-JJJJ – z. B. Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10
- Monat JJJJ – z. B. "Januar 2010" oder "Jan 2010" oder "10. Januar" oder "10. Januar"
- MonthYYYY – z. B. "january2010" oder "Jan2010" oder "january10" oder "Jan10"
- Monat/JJJJ – z. B. "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"

Akzeptierte Monatsnamen:

- Englisch
  - Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember
  - Jan Feb Mrz Apr Mai Juli Aug Sept Oct Dec

## <a name="func_us_address"></a>Func_us_address

Func_us_address sucht nach einem US-bundesstaatsnamen oder einer Postleitzahl, gefolgt von einer gültigen Postleitzahl. Die Postleitzahl muss eine der korrekten Postleitzahlen sein, die dem US-Bundesstaatsnamen oder der Abkürzung zugeordnet sind. Der Us-Bundesstaatsname und die Postleitzahl können nicht durch Satzzeichen oder Buchstaben getrennt werden.

Beispiele:

- Washington 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
