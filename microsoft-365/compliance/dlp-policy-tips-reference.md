---
title: 'Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)'
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie einer Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) einen Benutzer benachrichtigen, dass er mit Inhalten arbeitet, die mit einer DLP-Richtlinie in Konflikt stehen.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903802"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)

DLP-Richtlinientipps in Outlook Web Access werden für alle Bedingungen, Ausnahmen und Aktionen unterstützt, die für die Exchange-Arbeitsauslastung in einer DLP-Richtlinie gelten, mit Ausnahme der folgenden:

**Bedingungen:**

- Sender Is
- Absenderdomäne ist
- Recipient ist Mitglied von
- Kopfzeile enthält Wörter oder Ausdrücke
- Kopfzeile entspricht Mustern
- Dokumentgröße gleich oder größer als
- Nachrichtentyp ist
- Die Wichtigkeit der Nachricht ist
- Inhaltszeichensatz enthält Wörter
- Betreff oder Textkörper enthält Wörter oder Ausdrücke
- Betreff oder Textkörper entspricht Mustern
- Inhaltszeichensatz enthält Wörter
- Inhalt wird von empfangen
- Hat absender den Richtlinientipp außer Kraft gesetzt
- Nachrichtengröße gleich oder größer als
- Sender AD-Attribut enthält Wörter oder Ausdrücke
- Sender AD-Attribut entspricht Mustern
- Dokumentinhalt enthält Wörter oder Ausdrücke
- Dokumentinhalt entspricht Mustern

**Aktionen:**

- Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders
- Weiterleiten der Nachricht zur Genehmigung an bestimmte genehmigende Benutzer
- Umleiten der Nachricht an bestimmte Benutzer
- Hinzufügen von Empfängern zum Feld An
- Hinzufügen von Empfängern zum Cc-Feld
- Hinzufügen von Empfängern zum Bcc-Feld
- Hinzufügen des Vorgesetzten des Absenders als Empfänger
- Hinzufügen eines HTML-Haftungsausschlusses
- Vorausgeöffneter E-Mail-Betreff
- Entfernen von O365-Nachrichtenverschlüsselung und -rechteschutz

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 und höher unterstützt das Anzeigen von Richtlinientipps für nur einige Bedingungen und Ausnahmen

Derzeit unterstützt Outlook 2013 und höher das Anzeigen von Richtlinientipps für Richtlinien, die abgesehen von den unten genannten Bedingungen und entsprechenden Ausnahmen keine Bedingung oder Ausnahme enthalten:

- Inhalt enthält (funktioniert nur für Typen vertraulicher Informationen. Vertraulichkeitsbezeichnungen werden nicht unterstützt)
- Inhalt wird freigegeben

Beachten Sie, dass alle Bedingungen für E-Mails funktionieren, die in der Outlook-Client-App verfasst wurden und inhalte übereinstimmen und Schutzmaßnahmen für Inhalte erzwingen. Das Anzeigen von Richtlinientipps für Benutzer wird jedoch für bedingungen, die abgesehen von den oben genannten bedingungen verwendet werden, nicht unterstützt.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Unterstützung für Outlook 2013 und höher und Office-Apps auf Desktop mit Richtlinientipps für nur einige typen von vertraulichen Informationen

Die Liste der sofort verwendeten typen vertraulicher Informationen, die für die Anzeige von DLP-Richtlinientipps in Outlook on Desktop (2013 und höher) und Office-Apps (Word, Excel, PowerPoint) auf Desktop erkannt werden, sind die folgenden:

- ABA Routing Number (US-Bankleitzahl)
- Argentina National Identity (DNI) Number
- Australische Bankkontonummer
- Australische Medical Account-Nummer
- Australische Reisepassnummer
- Australische Steuernummer
- Azure DocumentDB-Authentifizierungsschlüssel  
- Azure IAAS Database Connection String und Azure SQL Connection String  
- Azure IoT-Verbindungszeichenfolge  
- Azure Publish Setting Password  
- Azure Redis Cache Connection String  
- Azure SAS  
- Azure Service Bus Connection String  
- Azure Storage Account Key  
- Azure Storage Account Key (Generisch)  
- Nationale belgische Nummer
- Brazil CPF Number
- Brasilien – Juristische Personennummer (CNPJ)
- 	Brasilien – Personalausweis (RG)
- Kanadische Bankkontonummer
- Kanadische Führerscheinnummer
- Kanadische Health Service-Nummer
- Kanadische Reisepassnummer
- Kanadische Personal Health Identification-Nummer (PHIN)
- Kanadische Sozialversicherungsnummer
- 	Chile Identity Card Number
- 	China (PRC) – Personalausweisnummer
- Kreditkartennummer
- Kroatische ID-Kartennummer  
- Kroatische persönliche ID-Nummer (OIB)  
- Tschechische Persönliche Identitätsnummer  
- Dänische persönliche ID-Nummer
- Drug Enforcement Agency (DEA)-Nummer
- EU-Debitkartennummer
- EU-Führerscheinnummer  
- Nationale EU-Identifikationsnummer  
- EU-Reisepassnummer  
- EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID  
- EU Tax Identification Number (TIN)  
- Nationale finnische ID-Nummer
- Finnische Reisepassnummer
- Französische Führerscheinnummer
- Französischer Personalausweis (Carte Nationale d'Identité, CNI)
- Französische Reisepassnummer
- Französische Sozialversicherungsnummer (INSEE)
- Deutsche Führerscheinnummer
- Deutsche Reisepassnummer
- Deutsche Personalausweisnummer
- Nationale griechische ID-Karte  
- Hongkong (HKID) - Personalausweisnummer
- Indien – Permanente Kontonummer
- Indien - Eindeutige Identifikationsnummer (Aadhaar)
- Indonesien – Perosonalausweisnummer (KTP)
- International Banking Account Number (IBAN)
- International Classification of Diseases (ICD-10-CM)  
- International Classification of Diseases (ICD-9-CM)  
- IP-Adresse
- Irische PPS-Nummer (Personal Public Service) 
- Israelische Bankkontonummer
- Israelische Ausweis-ID
- Italienische Führerscheinnummer
- Japanische Bankkontonummer
- Japanische Führerscheinnummer
- Japanische Reisepassnummer
- Japanische Einwohnerregistrierungsnummer
- Japanische Sozialversicherungsnummer (SIN)
- Japanische Wohnsitzkartennummer
- Malaysia Identity Card Number
- Nummer des niederländischen Citizen's Service (BSN)  
- Neuseeländische Gesundheitsministeriumsnummer
- Norwegische ID-Nummer  
- Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer
- Polnische Identitätskarte
- Nationale polnische ID-Nummer (PESEL)
- Polnische Reisepassnummer
- Portugiesische ID-Kartennummer (Citizen Card)
- Saudi-Arabische Ausweisnummer
- Singapur – National Registration Identity Card-Nummer (NRIC)
- Südafrika – Identifikationsnummer  
- Südkorea – Einwohnerregistrierungsnummer
- Spanische Sozialversicherungsnummer (SSN)
- SQL Server Verbindungszeichenfolge  
- Nationale schwedische ID-Nummer
- Schwedische Reisepassnummer
- SWIFT-Code
- Taiwanesicher Personalausweis
- 	Taiwan – Reisepassnummer
- Taiwan Resident Certificate (ARC/TARC)
- Thai Population Identification Code
- Nationale Identifikationsnummer der Türkei
- Vereinigtes Königreich – Führerscheinnummer
- Vereinigtes Königreich – Wählerverzeichnisnummer
- UK-Gesundheitsdienstnummer
- UK-Sozialversicherungsnummer (National Insurance Number, NINO)
- USA/Vereinigtes Königreich Passport Number
- US-Bankkontonummer
- US-Führerscheinnummer
- US-Steueridentifikationsnummer (ITIN)
- US-Sozialversicherungsnummer

Beachten Sie, dass benutzerdefinierte Typen vertraulicher Informationen zusätzlich zu den oben genannten typen für vertrauliche Informationen auch für DLP-Richtlinientipps unterstützt werden.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Verhinderung von Datenverlust auf Endpunktgeräten unterstützt Richtlinientipps nur für einige typen von vertraulichen Informationen

Die Liste der sofort verwendeten Typen vertraulicher Informationen, die in Dokumenten erkannt werden, die sich auf Endpunktgeräten befinden, sind folgende:

- ABA Routing Number (US-Bankleitzahl) 
- Argentina National Identity (DNI) Number 
- Australische Bankkontonummer 
- Australische Medical Account-Nummer 
- Australische Reisepassnummer 
- Australische Steuernummer 
- Australische Geschäftsnummer 
- Australische Firmennummer 
- Austria Driver's License Number 
- Austria Identity Card 
- Austria Passport Number 
- Österreich Sozialversicherungsnummer 
- Steueridentifikationsnummer für Österreich 
- Austria Value Added Tax (VAT) Number 
- Azure DocumentDB-Authentifizierungsschlüssel 
- Azure IAAS Database Connection String und Azure SQL Connection String 
- Azure IoT-Verbindungszeichenfolge 
- Azure Publish Setting Password 
- Azure Redis Cache Connection String 
- Azure SAS 
- Azure Service Bus Connection String 
- Azure Storage Account Key 
- Azure Storage Account Key (Generisch) 
- Belgische Führerscheinnummer 
- Nationale belgische Nummer 
- Belgische Reisepassnummer 
- Belgische Umsatzsteuernummer 
- Brazil CPF Number 
- Brasilien – Juristische Personennummer (CNPJ) 
- 	Brasilien – Personalausweis (RG) 
- Kennzeichen des Bulgarien-Führerscheins 
- Bulgarien Reisepassnummer 
- Uniform Civil Number (Bulgarien) 
- Kanadische Bankkontonummer 
- Kanadische Führerscheinnummer 
- Kanadische Health Service-Nummer 
- Kanadische Reisepassnummer 
- Kanadische Personal Health Identification-Nummer (PHIN) 
- Kanadische Sozialversicherungsnummer 
- 	Chile Identity Card Number 
- 	China (PRC) – Personalausweisnummer 
- Kreditkartennummer 
- Kroatische Führerscheinnummer 
- Kroatische ID-Kartennummer 
- Kroatische Nationale ID-Kartennummer 
- Kroatische Reisepassnummer 
- Kroatische persönliche ID-Nummer (OIB) 
- CSCAN-AZURE0060 Azure Storage Account Shared Access Signature 
- CSCAN-GENERAL0140 Allgemeiner symmetrischer Schlüssel 
- Zyprische Führerscheinnummer 
- Identitätskarte für Zypern 
- Reisepassnummer für Zypern 
- Steueridentifikationsnummer für Zypern 
- Tschechische Führerscheinnummer 
- Tschechische Persönliche Identitätsnummer 
- Tschechische Republik Reisepassnummer 
- Dänische Führerscheinnummer 
- Dänische Reisepassnummer 
- Dänische persönliche ID-Nummer 
- Drug Enforcement Agency (DEA)-Nummer 
- Estonia Driver's License Number 
- Estonia Passport Number 
- Estonia Personal Identification Code 
- EU-Debitkartennummer 
- EU-Führerscheinnummer 
- Nationale EU-Identifikationsnummer 
- EU-Reisepassnummer 
- EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID 
- EU Tax Identification Number (TIN) 
- Finland Driver's License Number 
- Finnland Europäische Krankenversicherungsnummer 
- Nationale finnische ID-Nummer 
- Finnische Reisepassnummer 
- Französische Führerscheinnummer 
- Französische Krankenversicherungsnummer 
- Französischer Personalausweis (Carte Nationale d'Identité, CNI) 
- Französische Reisepassnummer 
- Französische Sozialversicherungsnummer (INSEE) 
- Französische Steueridentifikationsnummer (numéro SPI.) 
- Französische Umsatzsteuernummer 
- Deutsche Führerscheinnummer 
- Deutsche Reisepassnummer 
- Deutsche Personalausweisnummer 
- Deutsche Steueridentifikationsnummer 
- Deutsche Umsatzsteuernummer 
- Führerscheinnummer für Griechenland 
- Nationale griechische ID-Karte 
- Griechenland Reisepassnummer 
- Griechenland Sozialversicherungsnummer (AMKA) 
- Griechische Steueridentifikationsnummer 
- Hongkong (HKID) - Personalausweisnummer 
- Ungarische Sozialversicherungsnummer (TAJ) 
- Mehrwertsteuernummer für Ungarn 
- Kennzeichen des Ungarn-Führerscheins 
- Ungarn Reisepassnummer 
- Ungarn Persönliche Identifikationsnummer 
- Ungarn Steueridentifikationsnummer 
- Indien – Permanente Kontonummer 
- Indien - Eindeutige Identifikationsnummer (Aadhaar) 
- Indonesien – Perosonalausweisnummer (KTP) 
- International Banking Account Number (IBAN) 
- International Classification of Diseases (ICD-10-CM) 
- International Classification of Diseases (ICD-9-CM) 
- IP-Adresse 
- Ireland Driver's License Number 
- Irland Reisepassnummer 
- Irische PPS-Nummer (Personal Public Service) 
- Israelische Bankkontonummer 
- Israelische Ausweis-ID 
- Italienische Führerscheinnummer 
- Steuercode für Italien 
- Italienische Reisepassnummer 
- Italienische Mehrwertsteuernummer 
- Japanische Bankkontonummer 
- Japanische Führerscheinnummer 
- Japanische Reisepassnummer 
- Japanische Einwohnerregistrierungsnummer 
- Japanische Sozialversicherungsnummer (SIN) 
- Japanische My Number Corporate 
- Japanisch My Number Personal 
- Japanische Wohnsitzkartennummer 
- Latvia Driver's License Number 
- Latvia Passport Number 
- Persönlichen Code für Lettland 
- Lizenznummer des Litauen-Führerscheins 
- Reisepassnummer für Litauen 
- Persönlichen Code für Litauen 
- LuxemburgEr Führerscheinnummer 
- Nationale Identifikationsnummer (natürliche Personen) 
- Nationale Identifikationsnummer (nicht natürliche Personen) 
- Luxemburg Passport Number 
- Malaysia Identity Card Number 
- Malta Driver's License Number 
- Malta Identity Card Number 
- Malta Passport Number 
- Malta Steuer-ID-Nummer 
- Nummer des niederländischen Citizen's Service (BSN) 
- Niederländische Führerscheinnummer 
- Niederländische Reisepassnummer 
- Niederländische Steueridentifikationsnummer 
- Niederländische Umsatzsteuernummer 
- Bankkontonummer für Neuseeland 
- New Zealand Driver License Number 
- New Zealand Inland Revenue Number 
- Neuseeländische Gesundheitsministeriumsnummer 
- New Zealand Social Welfare Number 
- Norwegische ID-Nummer 
- Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer 
- Polnische Führerscheinnummer 
- Polnische Identitätskarte 
- Nationale polnische ID-Nummer (PESEL) 
- Polnische Reisepassnummer 
- Polnische Steueridentifikationsnummer 
- Polnische REGON-Nummer 
- Portugiesische ID-Kartennummer (Citizen Card) 
- Portugal Driver's License Number 
- Portugal Passport Number 
- Steueridentifikationsnummer für Portugal 
- Romania Driver's License Number 
- Rumänien Reisepassnummer 
- Rumänien – Persönlicher numerischer Code (CNP) 
- Russische Reisepassnummer (Inland) 
- Russische Reisepassnummer (International) 
- Saudi-Arabische Ausweisnummer 
- Singapur – National Registration Identity Card-Nummer (NRIC) 
- Slovakia Driver's License Number 
- Slowakei Reisepassnummer 
- Persönliche Nummer der Slowakei 
- Slovenia Driver's License Number 
- Slowenien Reisepassnummer 
- Slowenien Steueridentifikationsnummer 
- Slowenien Eindeutige Master Citizen Number 
- Südafrika – Identifikationsnummer 
- Südkorea – Einwohnerregistrierungsnummer 
- Spanien DNI 
- Spain Driver's License Number 
- Spanische Reisepassnummer 
- Spanische Sozialversicherungsnummer (SSN) 
- Spanien Steueridentifikationsnummer 
- SQL Server Verbindungszeichenfolge 
- Schwedische Führerscheinnummer 
- Nationale schwedische ID-Nummer 
- Schwedische Reisepassnummer 
- Steueridentifikationsnummer für Schweden 
- SWIFT-Code 
- Swiss Social Security Number AHV 
- Taiwanesicher Personalausweis 
- 	Taiwan – Reisepassnummer 
- Taiwan Resident Certificate (ARC/TARC) 
- Thai Population Identification Code 
- Nationale Identifikationsnummer der Türkei 
- Vereinigtes Königreich – Führerscheinnummer 
- Vereinigtes Königreich – Wählerverzeichnisnummer 
- UK-Gesundheitsdienstnummer 
- UK-Sozialversicherungsnummer (National Insurance Number, NINO) 
- Vereinigtes Königreich Eindeutige Steuernummer 
- USA/Vereinigtes Königreich Passport Number 
- US-Bankkontonummer 
- US-Führerscheinnummer 
- US-Steueridentifikationsnummer (ITIN) 
- US-Sozialversicherungsnummer 
- Ukraine Passport Number (Inland) 
- Ukraine Passport Number (International) 
 
Bitte beachten Sie, dass zusätzlich zu den oben genannten sofort verwendeten Typen vertraulicher Informationen auch benutzerdefinierte Typen vertraulicher Informationen erkannt werden.

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Support matrix for DLP policy tips across Microsoft apps

|**App und Plattform**|**Unterstützung von DLP-Richtlinientipps**|**Unterstützte Typen vertraulicher Informationen**|**Unterstützte Prädikate und Aktionen**|**Kommentare**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alle|Subset|Siehe [Hinweise zu Richtlinientipps zur](#data-loss-prevention-policy-tips-reference) Verhinderung von Datenverlust|
|**Outlook Win32 (Outlook 2013 und darüber hinaus)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|Unter Outlook 2013 und höher finden Sie Richtlinientipps für nur einige Bedingungen und Ausnahmen sowie Unterstützung für [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher und Office-Apps auf Desktop mit Richtlinientipps für nur einige typen vertraulicher Informationen. Weitere Informationen zur Unterstützung vertraulicher Informationstypen sowie von DLP-Bedingungen und -Aktionen, die für die Anzeige von DLP-Richtlinientipps in Outlook Win32 unterstützt werden, finden Sie unter Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) und höher.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine|DLP-Richtlinientipps werden auf Outlook mobilen Geräten nicht unterstützt|
|**Sharepoint Online/One Drive for Business Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alle|Alle SPO/ODB-Prädikate und -Aktionen in DLP||
|**Sharepoint Win32/ One Drive for Business Win32-Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine|#A0 werden in Sharepoint- oder OneDrive-Desktopclient-Apps nicht unterstützt|
|**Word, Excel, PowerPoint Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alle|Alle SPO/ODB-Prädikate und -Aktionen in DLP|Der Tipp für die DLP-Richtlinie wird unterstützt, wenn das Dokument in spo- oder ODB-Web-App gehostet wird und die DLP-Richtlinie bereits gestempelt ist.|
|**Word, Excel, PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine|DLP-Richtlinientipps werden in mobilen Apps für Office nicht unterstützt.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alle|Alle Teams-Prädikate in der DLP-Richtlinie|Richtlinientipps werden angezeigt, wenn eine Nachricht mit "Diese Nachricht wurde gekennzeichnet" gekennzeichnet ist. Was kann ich tun?" Wenn der Benutzer auf den Link klickt, kann er die erkannten Typen vertraulicher Informationen überprüfen und ein Problem außer Kraft setzen oder melden, wenn dies vom Administrator zulässig ist. Beachten Sie, dass keine Richtlinientipps für Dateien angezeigt werden. Wenn der Empfänger versucht, auf das Dokument zu zugreifen, erhält er möglicherweise zugriff verweigert, wenn er nicht zugelassen ist.|
|**Win32-Endpunktgeräte**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Alle Endpunkt-DLP-Prädikate und -Aktionen in der DLP-Richtlinie|Weitere [Informationen finden Sie unter Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac-Geräte**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine|Richtlinien zur Verhinderung von Datenverlust sind heute auf Mac-Geräten nicht durchsetzbar|
|**Cloud-Apps von Drittanbietern**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine|Richtlinientipps zur Verhinderung von Datenverlust werden in Cloud-Apps von Drittanbietern nicht unterstützt.|
|**On-Prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Keine|Keine||
|**Word, Excel, PowerPoint Win32 Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|Informationen zur Liste der unterstützten Typen vertraulicher Informationen finden Sie unter Unterstützung von [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher sowie unter Unterstützung von Office-Apps auf Desktop mit Richtlinientipps für nur einige Typen vertraulicher Informationen.</br></br>Richtlinientipps für WXP-Client-Apps funktionieren für Dokumente, die auf Sharepoint Online- oder One Drive for Business-Websites gespeichert sind, für alle DLP-Richtlinien, die genau die folgende oder eine Teilmenge von Bedingungen oder Aktionen in der DLP-Richtlinie enthalten:</br> <ul><li>Inhalt enthält Typen vertraulicher Informationen</li><li>Zugriffsbereich (Inhalt wird intern/extern freigegeben)</li><li>Benutzer benachrichtigen (Richtlinientipps/Benutzerbenachrichtigungen)</li><li>Blockieren von allen</li><li>Schadensberichte</li></ul></br> Wenn eine andere Bedingung oder Aktion vorhanden ist, wird der DLP-Richtlinientipp für diese Richtlinie nicht in den Desktop-Apps von Word, Excel oder PowerPoint angezeigt.</br>Weitere [Informationen finden Sie unter Richtlinientipps in Excel, PowerPoint](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) und Word|
||||||
