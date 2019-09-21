---
title: Inhalt der DLP-Richtlinienvorlagen
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Datenverlust Verhinderung (DLP) im Office 365 &amp; Security Compliance Center umfasst vorgefertigte Richtlinienvorlagen, die allgemeine Compliance-Anforderungen erfüllen, beispielsweise zum Schutz vertraulicher Informationen unterliegen dem U.S.-Krankenversicherungsgesetz ( HIPAA), u.s. Gramm-Leach-Bliley Act (GLBA) oder u.s. Patriot Act. In diesem Thema werden alle Richtlinienvorlagen, die Arten von vertraulichen Informationen, die Sie suchen, und die Standardbedingungen und-Aktionen aufgelistet.
ms.openlocfilehash: aff9f5179d9bad3d8c1c97d17473a14995137c32
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082042"
---
# <a name="what-the-dlp-policy-templates-include"></a>Inhalt der DLP-Richtlinienvorlagen

Datenverlust Verhinderung (DLP) im Office 365 &amp; Security Compliance Center umfasst vorgefertigte Richtlinienvorlagen, die allgemeine Compliance-Anforderungen erfüllen, beispielsweise zum Schutz vertraulicher Informationen unterliegen dem U.S.-Krankenversicherungsgesetz ( HIPAA), u.s. Gramm-Leach-Bliley Act (GLBA) oder u.s. Patriot Act. In diesem Thema werden alle Richtlinienvorlagen, die Arten von vertraulichen Informationen, die Sie suchen, und die Standardbedingungen und-Aktionen aufgelistet. In diesem Thema werden nicht alle Details zur Konfiguration der einzelnen Richtlinienvorlagen berücksichtigt. Stattdessen stellt das Thema genügend Informationen bereit, damit Sie entscheiden können, welche Vorlage der beste Ausgangspunkt für Ihr Szenario ist. Denken Sie daran, dass Sie diese Richtlinienvorlagen entsprechend Ihren spezifischen Anforderungen anpassen können.
  
## <a name="australia-financial-data"></a>Finanzdaten – Australien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Australien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Australische Steuernummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Australische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Australien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Australische Steuernummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Australische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Australien: Health Records Act (HRIP Act)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Australien HRIP: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Steuernummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Australische Medical Account-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Australien HRIP: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Steuernummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Australische Medical Account-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Personenbezogene Informationen (PII-Daten) – Australien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PII-Daten – Australien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Steuernummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Australische Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PII-Daten – Australien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Steuernummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Australische Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="australia-privacy-act"></a>Datenschutzgesetz – Australien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Datenschutz – Australien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Australische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Datenschutz – Australien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Australische Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Australische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-financial-data"></a>Finanzdaten – Kanada

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Health Information Act (HIA) – Kanada

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|HIA – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|HIA – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Kanada: Personal Health Act (PHIPA) – Ontario

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Kanada – PHIPA: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Kanada – PHIPA: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Personal Health Information Act (PHIA) – Manitoba, Kanada

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PHIA – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PHIA – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Personal Information Protection Act (PIPA) – Kanada

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PIPA – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PIPA – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Kanada: Personal Information Protection Act (PIPEDA)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PIPEDA – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PIPEDA – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Personenbezogene Informationen (PII-Daten) – Kanada

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PII – Kanada: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PII – Kanada: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kanadische Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Sozialversicherungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kanadische Personal Health Identification-Nummer (PHIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="france-data-protection-act"></a>Datenschutzgesetz – Frankreich

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|DPA – Frankreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Französische Carte nationale d'identité (CNI) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Französische Sozialversicherungsnummer (INSEE) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|DPA – Frankreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Französische Carte nationale d'identité (CNI) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Französische Sozialversicherungsnummer (INSEE) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="france-financial-data"></a>Finanzdaten – Frankreich

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Frankreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  EU Debit Card-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Frankreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  EU Debit Card-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Frankreich: Personenbezogene Informationen (PII-Daten)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Frankreich – PII: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Französische Sozialversicherungsnummer (INSEE) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Französische Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Französische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Französische Carte nationale d'identité (CNI) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Frankreich – PII: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Französische Sozialversicherungsnummer (INSEE) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Französische Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Französische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Französische Carte nationale d'identité (CNI) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>DSGVO (EU-Datenschutz-Grundverordnung)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Niedriges Volumen von EU-vertraulichen Inhalten gefunden  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  EU Debit Card-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  EU-Führerscheinnummer – min. Count 1, Max count 9  <br/>  EU-nationale Identifikationsnummer-min. Count 1, Max count 9  <br/>  EU-Passport-Nummer – min. Count 1, max. Anzahl 9  <br/>  EU-Sozialversicherungsnummer (SSN) oder äquivalente ID – min. Count 1, Max count 9  <br/>  EU-Steueridentifikationsnummer (TIN) – min. Anzahl 1, max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Senden von Vorfall Berichten an den Administrator  <br/> |
|Hoher Umfang an vertraulichen Inhalten in der EU gefunden  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  EU Debit Card-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  EU-Führerscheinnummer – min. Count 1, Max count 9  <br/>  EU-nationale Identifikationsnummer-min. Count 1, Max count 9  <br/>  EU-Passport-Nummer – min. Count 1, max. Anzahl 9  <br/>  EU-Sozialversicherungsnummer (SSN) oder äquivalente ID – min. Count 1, Max count 9  <br/>  EU-Steueridentifikationsnummer (TIN) – min. Anzahl 1, max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Einschränken des Zugriffs auf Inhalte für externe Benutzer  <br/>  Benachrichtigen von Benutzern mit e-Mail-und Richtlinien Tipps  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Senden von Vorfall Berichten an den Administrator  <br/> |
   
## <a name="germany-financial-data"></a>Finanzdaten – Deutschland

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Deutschland: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  EU Debit Card-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Deutschland: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  EU Debit Card-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Deutschland: Personenbezogene Informationen (PII-Daten)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Deutschland – PII: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Deutsche Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Deutsche Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Deutschland – PII: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Deutsche Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Deutsche Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="israel-financial-data"></a>Finanzdaten – Israel

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Israel: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Israel: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Personenbezogene Informationen (PII-Daten) – Israel

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Israel – PII: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Ausweis-ID – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Israel – PII: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Ausweis-ID – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Datenschutzgesetz – Israel

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Israel – Datenschutz: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Ausweis-ID – Min. Anzahl 1, Max. Anzahl 9  <br/>  Israelische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Israel – Datenschutz: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Israelische Ausweis-ID – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Israelische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="japan-financial-data"></a>Finanzdaten – Japan

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Japan: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Japan: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Japan: Personenbezogene Informationen (PII-Daten)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Japan – PII: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Einwohnerregistrierungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Japanische Sozialversicherungsnummer (SIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Japan – PII: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Einwohnerregistrierungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Japanische Sozialversicherungsnummer (SIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Schutz persönlicher Informationen – Japan

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Japan – PPI: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Einwohnerregistrierungsnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Japanische Sozialversicherungsnummer (SIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Japan – PPI: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Japanische Einwohnerregistrierungsnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Japanische Sozialversicherungsnummer (SIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>PCI Data Security Standard (PCI-DSS)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PCI-DSS: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PCI-DSS: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Gesetz gegen Internetkriminalität – Saudi-Arabien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|ACC – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  International Banking Account Number (IBAN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|ACC – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  International Banking Account Number (IBAN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Finanzdaten – Saudi-Arabien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  International Banking Account Number (IBAN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  International Banking Account Number (IBAN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Personenbezogene Informationen (PII-Daten) – Saudi-Arabien

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PII – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Saudi-Arabische Ausweisnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PII – Saudi-Arabien: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Saudi-Arabische Ausweisnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>Access to Medical Reports Act – Vereinigtes Königreich

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|AMRA – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britannien National Health Service Number-min count 1, Max count 9  <br/>  Britannien Sozialversicherungsnummer (Nino) – min. Anzahl 1, max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|AMRA – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britannien National Health Service Number-min count 10, Max count any  <br/>  Britannien National Insurance Number (Nino) – min count 10, Max count any  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-data-protection-act"></a>Datenschutzgesetz – Vereinigtes Königreich

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Datenschutzgesetz – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 1, Max. Anzahl 9  <br/>  USA/U.K. Passnummer – min. Count 1, max. Anzahl 9  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Datenschutzgesetz – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  USA/U.K. Passnummer – min count 10, Max count any  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-financial-data"></a>Finanzdaten – Vereinigtes Königreich

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Finanzdaten – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  EU Debit Card-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Finanzdaten – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  EU Debit Card-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>Online-Verhaltenskodex für persönliche Informationen – U.K.

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PIOCP – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Britische National Health Service-Nummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PIOCP – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Britische National Health Service-Nummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Vereinigtes Königreich: Personenbezogene Informationen (PII)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PII – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-amerikanische/britische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PII – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Britische nationale Versicherungsnummer (NINO) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-amerikanische/britische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>Richtlinien für Datenschutz und elektronische Kommunikation – UK

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|PECR – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|PECR – Vereinigtes Königreich: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  SWIFT-Code – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>Verbraucherbestimmungen der Federal Trade Commission (FTC) – USA

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|FTC-Bestimmungen – USA: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  ABA Routing Number (US-Bankleitzahl) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|FTC-Bestimmungen – USA: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  ABA Routing Number (US-Bankleitzahl) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-financial-data"></a>USA: Finanzdaten

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|USA – Finanzdaten: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  ABA Routing Number (US-Bankleitzahl) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|USA – Finanzdaten: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  ABA Routing Number (US-Bankleitzahl) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>Gramm-Leach-Bliley Act (GLBA) – USA

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|GLBA – USA: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|GLBA – USA: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>USA: Health Insurance Act (HIPAA)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Inhalt entspricht US-HIPAA  <br/> | Enthält eine der folgenden vertraulichen Informationen:  <br/>  US-Sozialversicherungsnummer (SSN) – min. Count 1, Max count any  <br/>  Drug Enforcement Agency (DEA) number-min count 1, Max count any  <br/> **AND** <br/>  Inhalt enthält einen der folgenden Begriffe:  <br/>  Internationale Klassifikation von Krankheiten (ICD-9-cm) – min count 1, Max count any  <br/>  Internationale Klassifikation von Krankheiten (ICD-10-cm) – min count 1, Max count any  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
   
## <a name="us-patriot-act"></a>Patriot Act – USA

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|Patriot Act – USA: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|Patriot Act – USA: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>USA: Personenbezogene Informationen (PII-Daten)

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|USA – PII: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-amerikanische/britische Reisepassnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|USA – PII: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  US-Steueridentifikationsnummer (ITIN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-amerikanische/britische Reisepassnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>USA: State Breach Notification Laws

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|USA State Breach: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Bankkontonummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Führerscheinnummer – Min. Anzahl 1, Max. Anzahl 9  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|USA State Breach: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  Kreditkartennummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Bankkontonummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Führerscheinnummer – Min. Anzahl 10, Max. Anzahl bel.  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>USA: State Social Security Number Confidentiality Laws

|**Regelname**|**Bedingungen <br/> (einschließlich vertraulicher Informationstypen)**|**Aktionen**|
|:-----|:-----|:-----|
|US-Sozialversicherungsnummer-Gesetze: Extern weitergegebene Inhalte prüfen – niedrige Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 1, Max. Anzahl 9  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> |Benachrichtigung senden  <br/> |
|US-Sozialversicherungsnummer-Gesetze: Extern weitergegebene Inhalte prüfen – hohe Anzahl  <br/> | Inhalt enthält vertrauliche Informationen:  <br/>  US-Sozialversicherungsnummer (SSN) – Min. Anzahl 10, Max. Anzahl bel.  <br/>  Inhalt wird weitergegeben an:  <br/>  Personen außerhalb meiner Organisation  <br/> | Zugriff auf Inhalt sperren  <br/>  Benachrichtigung senden  <br/>  Außerkraftsetzung zulassen  <br/>  Geschäftliche Begründung anfordern  <br/>  Schadensbericht senden  <br/> |
   

