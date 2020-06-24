---
title: Auskunftsrecht betroffener Personen für Dynamics 365 im Rahmen der DSGVO und CCPA
description: Lernen Sie, wie Sie personenbezogene Daten finden und behandeln und wie Sie auf DSR- und CCPA-Anforderungen von Dynamics 365-Kunden reagieren können.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817664"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Auskunftsrecht betroffener Personen für Dynamics 365 im Rahmen der DSGVO und CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

In ähnlicher Weise bietet der California Consumer Privacy Act (CCPA) den kalifornischen Verbrauchern Datenschutzrechte und -pflichten, einschließlich von Rechten, die den Rechten von betroffenen Personen der DSGV entsprechen, wie z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) der persönlichen Informationen.  Das CCPA ermöglicht außerdem bestimmte Offenlegungen, Schutz vor Diskriminierung bei der Wahl von Ausübungsrechten und Deaktivierungs-/Aktivierungsanforderungen für bestimmte Datentransfers, die als "Verkäufe" eingestuft werden. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](offering-ccpa.md) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](ccpa-faq.md).

In dem Leitfaden wird erläutert, wie unsere als Datenverantwortliche handelnden Kunden Microsoft-Produkte, -Dienste und -Verwaltungstools zum Suchen von und Reagieren auf personenbezogene Daten als Reaktion auf DSRs verwenden können. Dies gilt insbesondere für die Suche nach, den Zugriff auf sowie die Verarbeitung von personenbezogenen Daten oder persönlichen Informationen, die sich in der Microsoft-Cloud befinden. Im Folgenden finden Sie eine kurze Übersicht über die Prozesse, die in diesem Leitfaden beschrieben werden:

- **Erkennung:** Sie können Kundendaten, die ggf. Gegenstand eines Antrags einer betroffenen Person sind, mithilfe von Such- und Ermittlungstools finden. Sobald Sie potenziell relevante Dokumente ermittelt haben, können Sie dem Antrag entsprechend eine oder mehrere der in den folgenden Schritten beschriebenen Aktionen ausführen. Möglicherweise stellen Sie jedoch fest, dass der Antrag nicht den Vorgaben Ihrer Organisation für die Beantwortung von Anträgen auf Rechteausübung entspricht.
- **Zugriff:** Rufen Sie personenbezogene Daten ab, die sich in der Microsoft Cloud befinden, und erstellen Sie eine Kopie, die der betroffenen Person zur Verfügung gestellt werden kann, sofern dies beantragt wurde.
- **Berichtigung:** Nehmen Sie gegebenenfalls Änderungen vor oder führen Sie andere beantragte Aktionen für die personenbezogenen Daten aus.
- **Einschränken:** Schränken Sie die Verarbeitung von personenbezogenen Daten ein, indem Sie entweder die Lizenzen für verschiedene Onlinedienste entfernen oder die gewünschten Dienste, wenn möglich, deaktivieren. Ihre Möglichkeiten:
- **Löschen:** Entfernen Sie personenbezogene Daten, die sich in der Microsoft-Cloud befinden, dauerhaft.
- **Exportieren/Empfangen (Portierbarkeit):** Stellen Sie der betroffenen Person eine elektronische Kopie (in einem maschinenlesbaren Format) von personenbezogenen Daten oder persönlichen Informationen zur Verfügung. Personenbezogene Informationen gemäß CCPA sind alle Informationen, die eine identifizierte oder identifizierbare Person betreffen. Es wird nicht zwischen privaten, öffentlichen oder beruflichen Rollen einer Person unterschieden. Der definierte Begriff "persönliche Informationen" entspricht in etwa dem Begriff "persönliche Daten" unter der DSGVO. Allerdings umfasst das CCPA auch Familien- und Haushaltsdaten. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](offering-ccpa.md) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](ccpa-faq.md).

In jedem Abschnitt dieses Leitfadens werden die Prozesse beschrieben, die ein als Datenverantwortlicher handelndes Unternehmen nutzen kann, um auf einen Antrag einer betroffenen Person bezüglich ihrer personenbezogenen Daten in der Microsoft-Cloud zu reagieren.

### <a name="gdpr-terminology"></a>Terminologie der DSGVO

Nachfolgend finden Sie Definitionen von Begriffen, die für diesen Leitfaden relevant sind:

- **Datenverantwortlicher:** Eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die allein oder gemeinsam mit anderen die Zwecke und Mittel der Verarbeitung personenbezogener Daten bestimmt. Sofern die Zwecke und Mittel der Verarbeitung durch das Recht der Union oder der Mitgliedstaaten bestimmt werden, können der Datenverantwortliche bzw. die spezifischen Kriterien für dessen Benennung durch das Recht der Union oder des Mitgliedstaats angegeben werden.
- **Personenbezogene Daten und betroffene Person:** Alle Informationen über eine identifizierte oder identifizierbare natürliche Person ("betroffene Person"). Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt, insbesondere durch Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.
- **Verarbeiter:** Eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die personenbezogene Daten im Auftrag des Verantwortlichen verarbeitet.
- **Kundendaten:** Alle Daten, einschließlich aller Text-, Sound-, Video- oder Bilddateien, die Microsoft vom Kunden oder im Auftrag des Kunden durch Nutzung von Enterprise-Diensten bereitgestellt werden. Kundendaten umfassen sowohl (1) Informationen zur Identifikation von Endbenutzern (z. B. Benutzernamen und Kontaktinformationen in Azure Active Directory) als auch Kundeninhalte, die ein Kunde in einen bestimmten Dienst hochlädt oder in diesem erstellt (z. B. Kundeninhalte in einem Azure Storage-Konto, Kundeninhalte in einer Azure SQL-Datenbank oder das Image einer virtuellen Maschine eines Kunden in Azure Virtual Machines).
- **Vom System generierte Protokolle:** Von Microsoft generierte Protokolle und verbundene Daten, die Microsoft bei der Bereitstellung von Enterprise-Diensten für Benutzer unterstützen. Vom System generierte Protokolle enthalten in erster Linie pseudonymisierte Daten, z. B. eindeutige Bezeichner – in der Regel eine vom System generierte Zahl, die von sich aus eine Einzelperson nicht identifizieren kann, aber dazu verwendet wird, die Enterprise-Dienste für Benutzer bereitzustellen. Vom System generierte Protokolle enthalten möglicherweise auch Informationen zur Identifikation von Endbenutzern, z. B. einen Benutzernamen.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>So kann Sie dieser Leitfaden bei der Einhaltung Ihrer Verantwortlichkeiten als Datenverantwortlicher unterstützen

Der aus zwei Teilen bestehende Leitfaden erklärt, wie Dynamics 365-Produkte, -Dienste und -Verwaltungstools verwendet werden können, um Daten in der Microsoft-Cloud zu finden und zu nutzen als Reaktion auf Anforderungen von betroffenen Personen, die von ihren Rechten gemäß der DSGVO Gebrauch machen. Der erste Teil befasst sich mit personenbezogenen Daten, die in Kundendaten enthalten sind, gefolgt von einem Teil zu sonstigen pseudonymisierten personenbezogenen Daten, die in vom System generierten Protokollen enthalten sind.

- **Teil 1: Reaktion auf Anträge betroffener Personen bezüglich personenbezogener Daten, die in Kundendaten enthalten sind:** Teil 1 dieses Leitfadens erläutert, wie auf personenbezogene Daten in Dynamics 365-Anwendungen (Software-as-a-Service), die als Teil der Kundendaten verarbeitet werden, die Sie dem Onlinedienst zur Verfügung gestellt haben, zugegriffen, wie diese berichtigt, eingeschränkt, gelöscht und exportiert werden können.
- **Teil 2: Reaktion auf Anträge betroffener Personen bezüglich pseudonymisierten Daten:** Wenn Sie Dynamics 365 Enterprise Services verwenden, generiert Microsoft einige Informationen (in diesem Dokument als *vom System generierte Protokolle bezeichnet*), um den Dienst bereitzustellen, der auf den Verwendungsumfang von Endbenutzern beschränkt ist, um deren Aktionen im System zu identifizieren. Obwohl diese Daten nicht ohne das Hinzuziehen zusätzlicher Informationen einer bestimmten betroffenen Person zugeordnet werden können, ist es möglich, dass ein Teil dieser Daten gemäß der Definition der DSGVO als personenbezogen eingestuft wird. In Teil 2 dieses Leitfadens wird erläutert, wie Sie von Dynamics 365 generierte Protokolle aufrufen, löschen und exportieren können.

### <a name="preparing-for-data-subject-rights-investigations"></a>Vorbereiten auf Untersuchungen im Rahmen von Anträgen betroffener Personen

Wenn betroffene Personen Gebrauch von Ihren Rechten machen und Anträge stellen, müssen die folgenden Punkte berücksichtigt werden:

- Korrekte Identifizierung der Person und Rolle (wie Mitarbeiter, Kunde, Lieferant) mithilfe von Informationen, welche die betroffene Person Ihnen im Rahmen des Antrags bereitgestellt hat. Diese Informationen können ein Name, eine Mitarbeiter-ID oder Kundennummer sowie sonstige Kennungen sein.
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Vergewissern Sie sich, dass Sie über die Informationen zu dem Antrag verfügen.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Teil 1: Reaktion auf Anträge betroffener Personen bezüglich personenbezogenen Daten, die in Kundendaten enthalten sind.

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Suchen nach Kundendaten

Der erste Schritt der Reaktion auf einen Antrag einer betroffenen Person ist es, die Kundendaten zu suchen und zu ermitteln, die von dem Antrag betroffen sind.

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

***Dynamics 365 for Customer Engagement*** bietet Ihnen mehrere Methoden, um in Datensätzen nach personenbezogenen Daten zu suchen, z. B.: Erweiterte Suche und Suche nach Datensätzen. Diese Funktionen ermöglichen es Ihnen, personenbezogene Daten zu identifizieren (zu finden).

- [Erweiterte Suche](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Suchen Sie nach Datensätzen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) für mehrere Typen von Datensätzen

In Dynamics 365 for Marketing haben Sie die folgenden zusätzlichen Funktionen:

1. [Erstellen von Power BI-Berichten](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm), um Kundendaten zu filtern und zu identifizieren.
2. Nutzen Sie die Insight-Ansichten für Kontakte und Objekte der Marketingversion, um zusätzliche Datenpunkte zu identifizieren, die Kundendaten enthalten können.

***Dynamics 365 Customer Service Insights*** bietet eine Liste von Ressourcen, die Ihnen helfen, [Kundendaten zu finden](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery), um auf DSGVO-Anträge von Kunden zu reagieren. 

***Dynamics 365 for Finance and Operations*** bietet Ihnen mehrere Möglichkeiten, nach Kundendaten zu suchen. Als Mandantenadministrator können Sie die folgenden Aktionen durchführen, um nach Kundendaten zu suchen:

- Sie können Ihre Kundendaten so organisieren, dass sie dem schnellen Auffinden personenbezogener Daten dienen. Hier finden Sie Informationen dazu, [wie Sie den Datenbestand klassifizieren](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Verwenden des [Personensuchberichts](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), um personenbezogene Daten zu suchen und zu erfassen.
- [Erweitern des Personensuchberichts](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) durch Erstellen einer neuen Entität oder Erweitern einer vorhandenen Entität.
- Verwenden Sie Such- und Filterfunktionen, um bestimmte personenbezogene Daten zu finden und diese mit Hilfe der Microsoft Office-Exportfunktion zu exportieren, oder drucken Sie diese Informationen mit Hilfe von Browsererweiterungen in ein .pdf-Format.
- Erstellen Sie ein benutzerdefiniertes Formular, das personenbezogene Daten sucht und exportiert.
- Erstellen Sie ein externes Portal oder eine externe Website, das bzw. die es einem authentifizierten Kunden ermöglicht, seine personenbezogenen Daten einzusehen.

***Dynamics 365 Business Central*** bietet mehrere Optionen, mit denen Sie nach Daten suchen können. Einzelheiten hierzu finden Sie unter [Suchen, Filtern und Sortieren von Daten](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters).

***Dynamics 365 for Talent*** bietet erweiterte Such- und Filterfunktionen, um bestimmte personenbezogene Daten zu finden. Außerdem stellt es Microsoft Office-Exportfunktionen zur Verfügung, um diese Informationen mithilfe von Browsererweiterungen in ein .pdf-Format zu exportieren oder zu drucken.

- Verwenden des [Personensuchberichts](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), um Kundendaten zu suchen und zu erfassen.
- [Erweitern des Personensuchberichts](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) durch Erstellen einer neuen Entität oder Erweitern einer vorhandenen Entität.

### <a name="providing-a-copy-of-customer-data"></a>Bereitstellen einer Kopie der Kundendaten

Kundendaten in ***Dynamics 365 for Customer Engagement*** können mit den umfangreichen Exportfunktionen exportiert werden. Kundendaten können in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit einfacher erfüllen zu können. Mit Excel können Sie dann die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Dynamics 365 for Customer Engagement-Datensätze können auch über die [Common Data Service-Web-API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview) exportiert werden.

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** ermöglicht es Ihnen, mithilfe von Datenexporten [eine Kopie der Kundendaten bereitzustellen](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export).

Kundendaten in ***Dynamics 365 for Finance and Operations*** können mithilfe der umfassenden Exportfunktionen für Entitäten exportiert werden. Unter Verwendung von [*Datenverwaltungs- und Integrationsentitäten*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity) kann der Mandantenadministrator bereitgestellte Entitäten verwenden, neue Entitäten erstellen oder bestehende Entitäten für einen wiederholbaren Export personenbezogener Daten nach Excel oder einer Reihe anderer gängiger Formate unter Verwendung von [*Datenimport- und -exportaufträgen*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job) erweitern.  Alternativ können viele Listen in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit einfacher erfüllen zu können. Werden Kundendaten nach Excel exportiert, können Sie die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und die Datei dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Sie können auch den *Personensuchbericht* verwenden, um der betroffenen Person Daten zur Verfügung zu stellen, die Sie als personenbezogene Daten klassifiziert haben.

In ***Dynamics 365 Business Central*** können Sie zwei Funktionen nutzen, um eine Kopie der Kundendaten an eine betroffene Person zu übermitteln:

Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

In ***Dynamics 365 for Talent*** können Sie die Option [Personensuchbericht erweitern](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) verwenden, um Informationen zu erfassen, die für den Antrag einer betroffenen Person auf eine Kopie ihrer personenbezogenen Daten hilfreich sind.

### <a name="rectifying-customer-data"></a>Berichtigen von Kundendaten

***Dynamics 365 for Customer Engagement*** gibt Ihnen folgende Möglichkeiten, ungenaue oder unvollständige Kundendaten zu korrigieren oder Kundendaten zu löschen:

- Suchen Sie nach Kundendaten mithilfe der unter „Suchen nach Kundendaten“ genannten Funktionen, und bearbeiten Sie die Daten direkt in Customer Engagement-Formularen. Änderungen können auf einer einzigen Zeilenebene oder direkt in mehreren Zeilen vorgenommen werden.
- Für die Massenverarbeitung mehrerer Customer Engagement-Berichte können Sie das Microsoft Office-Add-In verwenden, um Daten nach Microsoft Excel zu exportieren, Ihre Änderungen vorzunehmen und die geänderten Daten aus Excel in Dynamics 365 for Customer Engagement zu importieren.

Darüber hinaus haben Sie in Dynamics 365 for Marketing auch folgende Optionen:

- Aktualisieren meiner Datenzielseite, indem Sie einzelne oder mehrere Zeilen direkt bearbeiten
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** bietet auch Funktionen, mit denen Organisationen [Kundendaten korrigieren oder ändern](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary) können.

In ***Dynamics 365 for Finance and Operations*** können Sie auch [*Anpassungstools*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) verwenden, aber die Entscheidung und Umsetzung liegt in Ihrer Verantwortung.

***Dynamics 365 Business Central*** bietet zwei Möglichkeiten, ungenaue oder unvollständige Kundendaten zu korrigieren.

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Sie können Kundendaten, die in einem beliebigen Feld gespeichert sind, z. B. Informationen über einen Kunden in der Kundenkarte, ändern, indem Sie das Datenelement, das die betroffenen personenbezogenen Daten enthält, manuell bearbeiten. Für Details siehe [Eingabe von Daten](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Kurzer Hinweis zum Ändern von Einträgen in geschäftlichen Transaktionen

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>Einschränken der Verarbeitung von Kundendaten

Wenn Sie einen Antrag einer betroffenen Person auf Einschränkung der Verarbeitung von Kundendaten erhalten, können Sie die betroffenen Kundendaten einfach aus dem Onlinedienst extrahieren und in einem separaten Container (d. h. Vor-Ort-Speicherung oder separater Webdienst mit Datenisolierung) speichern, der von den Verarbeitungsfunktionen einer beliebigen Cloud-Anwendung isoliert ist.

Alternative Mechanismen wie z. B. Datenverarbeitungsblocks werden von ***Dynamics 365 Business Central*** angeboten, wo den Benutzern die Möglichkeit geboten wird, bestimmte Datensätze zu blockieren. Einzelheiten finden Sie unter [Einschränken der Datenverarbeitung für eine betroffene Person](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Wenn ein Datensatz als gesperrt markiert ist, stellt Dynamics 365 Business Central die Verarbeitung der Kundendaten der betroffenen Person ein. Sie können keine neuen Transaktionen anlegen, die einen gesperrten Datensatz verwenden; z. B. können Sie keine neue Rechnung für einen Kunden erstellen, wenn entweder der Kunde oder der Verkäufer gesperrt ist.

### <a name="deleting-customer-data"></a>Löschen von Kundendaten

Wenn eine betroffene Person Sie auffordert, ihre Kundendaten zu löschen, gibt es mehrere Möglichkeiten, dies zu tun:

- Für die Massenverarbeitung mehrerer Dynamics 365-Berichte können Sie das Microsoft Office-Add-In verwenden, um Daten nach Microsoft Excel zu exportieren, Ihre Änderungen vorzunehmen und die geänderten Daten aus Excel in den Onlinedienst zu importieren.
- Sie können Kundendaten, die in einem beliebigen Feld gespeichert sind, löschen, indem Sie die zu löschenden Daten suchen und dann das Datenelement, das die Zielkundendaten enthält, manuell löschen, z. B. durch ein endgültiges Löschen des Kontaktdatensatzes, der die betroffene Person repräsentiert, und anderer Datensätze, die personenbezogene Daten enthalten.

Zusätzlich wird bei Dynamics 365 Marketing durch die Löschung eines Kontaktes sichergestellt, dass auch Interaktionsdaten mit personenbezogenen Daten entfernt werden. Für alle benutzerdefinierten Felder oder Entitäten müssen Sie Ihr System so anpassen, dass es alle Kundendaten aus zugehörigen Datensätzen löscht und/oder deren Verknüpfung mit dem Kontaktdatensatz löscht, sodass alle personenbezogenen Daten entfernt werden. Weitere Informationen: [Entwicklerhandbuch (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** bietet Unternehmen auch die Möglichkeit, [Kundendaten zu löschen](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Alternativ können Sie in ***Dynamics 365 for Finance and Operations*** auch [*Anpassungstools*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) verwenden, um Kundendaten zu löschen/ändern.

Wenn eine betroffene Person Sie auffordert, seine/ihre personenbezogenen Daten zu löschen, die in Ihren Kundendaten enthalten sind, gibt es in ***Dynamics 365 Business Central*** mehrere Möglichkeiten, diese Anforderung zu erfüllen:

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Sie können in jedem Feld gespeicherte Kundendaten löschen, indem Sie das Datenelement, das die Zielkundendaten enthält, manuell löschen. Für Details siehe [Eingabe von Daten](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Sie können Kundendaten direkt löschen, indem Sie z. B. einen Kontakt löschen und anschließend den Batchauftrag „Protokolleinträge zu abgebrochenen Interaktionen löschen“ ausführen, um Interaktionen für diesen Kontakt zu löschen.
- Sie können [Dokumente löschen](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents), die Kundendaten enthalten, z. B. Notizen und gebuchte Verkaufs- und Eingangsrechnungen.

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Exportieren von Kundendaten

Als Reaktion auf einen Antrag auf Datenübertragbarkeit können Kundendaten in ***Dynamics 365 for Customer Engagement*** mit den umfangreichen Exportfunktionen exportiert werden. Kundendaten können in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit einfacher erfüllen zu können. Mit Excel können Sie dann die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern.

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

Für ***Dynamics 365 Customer Service Insights*** können Sie zum [Exportieren von Kundendaten](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) das Azure-Verwaltungsportal verwenden.

***Dynamics 365 for Finance and Operations*** bietet [Datenverwaltungs- und Integrationsentitäten](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), mit denen bereitgestellte Entitäten verwendet, neue Entitäten erstellt oder bestehende Entitäten für einen wiederholbaren Export personenbezogener Daten nach Excel oder einer Reihe anderer gängiger Formate unter Verwendung von [Datenimport- und -exportaufträgen](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job) erweitert werden können.  Alternativ können viele Listen in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit einfacher erfüllen zu können. Werden Kundendaten auf diese Weise nach Excel exportiert, können Sie die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und die Datei dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern.

Sowohl Dynamics 365 for Finance and Operations als auch ***Dynamics 365 for Talent*** bieten einen Personensuchbericht an, um der betroffenen Person die Daten bereitzustellen, die Sie als personenbezogene Daten klassifiziert haben. 

***Dynamics 365 Business Central*** bietet die folgenden Funktionen:

- Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Teil 2: Reagieren auf Anträge betroffener Personen für vom System generierte Protokolle

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Daten zu Produkt- und Dienstnutzung, z. B. Aktivitätsprotokolle
- Suchanfragen und Abfragedaten von Benutzern
- Daten, die durch Produkte und Dienste als Produkt der Systemfunktionalität und Interaktion von Benutzern oder anderen Systemen erzeugt werden

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>Zugreifen auf und Exportieren von vom System generierte(n) Protokolle(n)

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. Gehen Sie zum [Microsoft Service Trust-Portal](https://servicetrust.microsoft.com/) und melden Sie sich mit den Anmeldeinformationen des globalen Dynamics 365-Administrators an.
2. In der **Datenschutz**-Dropdownliste klicken Sie am oberen Rand der Seite auf **Antrag einer betroffenen Person**.
3. Auf der Seite **Antrag einer betroffenen Person** unter **Vom System generierte Protokolle** klicken Sie auf **Datenprotokollexport**.
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. Wenn Sie eine neue Anforderung für einen Benutzer erstellen möchten, klicken Sie auf **Anforderung zum Exportieren von Daten erstellen**.

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure unterstützt dies, indem es Ihrer Organisation ermöglicht, die Daten im nativen JSON-Format in den angegebenen Azure Storage-Container zu exportieren. Artikel [Einführung in Microsoft Azure Storage – Blob-Speicher](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage). Die abgerufenen Daten enthalten keine Daten, die die Sicherheit und Stabilität des Diensts beeinträchtigen können.

> [!IMPORTANT]
> Sie müssen ein Mandantenadministrator sein, um Benutzerdaten aus dem Mandanten exportieren können.

Die folgende Tabelle fasst den Zugriff auf und den Export von vom System generierten Protokollen zusammen:

| | |
|:----|:---|
| | |
|**Wie lange benötigt das Tool für den Datenprotokollexport von Microsoft, um eine Anforderung abzuschließen?**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**Welches Format weist die Ausgabe auf?**| Die Ausgabe ist in maschinenlesbaren Dateien, z. B. XML, CSV oder JSON, strukturiert. |
|**Welche Daten werden durch das Tool für den Datenprotokollexport ausgegeben?**| Das Tool für den Datenprotokollexport gibt vom System generierte Protokolle aus, die Microsoft speichert. Die exportierten Daten umfassen mehrere Microsoft-Dienste, einschließlich Office 365, Azure und Dynamics. |
|***Wer hat Zugriff auf das Tool für den Datenprotokollexport und kann Zugriffsanforderungen für vom System generierte Protokolle senden?**| Globale Administratoren von Dynamics 365 haben Zugriff auf das DSGVO-Hilfsprogramm zur Verwaltung von Protokollen. |
|**Wie werden Daten an den Benutzer zurückgegeben?**| Die Daten werden an den Azure-Speicherort Ihrer Organisation exportiert; es ist Sache der Administratoren in Ihrer Organisation, zu bestimmen, wie sie diese Daten den Benutzern anzeigen/bereitstellen. |
|**Wie werden Daten in vom System generierten Protokollen dargestellt?**| Beispiel für ein vom System generiertes Protokoll im JSON-Format: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Löschen von vom System generierten Protokollen

Wenn Sie vom System generierte Protokolle löschen möchten, die über eine Zugriffsanforderung abgerufen wurden, müssen Sie den Benutzer aus dem Dienst entfernen und dessen Azure Active Directory-Konto endgültig löschen. Anweisungen dazu, wie ein Benutzer dauerhaft gelöscht wird, finden Sie im Abschnitt [Schritt 5: Löschen](gdpr-dsr-azure.md#step-5-delete) im Thema „Leitfaden für Anträge betroffener Personen in Azure“. Es ist wichtig zu beachten, dass das Benutzerkonto nach dem Initiieren des Löschvorgangs endgültig gelöscht wird. Durch die dauerhafte Löschung eines Benutzerkontos werden die Daten des Benutzers – mit Ausnahme von Daten, die für die Sicherheit und die Stabilität des Dienstes wesentlich sind – innerhalb von 30 Tagen aus vom System generierten Protokollen für fast alle Dynamics 365-Dienste entfernt.

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
