---
title: Anträge betroffener Personen für Dynamics 365 im Rahmen der DSGVO
description: Leitfaden, wie unsere als Datenverantwortliche handelnden Kunden Microsoft-Produkte, -Dienste und -Verwaltungstools zum Suchen und Verarbeiten von personenbezogenen Daten im Rahmen von Anträgen betroffener Personen nach der DSGVO verwenden können.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/30/2019
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: c0783f8146ae04e31e98d638ba90d9f41fc491a8
ms.sourcegitcommit: dc5c297ee7bca212b8a902daebe4907254c4315f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34589791"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>Anträge betroffener Personen für Dynamics 365 im Rahmen der DSGVO

Die europäische [Datenschutz-Grundverordnung (DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gewährt Personen (die in den Bestimmungen als *betroffene Personen* bezeichnet werden) Berechtigungen zum Verwalten der personenbezogenen Daten, die von einem Arbeitgeber oder von einer anderen Art von Behörde oder Organisation (als *Datenverantwortlicher* oder nur *Verantwortlicher* bezeichnet) erfasst werden. Personenbezogene Daten sind im Rahmen der DSGVO weitgefasst als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO erteilt betroffenen Personen bestimmte Rechte für ihre personenbezogenen Daten; dazu gehören das Kopieren der personenbezogenen Daten, das Anfordern von Änderungen, das Einschränken der Verarbeitung, das Löschen oder das Erhalten in einem elektronischen Format, damit sie zu einem anderen Datenverantwortlichen bewegt werden können. Eine formale Anforderung von einer betroffenen Person an einen Datenverantwortlichen im Hinblick auf eine bestimmte Aktion für deren personenbezogene Daten wird in diesem Dokument als *Anforderung einer betroffenen Person* oder DSR bezeichnet.

In diesem Leitfaden wird erläutert, wie Microsoft-Produkte, -Dienste und -Verwaltungstools verwendet werden können, um als Reaktion auf Anträge betroffener Personen unseren als Datenverantwortliche handelnden Kunden dabei zu helfen, personenbezogene Daten zu finden und auf diese zu reagieren. Dies umfasst das Suchen, den Zugriff und die Reaktion auf personenbezogene Daten, die in der Microsoft-Cloud gespeichert sind. Im Folgenden finden Sie eine kurze Übersicht den in diesem Leitfaden beschriebenen Prozesse:

- **Ermittlung:** Verwenden Sie Such- und Ermittlungstools, um Kundendaten leichter zu finden, die möglicherweise Gegenstand eines Antrags einer betroffenen Person sind. Sobald potenziell geeignete Dokumente gefunden wurden, können Sie eine oder mehrere der Aktionen für Anträge betroffener Personen ausführen, die in den folgenden Schritten beschrieben sind, um auf den Antrag der betroffenen Person zu reagieren. Andernfalls können Sie bestimmen, dass der Antrag nicht den Unternehmensrichtlinien für die Reaktion auf Anträge betroffener Personen entspricht.
- **Zugriff:** Rufen Sie personenbezogene Daten ab, die sich in der Microsoft-Cloud befinden, und erstellen Sie eine Kopie, die der betroffenen Person zur Verfügung gestellt werden kann, sofern dies beantragt wurde.
- **Berichtigung:** Nehmen Sie gegebenenfalls Änderungen oder sonstige beantragte Aktionen an den personenbezogenen Daten vor.
- **Einschränken:** Schränken Sie die Verarbeitung von personenbezogenen Daten ein, indem Sie entweder die Lizenzen für verschiedene Onlinedienste entfernen oder die gewünschten Dienste, wenn möglich, deaktivieren.
- **Löschen:** Entfernen Sie personenbezogene Daten, die sich in der Microsoft-Cloud befinden, dauerhaft.
- **Export:** stellen Sie der betroffenen Person eine elektronische Kopie (in einem maschinenlesbaren Format) von personenbezogenen Daten zur Verfügung.

In jedem Abschnitt dieses Leitfadens werden technische Verfahren beschrieben, die ein als Datenverantwortlicher handelndes Unternehmen nutzen kann, um auf einen Antrag einer betroffenen Person bezüglich personenbezogener Daten in der Microsoft-Cloud zu reagieren.

### <a name="gdpr-terminology"></a>Terminologie der DSGVO

Nachfolgend finden Sie Definitionen von Begriffen, die für diesen Leitfaden relevant sind:

- **Datenverantwortlicher:** Eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die allein oder gemeinsam mit anderen die Zwecke und Mittel der Verarbeitung personenbezogener Daten bestimmt. Sofern die Zwecke und Mittel der Verarbeitung durch das Recht der Union oder der Mitgliedstaaten bestimmt werden, können der Datenverantwortliche bzw. die spezifischen Kriterien für dessen Benennung durch das Recht der Union oder des Mitgliedstaats angegeben werden.
- **Personenbezogene Daten und betroffene Person:** Alle Informationen über eine identifizierte oder identifizierbare natürliche Person („betroffene Person“). Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt, insbesondere durch Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.
- **Verarbeiter:** Eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die personenbezogene Daten im Auftrag des Verantwortlichen verarbeitet.
- **Kundendaten:** Alle Daten, einschließlich aller Text-, Sound-, Video- oder Bilddateien, die Microsoft vom Kunden oder im Auftrag des Kunden durch Nutzung von Enterprise-Diensten bereitgestellt werden. Kundendaten umfassen sowohl (1) Informationen zur Identifikation von Endbenutzern (z. B. Benutzernamen und Kontaktinformationen in Azure Active Directory) als auch Kundeninhalte, die ein Kunde in einen bestimmten Dienst hochlädt oder in diesem erstellt (z. B. Kundeninhalte in einem Azure Storage-Konto, Kundeninhalte in einer Azure SQL-Datenbank oder das Image einer virtuellen Maschine eines Kunden in Azure Virtual Machines).
- **Vom System generierte Protokolle:** Von Microsoft generierte Protokolle und verbundene Daten, die Microsoft bei der Bereitstellung von Enterprise-Diensten für Benutzer unterstützen. Vom System generierte Protokolle enthalten in erster Linie pseudonymisierte Daten, z. B. eindeutige Bezeichner – in der Regel eine vom System generierte Zahl, die von sich aus eine Einzelperson nicht identifizieren kann, aber dazu verwendet wird, die Enterprise-Dienste für Benutzer bereitzustellen. Vom System generierte Protokolle enthalten möglicherweise auch Informationen zur Identifikation über Endbenutzer, wie z. B. einen Benutzernamen.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>So kann Sie dieser Leitfaden bei der Einhaltung Ihrer Verantwortlichkeiten als Datenverantwortlicher unterstützen

Der aus zwei Teilen bestehende Leitfaden erklärt, wie Dynamics 365-Produkte, -Dienste und -Verwaltungstools verwendet werden können, um Daten in der Microsoft-Cloud zu finden und zu nutzen als Reaktion auf Anforderungen von betroffenen Personen, die von ihren Rechten gemäß der DSGVO Gebrauch machen. Der erste Teil befasst sich mit personenbezogenen Daten, die in Kundendaten enthalten sind, gefolgt von einem Teil zu sonstigen pseudonymisierten personenbezogenen Daten, die in vom System generierten Protokollen enthalten sind.

- **Teil 1: Reaktion auf Anträge betroffener Personen bezüglich personenbezogener Daten, die in Kundendaten enthalten sind:** Teil 1 dieses Leitfadens erläutert, wie auf personenbezogene Daten in Dynamics 365-Anwendungen (Software as a Service) zugegriffen, wie diese berichtigt, eingeschränkt, gelöscht und exportiert werden können, die als Teil der Kundendaten verarbeitet werden, die Sie dem Onlinedienst zur Verfügung gestellt haben.
- **Teil 2: Reaktion auf Anträge betroffener Personen bezüglich pseudonymisierter Date:.** Wenn Sie Enterprise-Dienste von Dynamics 365 nutzen, generiert Microsoft im Rahmen der Bereitstellung des Service Informationen (in diesem Dokument als *vom System generierte Protokolle* bezeichnet) zur Verwendung durch die Endbenutzer, um ihre Aktionen im System zu ermitteln. Obwohl diese Daten nicht ohne zusätzliche Informationen einer bestimmten betroffenen Person zugeordnet werden können, können manche dieser Daten gemäß der DSGVO als personenbezogen klassifiziert werden. Teil 2 dieses Leitfadens erläutert, wie auf vom System generierte Protokolle von Dynamics 365 zugegriffen werden kann und wie diese gelöscht und exportiert werden können.

### <a name="preparing-for-data-subject-rights-investigations"></a>Vorbereiten auf die Überprüfung im Rahmen von Anträgen betroffener Personen

Wenn betroffene Personen Gebrauch von Ihren Rechten machen und Anträge stellen, müssen die folgenden Punkte berücksichtigt werden:

- Korrekte Identifizierung der Person und Rolle (wie Mitarbeiter, Kunde, Lieferant) mithilfe von Informationen, die die betroffene Person Ihnen im Rahmen des Antrags bereitgestellt hat. Diese Informationen können ein Name, eine Mitarbeiter-ID oder Kundennummer sowie sonstige Kennungen sein.
- Aufzeichnen von Datum und Uhrzeit der Anforderung. (Sie haben 30 Tage Zeit, um die Anforderung zu erfüllen.)
- Bestätigen Sie, dass der Antrag den Anforderungen Ihres Unternehmens bezüglich der Erfüllung oder Ablehnung von Anträgen betroffener Personen entspricht. Zum Beispiel müssen Sie sicherstellen, dass die Ausführung des Antrags nicht im Widerspruch zu anderen rechtlichen, finanziellen oder regulatorischen Verpflichtungen steht, die Sie haben, oder die Rechte und Freiheiten anderer verletzt.
- Vergewissern Sie sich, dass Sie über die Informationen verfügen, die sich auf die Anforderungen beziehen.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Teil 1: Reaktion auf Anträge betroffener Personen bezüglich personenbezogenen Daten, die in Kundendaten enthalten sind.

In den folgenden Artikeln finden Sie Informationen zur Vorbereitung und Reaktion auf Anträge betroffener Personen bezüglich personenbezogener Daten, die in den von Dynamics 365 verarbeiteten Kundendaten enthalten sind. Es ist zu beachten, dass personenbezogene Daten in anderen Kategorien von Daten enthalten sein können, die von Microsoft im Rahmen eines Abonnements für Onlinedienste verarbeitet werden, wie z. B. Administratordaten oder Unterstützungsdaten, die in den Microsoft-Datenschutzbestimmungen definiert sind. Dieses Dokument ist darauf beschränkt, Sie bei der Ermittlung und Verwaltung von Anträgen betroffener Personen zu unterstützen, die personenbezogene Daten betreffen, die in den Kundendaten enthalten sind, die Sie Dynamics 365 zur Verfügung gestellt haben.

Dynamics 365 ist ein Onlinedienst, der mehrere Datenverarbeitungsfunktionen als Software-as-a-Service (SaaS) anbietet. Damit bietet Dynamics 365 eine breite Palette von Funktionen zur Verarbeitung einer vielfältigen Sammlung von Daten, die je nach Art, Zweck oder anderen spezifischen Merkmalen wie Verkaufsdaten, Transaktionen, Finanzen, Personalinformationen usw. variieren können. Angesichts dieser Vielfalt bietet Dynamics 365 mehrere Formulare, Felder, Schemata, Endpunkte und Logik zur Verarbeitung von Kundendaten, was sich auch in den vielfältigen Möglichkeiten widerspiegelt, mit denen Anträge betroffener Personen in den einzelnen Anwendungen bearbeitet werden können. Wenn Dynamics 365-Anwendungen mehrere Möglichkeiten bieten, um auf spezifische Anträge betroffener Personen zu reagieren, werden wir darauf in diesem Leitfaden hinweisen, indem wir auf die technischen Beschreibungen der einzelnen Anwendungen verweisen.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Suchen nach Kundendaten

Der erste Schritt der Reaktion auf einen Antrag einer betroffenen Person ist es, die Kundendaten zu suchen und zu ermitteln, die von dem Antrag betroffen sind.

Die angemessene Klassifizierung von Kundendaten ist der Grundstein für die Arbeit mit personenbezogenen Daten in Dynamics 365 Customer Engagement-Geschäftsanwendungen. Dynamics 365 for Customer Engagement bietet Flexibilität beim Aufbau einer Anwendungserweiterung rund um die Datenklassifizierung. Die richtige Klassifizierung ermöglicht es Ihnen, Informationen als personenbezogene Daten zu identifizieren, wodurch sie im Rahmen eines Antrags einer betroffenen Person gefunden und abgerufen werden können. Es kann auch dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften für die Erhebung und Verwaltung personenbezogener Daten zu ermöglichen.

Microsoft bietet Funktionen, die Sie bei der Reaktion auf Anträge betroffener Personen und in diesem Zusammenhang beim Zugriff auf Kundendaten unterstützen können. Es liegt jedoch in Ihrer Verantwortung, dafür zu sorgen, dass personenbezogene Daten angemessen lokalisiert und klassifiziert werden.

***Dynamics 365 for Customer Engagement*** bietet Ihnen mehrere Methoden, um in Datensätzen nach personenbezogenen Daten zu suchen, z. B.: Erweiterte Suche, Relevanzsuche und Suche nach Datensätzen. Diese Funktionen ermöglichen es Ihnen, personenbezogene Daten zu identifizieren (zu finden).

- [Erweiterte Suche](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Relevanzsuche](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results), die mit Hilfe der Relevanzsuche in Dashboards als zukünftige Referenz gespeichert werden kann
- [Suchen Sie nach Datensätzen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) über mehrere Eintragstypen hinweg

In Dynamics 365 for Marketing haben Sie die folgenden zusätzlichen Funktionen:

1. [Erstellen von Power BI-Berichten](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm), um Kundendaten zu filtern und zu identifizieren.
2. Nutzen Sie die Insight Views zu Kontakten und Objekten der Marketingausführung, um zusätzliche Datenpunkte zu identifizieren, die Kundendaten enthalten können.

***Dynamics 365 Customer Service Insights*** bietet eine Liste von Ressourcen, die Ihnen helfen, [Kundendaten zu finden](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery), um auf DSGVO-Anforderungen von Kunden zu reagieren. 

***Dynamics 365 Finance and Operations*** bietet Ihnen mehrere Möglichkeiten, nach Kundendaten zu suchen. Als Mandantenadministrator können Sie die folgenden Aktionen durchführen, um nach Kundendaten zu suchen:

- Sie können Ihre Kundendaten so organisieren, dass sie dem schnellen Auffinden personenbezogener Daten dienen. Hier finden Sie Informationen dazu, [wie Sie den Datenbestand klassifizieren](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Verwenden der [Personensuchberichts](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), um personenbezogene Daten zu suchen und zu erheben.
- [Erweitern des Personensuchberichts ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) durch Erstellen einer neuen Einheit oder Erweiterung einer vorhandenen Einheit.
- Verwenden Sie Such- und Filterfunktionen, um bestimmte personenbezogene Daten zu finden und diese mit Hilfe der Microsoft Office-Exportfunktion zu exportieren, oder drucken Sie diese Informationen mit Hilfe von Browsererweiterungen in ein .pdf-Format.
- Erstellen Sie ein benutzerdefiniertes Formular, das personenbezogene Daten sucht und exportiert.
- Erstellen Sie ein externes Portal oder eine externe Website, das bzw. die es einem authentifizierten Kunden ermöglicht, seine personenbezogenen Daten einzusehen.

***Dynamics for Business Central*** bietet mehrere Optionen, mit denen Sie nach Daten suchen können. Einzelheiten hierzu finden Sie unter [Suchen, Filtern und Sortieren von Daten](https://docs.microsoft.com/dynamics-nav-app/ui-enter-criteria-filters).

***Dynamics 365 for Talent*** bietet erweiterte Such- und Filterfunktionen, um bestimmte personenbezogene Daten und Microsoft Office-Exportfunktionen zu finden, um diese Informationen mit Hilfe von Browser-Erweiterungen in ein .pdf zu exportieren oder zu drucken.


- Verwenden Sie den [Personensuchbericht](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), um Kundendaten zu suchen und zu erheben.
- [Erweitern des Personensuchberichts ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) durch Erstellen einer neuen Einheit oder Erweiterung einer vorhandenen Einheit.

### <a name="providing-a-copy-of-customer-data"></a>Bereitstellen einer Kopie der Kundendaten

Kundendaten in ***Dynamics 365 for Customer Engagement*** können mit den umfangreichen Exportfunktionen exportiert werden. Kundendaten können in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit zu erleichtern. Mit Excel können Sie dann die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern.

Zusätzlich wird für Dynamics 365 for Marketing eine [ dedizierte API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) bereitgestellt, die es dem Kunden ermöglicht, Erweiterungen zu erstellen, die zusätzliche Aufzeichnungen über erfasste Kundeninteraktionen, die personenbezogene Daten enthalten können, abrufen. Die API lädt alle relevanten Informationen aus dem Back-End-System und fasst sie zu einem einzigen, portablen Dokument zusammen.

***Dynamics 365 Customer Service Insights*** ermöglicht es Ihnen, mithilfe von Datenexporten [eine Kopie der Kundendaten bereitzustellen](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export).

Kundendaten in ***Dynamics 365 for Finance and Operations*** können mithilfe der umfassenden Exportfunktionen für Entitäten exportiert werden. Unter Verwendung von [*Datenverwaltungs- und Integrationsentitäten*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity) kann der Mandantenadministrator bereitgestellte Entitäten verwenden, neue Entitäten erstellen oder bestehende Entitäten für einen wiederholbaren Export personenbezogener Daten nach Excel oder einer Reihe anderer gängiger Formate unter Verwendung von [*Datenimport- und -exportaufträgen*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job) erweitern.  Alternativ können viele Listen in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit zu erleichtern. Werden Kundendaten nach Excel exportiert, können Sie die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und die Datei dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Sie können auch den *Personensuchbericht* verwenden, um der betroffenen Person Daten zur Verfügung zu stellen, die Sie als personenbezogene Daten klassifiziert haben.

In ***Dynamics 365 Business Central*** können Sie zwei Funktionen nutzen, um eine Kopie der Kundendaten an eine betroffene Person zu übermitteln:

Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/de-DE/dynamics365/business-central/about-export-data).

In ***Dynamics 365 for Talent*** können Sie [Den Personensuchbericht erweitern](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report), um Informationen zur Unterstützung eines Antrags auf eine Kopie der personenbezogenen Daten der betroffenen Person zu sammeln.

### <a name="rectifying-customer-data"></a>Berichtigen von Kundendaten

***Dynamics 365 for Customer Engagement*** gibt Ihnen folgende Möglichkeiten, ungenaue oder unvollständige Kundendaten zu korrigieren oder Kundendaten zu löschen:

- Suchen Sie nach Kundendaten mit den unter „Kundendaten finden“ genannten Möglichkeiten und bearbeiten Sie die Daten direkt in Kundenbindungsformularen. Änderungen können auf einer einzigen Zeilenebene oder direkt in mehreren Zeilen vorgenommen werden.
- Für die Massenverarbeitung mehrerer Customer Engagement-Berichte können Sie das Microsoft Office Add-In verwenden, um Daten nach Microsoft Excel zu exportieren, Ihre Änderungen vorzunehmen und die geänderten Daten aus Excel in Dynamics 365 for Customer Engagement zu importieren.

Darüber hinaus können Sie mit Dynamics 365 for Marketing auch:

- Aktualisieren meiner Datenzielseite, indem Sie einzelne oder mehrere Zeilen direkt bearbeiten
- Vorbereiten einer [Abonnementcenter](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center)-Seite, die so viele editierbare Kontaktfelder wie möglich enthält. Dies ermöglicht einem Endbenutzer, seine eigenen Informationen so weit wie möglich zu aktualisieren.

***Dynamics 365 Customer Service Insights*** bietet auch Funktionen, mit denen Organisationen [Kundendaten korrigieren oder ändern](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary#a=note-about-requests-to-rectify-personal-data) können.

In ***Dynamics 365 for Finance and Operations*** können Sie auch [*Anpassungstools*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) verwenden, aber die Entscheidung und Umsetzung liegt in Ihrer Verantwortung.

***Dynamics 365 Business Central*** bietet zwei Möglichkeiten, ungenaue oder unvollständige Kundendaten zu korrigieren.

Um mehrere Business Central-Datensätze schnell in großen Mengen zu bearbeiten, können Sie Listen mit dem [Business Central Excel-Add-In](https://docs.microsoft.com/de-DE/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) nach Excel exportieren, um mehrere Datensätze zu korrigieren, und dann die geänderten Daten aus Excel in Business Central veröffentlichen. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/de-DE/dynamics365/business-central/about-export-data).

Sie können Kundendaten, die in einem beliebigen Feld gespeichert sind, z. B. Informationen über einen Kunden in der Kundenkarte, ändern, indem Sie das Datenelement, das die betroffenen personenbezogenen Daten enthält, manuell bearbeiten. Für Details siehe [Eingabe von Daten](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Kurzer Hinweis zum Ändern von Einträgen in geschäftlichen Transaktionen

Für die Integrität eines Ressourcen-Planungssystems eines Unternehmens sind Transaktionsdatensätze, wie z. B. allgemeine Buchungen, Debitorenbuchungen und Steuerbuchungen, unerlässlich. Personenbezogene Daten, die Teil einer finanziellen oder anderen Transaktion sind, werden im Ist-Zustand für die Einhaltung von Finanzgesetzen (z. B. Steuergesetze), die Verhinderung von Betrug (z. B. Security Audit Trail) oder die Einhaltung von Branchenzertifizierungen aufbewahrt. Daher beschränken Dynamics 365 for Finance and Operations und Dynamics 365 Business Central das Ändern von Daten in solchen Datensätzen.

Wenn Sie personenbezogene Daten in Geschäftsdatensätzen speichern, besteht die einzige Möglichkeit, die Verarbeitung personenbezogener Daten zu korrigieren, zu löschen oder einzuschränken, um dem Antrag einer betroffenen Person nachzukommen, darin, die Anpassungsfähigkeiten von Dynamics 365 Business Central [ zu nutzen](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). [](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)Die Entscheidung, einen Antrag einer betroffenen Person auf Änderung zu berücksichtigen sowie dessen Umsetzung liegt in Ihrer Verantwortung.

### <a name="restricting-the-processing-of-customer-data"></a>Einschränken der Verarbeitung von Kundendaten

Wenn Sie einen Antrag einer betroffenen Person auf Einschränkung der Verarbeitung von Kundendaten erhalten, können Sie die betroffenen Kundendaten einfach aus dem Onlinedienst extrahieren und in einem separaten Container (d. h. Vor-Ort-Speicherung oder separater Webdienst mit Datenisolierung) speichern, der von den Verarbeitungsfunktionen einer beliebigen Cloud-Anwendung isoliert ist.

Alternative Mechanismen wie z. B. Datenverarbeitungsblocks werden von ***Dynamics 365 Business Central*** angeboten, wo den Benutzern die Möglichkeit geboten wird, bestimmte Datensätze zu blockieren. Einzelheiten finden Sie unter [Einschränken der Datumsverarbeitung für eine betroffene Person](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Wenn ein Datensatz als gesperrt markiert ist, stellt Dynamics 365 Business Central die Verarbeitung der Kundendaten der betroffenen Person ein. Sie können keine neuen Transaktionen anlegen, die einen gesperrten Datensatz verwenden; z. B. können Sie keine neue Rechnung für einen Kunden erstellen, wenn entweder der Kunde oder der Verkäufer gesperrt ist.

### <a name="deleting-customer-data"></a>Löschen von Kundendaten

Wenn eine betroffene Person Sie auffordert, ihre Kundendaten zu löschen, gibt es mehrere Möglichkeiten, dies zu tun:

- Für die Massenverarbeitung mehrerer Dynamics 365-Berichte können Sie das Microsoft Office Add-In verwenden, um Daten nach Microsoft Excel zu exportieren, Ihre Änderungen vorzunehmen und die geänderten Daten aus Excel in den Onlinedienst zu importieren.
- Sie können Kundendaten, die in einem beliebigen Feld gespeichert sind, löschen, indem Sie die zu löschenden Daten suchen und dann das Datenelement, das die Zielkundendaten enthält, manuell löschen, z. B. durch ein endgültiges Löschen des Kontaktdatensatzes, der die betroffene Person repräsentiert, und anderer Datensätze, die personenbezogene Daten enthalten.

Zusätzlich wird bei Dynamics 365 Marketing durch die Löschung eines Kontaktes sichergestellt, dass auch Interaktionsdaten mit personenbezogenen Daten entfernt werden. Für alle benutzerdefinierten Felder oder Entitäten müssen Sie Ihr System so anpassen, dass es alle Kundendaten aus Bezugsdatensätzen löscht und/oder sie aus dem Kontaktdatensatz entfernt, sodass alle personenbezogenen Daten entfernt werden. Weitere Informationen: [Entwicklerhandbuch (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** bietet Unternehmen auch die Möglichkeit, [Kundendaten zu löschen](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Alternativ können Sie in ***Dynamics 365 for Finance and Operations*** auch [*Anpassungstools*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) verwenden, um Kundendaten zu löschen/ändern.

Wenn eine betroffene Person Sie auffordert, seine/ihre personenbezogenen Daten zu löschen, die in Ihren Kundendaten enthalten sind, gibt es in ***Dynamics 365 Business Central*** mehrere Möglichkeiten, diese Anforderung zu erfüllen:

- Um mehrere Business Central-Datensätze schnell in großen Mengen zu bearbeiten, können Sie Daten mit dem [Business Central Excel-Add-In](https://docs.microsoft.com/de-DE/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) nach Excel exportieren, um mehrere Datensätze zu löschen, und dann die Änderungen aus Excel in Business Central veröffentlichen. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/de-DE/dynamics365/business-central/about-export-data).
- Sie können in jedem Feld gespeicherte Kundendaten löschen, indem Sie das Datenelement, das die Zielkundendaten enthält, manuell löschen. Für Details siehe [Eingabe von Daten](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Sie können Kundendaten direkt löschen, indem Sie z. B. einen Kontakt löschen und anschließend den Batchauftrag Stornierte Aktivitätsprotokollposten löschen ausführen, um Interaktionen für diesen Kontakt zu löschen.
- Sie können [Dokumente löschen](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents), die Kundendaten enthalten, z. B. Notizen und gebuchte Verkaufs- und Eingangsrechnungen.

Neben der Massen- oder Einzellöschung diskreter Datensätze ist zu beachten, dass nur gekündigte Mitarbeiter aus ***Dynamics 365 for Talent*** vollständig gelöscht werden können. [Folgen Sie diesen Schritten, um gekündigte Mitarbeiter](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data) zu löschen.

### <a name="exporting-customer-data"></a>Exportieren von Kundendaten

Als Reaktion auf einen Antrag auf Datenübertragbarkeit können Kundendaten in ***Dynamics 365 for Customer Engagement*** mit den umfangreichen Exportfunktionen exportiert werden. Kundendaten können in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit zu erleichtern. Mit Excel können Sie dann die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern.

Zusätzlich wird für Dynamics 365 for Marketing eine [ dedizierte API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) bereitgestellt, die es dem Kunden ermöglicht, Erweiterungen zu erstellen, die zusätzliche Aufzeichnungen über erfasste Kundeninteraktionen, die personenbezogene Daten enthalten können, abrufen. Die API lädt alle relevanten Informationen aus dem Back-End-System und fasst sie zu einem einzigen, portablen Dokument zusammen.

Für ***Dynamics 365 Customer Service Insights*** können Sie zum [Exportieren von Kundendaten](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) das Azure-Verwaltungsportal verwenden.

***Dynamics 365 for Finance and Operations*** bietet [Datenverwaltungs- und Integrationsentitäten](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), mit denen bereitgestellte Entitäten verwendet, neue Entitäten erstellt oder bestehende Entitäten für einen wiederholbaren Export personenbezogener Daten nach Excel oder einer Reihe anderer gängiger Formate unter Verwendung von [Datenimport- und -exportaufträgen](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job) erweitert werden können.  Alternativ können viele Listen in eine statische Excel-Datei exportiert werden, um einen Antrag auf Datenübertragbarkeit zu erleichtern. Werden Kundendaten auf diese Weise nach Excel exportiert, können Sie die personenbezogenen Daten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und die Datei dann in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern.

Sowohl Dynamics 365 for Finance and Operations als auch ***Dynamics 365 for Talent*** bieten einen Personensuchbericht an, um die betroffene Person mit Daten zu versorgen, die Sie als personenbezogene Daten klassifiziert haben. 

***Dynamics 365 Business Central*** bietet die folgenden Funktionen:

- Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/dynamics-nav-app/about-export-data).
- Sie können Kundendaten in eine Excel-Datei exportieren. In Excel können Sie dann die Kundendaten, die in den Antrag auf Datenübertragbarkeit aufgenommen werden sollen, bearbeiten und in einem gängigen, maschinenlesbaren Format, wie z. B. CSV oder XML, speichern. Weitere Informationen finden Sie unter [Exportieren Ihrer Geschäftsdaten nach Excel](https://docs.microsoft.com/de-DE/dynamics365/business-central/about-export-data).

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

Da Microsoft Social Engagement personenbezogene Daten verarbeitet, die in Kundendaten und sozialen Inhalten zu finden sind, bietet diese Anwendung eine einzigartige Möglichkeit, DSR in Bezug auf personenbezogene Daten aus sozialen Netzwerken zu beantworten. Soziale Inhalte sind öffentlich zugängliche Inhalte, die aus sozialen Medien (wie Twitter, Facebook und YouTube) und Datenindizierungs- oder Datenaggregationsdiensten als Antwort auf Suchanfragen des Kunden in Microsoft Social Engagement gesammelt werden. Soziale Inhalte sind keine Kundendaten. Weitere Einschränkungen bei der Verarbeitung, Nutzung und Speicherung von sozialen Inhalten sind in den Onlinedienstbedingungen von Microsoft beschrieben.

### <a name="finding-personal-data"></a>Suchen nach personenbezogenen Daten

Der erste Schritt der Reaktion auf einen Antrag einer betroffenen Person besteht darin, die personenbezogenen Daten, die Gegenstand dieses Antrags sind, zu suchen und zu identifizieren. Microsoft Social Engagement speichert folgende Daten:

#### <a name="for-social-media-users"></a>Für Benutzer von sozialen Medien

- Daten von Benutzern sozialer Medien (in Social Engagement als *Autor* bezeichnet), die Social Engagement von sozialen Plattformen erhält. Es könnte den Namen, den Benutzernamen, das Profilbild, den Standort, die Website und die Biografie enthalten, wenn dies vom Autor bereitgestellt wird.
- Autoren-Tags, die verwendet werden, um Autoren zu gruppieren und zu klassifizieren – zum Beispiel als Influencer, Konkurrenten oder Fans.

#### <a name="for-employees"></a>Für Mitarbeiter

- Benutzerprofile, die Mitarbeiternamen, Kontaktinformationen und Profilbilder enthalten und in Office 365 verwaltet werden.
- E-Mail-Adressen von Mitarbeitern, die Post-Benachrichtigungen und Trend-Benachrichtigungen erstellt haben.
- Konten in sozialen Medien (in Social  Engagement als *soziale Profile* bezeichnet), die in Social  Engagement von Mitarbeitern authentifiziert werden, um sich mit anderen auf einer sozialen Plattform zu engagieren. Sie können sich im Besitz eines Mitarbeiters oder des Unternehmens befinden und beinhalten Daten, die Mitarbeiter bei der Registrierung eines Kontos auf einer sozialen Plattform angeben. Diese Profile repräsentieren die das Unternehmen in sozialen Medien und werden verwendet, um mit Beiträgen im Namen des Unternehmens in der Social  Engagement-Anwendung zu interagieren.
- Benutzernamen in Power BI, wenn Ihre Organisation das [Social Engagement Content Pack](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) für Power BI verwendet, um die Teamleistung on sozialen Medien zu analysieren.

Dieser erste Schritt – Suchen und Überprüfen der persönlichen Daten – ist hilfreich, um festzustellen, ob ein Antrag einer betroffenen Person die Anforderungen Ihrer Organisation für die Anerkennung oder Ablehnung eines Antrags erfüllt. So könnten Sie beispielsweise nach dem Suchen und Überprüfen der persönlichen Daten bestimmen, dass die Anforderung nicht den Anforderungen Ihrer Organisation entspricht, da sie sich auf die Rechte und Freiheiten anderer auswirken kann.

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

- Um ihre personenbezogene Daten zu finden, folgen Sie den ersten vier Schritten in [Autor finden und löschen](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author).
- Mitarbeiter können Regeln in Social Engagement erstellen, die auf sozialen Plattformen nach bestimmten definierten Inhalten suchen; diese Suchregeln können Autorennamen enthalten. Um sicherzustellen, dass Sie diese Regeln finden, überprüfen Sie die Regeln für die Suche nach sozialen Konten für das entsprechende Konto wie [Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule), [Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule) und [YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule).
- Um Autoren-Tags für einen Autor zu suchen, [filtern Sie zuerst die Beiträge](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter) nach [Autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors) und dann zeigen Sie [Autor-Tags](https://go.microsoft.com/fwlink/?linkid=864795) an.

##### <a name="your-employees"></a>Ihre Mitarbeiter

Suche nach:

- Einem Benutzerprofil: Gehen Sie zum [Office 365 Admin Center](https://portal.office.com/adminportal/home). Wählen Sie im **Admin Center** die Option **Benutzer** aus. Suchen Sie auf der Seite **Aktive Benutzer** nach dem Benutzer in der Liste. Social Engagement: Gehen Sie zu **Einstellungen\>, Benutzerverwaltung**, um Informationen anzuzeigen, die von Office 365 automatisch synchronisiert werden.
- Der Empfänger einer Benachrichtigung: Folgen Sie den ersten beiden Schritten aus [Benachrichtigungsempfänger als Administrator verwalten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).
- Daten sozialer Profile, die von Mitarbeitern eingegeben wurden: Gehen Sie zu **Einstellungen \>, Soziale Profile**. (Weitere Informationen finden Sie unter [Soziale Profile verwalten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles).
- Benutzernamen in Power BI: Öffnen Sie das Social Engagement Power BI-Dashboard und filtern Sie nach dem Mitarbeiternamen.

### <a name="providing-a-copy-of-personal-data"></a>Bereitstellen einer Kopie der personenbezogenen Daten

Die DSGVO gibt den betroffenen Personen das Recht, einen Antrag auf eine Kopie ihrer personenbezogenen Daten zu stellen. Nachdem Sie Kundeninhalte gefunden haben, die Daten enthalten, die möglicherweise mit diesem Antrag zusammenhängen, liegt es an Ihnen und Ihrem Unternehmen, zu entscheiden, ob Sie der betroffenen Person eine Kopie zur Verfügung stellen.

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

- Zum Exportieren personenbezogener Daten von Autoren, führen Sie die Schritte in [Autoreninformationen exportieren](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) aus, um die Daten in eine Excel-Datei zu exportieren.
- Um die Autoren-Tags zu extrahieren, die einem bestimmten Autor hinzugefügt wurden, können Sie [Autoren-Tag-Daten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data) exportieren.

##### <a name="your-employees"></a>Ihre Mitarbeiter

Um zu exportieren:

- Kundendaten aus Benutzerprofilen: Navigieren Sie zum [Office 365 Admin Center](https://portal.office.com/adminportal/home). Wählen Sie im **Admin Center** die Option **Benutzer** aus. Suchen Sie auf der Seite **Aktive Benutzer** nach dem Benutzer, dessen Daten Sie exportieren möchten. Löschen Sie alle Benutzer außer dem Zielbenutzer, und wählen Sie dann **Exportieren** aus, um die Daten in eine CSV-Datei zu exportieren, in der Sie die Informationen mit Excel anzeigen können.
- E-Mail-Adressen eines Benachrichtigungsempfängers (die einzigen Kundendaten in einer Benachrichtigung). Folgen Sie den Schritten in [Verwalten von Benachrichtigungsempfängern als Administrator](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Wählen Sie dann **Exportieren** aus, um eine Excel-Liste der Benachrichtigungen herunterzuladen, die diesen Empfänger enthalten.
- Benutzernamen aus Power BI: [Engagement-Berichte](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) zeigen Benutzernamen in Berichten zur Teamleistung in sozialen Medien. Um diese Daten zu exportieren, filtern Sie nach dem Benutzer im PowerBI-Dashboard oder [Bericht](https://docs.microsoft.com/power-bi/power-bi-report-add-filter), und [exportieren Sie die Daten](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

### <a name="rectifying-personal-data"></a>Berichtigen von personenbezogenen Daten

Um ungenaue oder unvollständige personenbezogene Daten zu berichtigen:

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

- Sie müssen den Datenbesitzer (Autor) bitten, die Änderung auf der sozialen Plattform (z. B. Twitter, WordPress oder Tumblr) vorzunehmen. Die betroffene Person besitzt die Daten im Konto des sozialen Netzwerks, so dass er/sie sie als einzige/r ändern kann. Sobald der Autor die Änderung vornimmt, synchronisiert Social Engagement die überarbeiteten Informationen automatisch.
- Autoren-Tags: Folgen Sie den Schritten in [Autoren-Tags ändern](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags).

##### <a name="your-employees"></a>Ihre Mitarbeiter

- Benutzerprofile: Um Änderungen an den Kundendaten in einem Benutzerprofil vorzunehmen, siehe [Benutzername und E-Mail-Adresse in Office 365](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297) und [Fügen Sie Ihr Profilbild zu Office 365](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7) hinzu. Diese Änderungen werden automatisch im sozialen Engagement synchronisiert. Um Sie zu finden, wechseln Sie zu **Einstellungen** \> **Benutzerverwaltung**.

- Benachrichtigungsempfänger: Sie können [eine Benachrichtigung ändern](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert).

### <a name="restricting-the-processing-of-personal-data"></a>Einschränken der Verarbeitung von personenbezogenen Daten

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

Um die Verarbeitung der Kundendaten von Autoren in Social Engagement zu beenden, [löschen Sie den Autor](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).

Hierdurch wird die zukünftige Verarbeitung der Daten dieser betroffenen Person und etwaiger künftiger Beiträge sowie die Löschung aller Daten über und durch diesen Autor verhindert. Wenn Social Engagement neue Beiträge erhält, prüft es automatisch, ob der Autor früher gelöscht wurde und verwirft Beiträge von gelöschten Autoren. Dies hat keine Auswirkungen auf das Benutzerkonto auf der sozialen Plattform.

##### <a name="your-employees"></a>Ihre Mitarbeiter

- Um die Verarbeitung der Kundendaten von Mitarbeitern zu beenden, können Sie [ihre Lizenz in Office 365 entfernen](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1). Dadurch werden alle für Social Engagement relevanten Elemente wie Benutzerrollen und -profile, alle zugehörigen benutzerdefinierten Einstellungen, Benachrichtigungen, Aktivitätszuordnungen und Datenströme gelöscht. Suchbegriffe und soziale Profile werden nicht gelöscht. (Die sozialen Profile der gelöschten Benutzer werden auf Administratoren übertragen und können auf Anforderung gelöscht werden).
- Um das Senden von Benachrichtigungs-E-Mail-Nachrichten einzuschränken, können Sie eine E-Mail-Adresse aus allen Benachrichtigungen entfernen, zu denen sie hinzugefügt wurde, indem Sie die Schritte in [Benachrichtigungsempfänger als Administrator verwalten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator) ausführen.

### <a name="deleting-personal-data"></a>Löschen von personenbezogenen Daten

Die DSGVO gibt den betroffenen Personen das Recht, vom für die Verarbeitung Verantwortlichen unter bestimmten Umständen die Löschung personenbezogener Daten zu verlangen. Das „Recht auf Vergessenwerden“ durch Löschen solcher Daten durch ein Unternehmen ist ein wesentlicher Schutzmechanismus der DSGVO.

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

Um alle personenbezogenen Daten eines Autors in Social Engagement dauerhaft zu löschen, löschen Sie das komplette soziale Profil dieses Autors. Siehe [](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors)[Löschen eines Autors](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).  

Dieser Vorgang kann nicht rückgängig gemacht werden. Alle Daten über und vom Autor in  Social Engagement werden gelöscht und die zukünftige Verarbeitung der Daten sowie zukünftige Posts werden verhindert. Wenn Social Engagement neue Beiträge erhält, prüft es automatisch, ob der Autor früher gelöscht wurde und verwirft Beiträge von gelöschten Autoren. Dies hat keine Auswirkungen auf das Benutzerkonto auf der sozialen Plattform.

Um Autoren-Tags zu löschen, lesen Sie [Autoren-Tags löschen](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags).

>[!NOTE]
>Wenn Sie aufgefordert werden, Informationen zu einem bestimmten Autor zu entfernen, empfehlen wir Ihnen, zuerst die Identität des Autors zu bestätigen, um die Anforderung zu überprüfen. Um seine Identität zu überprüfen, können Sie eine private Nachricht vom Autor von seinem Social Media-Konto anfordern.

Social Engagement hat Compliance-Feeds von verschiedenen sozialen Plattformen (wie Twitter, WordPress, Tumblr) implementiert, um auf Signale wie Löschungen von Posts zu reagieren, die direkt auf den sozialen Plattformen ausgelöst wurden. Diese Funktion wird automatisch bei jeder Installation von Social-Engagement aktiviert und erfordert keine Maßnahmen seitens des Benutzers. Zusätzlich bietet Social Engagement eine Funktion, mit der Dienste (wie Dynamics 365 for Customer Engagement), die auf sozialen Inhalten von Social Engagement aufbauen, diese Signale übernehmen können.

##### <a name="your-employees"></a>Ihre Mitarbeiter

Um alle Kundendaten eines Mitarbeiters dauerhaft zu löschen, können Sie [dessen Lizenz in Office 365 entfernen](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1).

- Dadurch werden alle für Social Engagement relevanten Elemente wie Benutzerrollen und -profile, alle zugehörigen benutzerdefinierten Einstellungen, Benachrichtigungen, Aktivitätszuordnungen und Datenströme gelöscht. Suchbegriffe und soziale Profile werden nicht gelöscht. (Die sozialen Profile der gelöschten Benutzer werden auf Administratoren übertragen und können auf Anforderung gelöscht werden).
- Diese Änderungen werden automatisch mit Social Engagement synchronisiert. Sie finden sie unter **Einstellungen \> Benutzerverwaltung**.
- Die Einträge zu einem Mitarbeiter in einem PowerBI-Bericht werden anonymisiert, wenn die personenbezogenen Daten dieses Mitarbeiters gelöscht werden.

Sie können [ein soziales Profil löschen](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile).

Um eine E-Mail-Adresse von allen Benachrichtigungen auszuschließen, zu denen sie hinzugefügt wurde, folgen Sie den Schritten unter [Benachrichtigungsempfänger als Administrator verwalten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>Exportieren von personenbezogenen Daten

Sie können betroffenen Personen ihre Daten in einem elektronischen Format zur Verfügung stellen.

#### <a name="social-media-users-authors"></a>Für Benutzer von sozialen Medien (Autoren)

Zum Exportieren personenbezogener Daten von Autoren, führen Sie die Schritte in [Autoreninformationen exportieren](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) aus, um die Daten in eine Excel-Datei zu exportieren.

Um die Autoren-Tags zu extrahieren, die einem bestimmten Autor hinzugefügt wurden, können Sie [Autoren-Tag-Daten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data) exportieren.

##### <a name="your-employees"></a>Ihre Mitarbeiter

Um zu exportieren:

- Kundendaten aus Benutzerprofilen: Navigieren Sie zum [Office 365 Admin Center](https://portal.office.com/adminportal/home). Wählen Sie im **Admin Center** die Option **Benutzer** aus. Suchen Sie auf der Seite **Aktive Benutzer** nach dem Benutzer, dessen Daten Sie exportieren möchten. Löschen Sie alle Benutzer außer dem Zielbenutzer, und wählen Sie dann **Exportieren** aus, um die Daten in eine CSV-Datei zu exportieren, in der Sie die Informationen mit Excel anzeigen können.
- E-Mail-Adressen eines Benachrichtigungsempfängers (die einzigen personenbezogenen Daten in einer Benachrichtigung). folgen Sie den Schritten in [Benachrichtungsempfänger als Administrator verwalten](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Wählen Sie dann **Export**, um eine Excel-Liste der Benachrichtigungen herunterzuladen, die diesen Empfänger enthalten.
- Benutzernamen aus Power BI: [Engagement-Berichte](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) zeigen Benutzernamen in Berichten zur Teamleistung in sozialen Medien. Um diese Daten zu exportieren, filtern Sie nach dem Benutzer im PowerBI-Dashboard oder [Bericht](https://docs.microsoft.com/power-bi/power-bi-report-add-filter), und [exportieren Sie die Daten](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Teil 2: Reagieren auf Anträge betroffener Personen für vom System generierte Protokolle

Microsoft bietet Ihnen außerdem die Möglichkeit, auf vom System erzeugte Protokolle zuzugreifen, sie zu exportieren und zu löschen, die nach der weit gefassten Definition der DSGVO als „personenbezogene Daten“ gelten können. Beispiele für vom System generierte Protokolle, die unter der DSGVO als personenbezogen angesehen werden können:

- Daten zu Produkt- und Dienst-Nutzung, z. B. Aktivitätsprotokolle
- Suchanfragen und Abfragedaten von Benutzern
- Daten, die durch Produkte und Dienste als Produkt der Systemfunktionalität und Interaktion von Benutzern oder anderen Systemen erzeugt werden

Beachten Sie, dass die Möglichkeit, Daten in vom System generierten Protokollen einzuschränken oder zu korrigieren, nicht unterstützt wird. Daten in vom System generierten Protokollen geben auf Fakten basierende Aktionen innerhalb der Microsoft-Cloud und Diagnosedaten wieder, und Änderungen an diesen Daten würden den historischen Datensatz von Aktionen kompromittieren und das Betrugs- und Sicherheitsrisiko erhöhen.

### <a name="accessing-and-exporting-system-generated-logs"></a>Zugreifen auf und Exportieren von vom System generierte(n) Protokolle(n)

Administratoren können auf vom System generierte Protokolle zugreifen, die mit der Nutzung von Dynamics 365-Diensten und -Anwendungen durch einen bestimmten Benutzer verbunden sind. Um auf vom System generierte Protokolle zuzugreifen und sie zu exportieren:

1. Gehen Sie zum [Microsoft Service Trust-Portal](https://servicetrust.microsoft.com/) und melden Sie sich mit den Anmeldeinformationen des globalen Dynamics 365-Administrators an.
2. In der **Datenschutz**-Dropdownliste klicken Sie am oberen Rand der Seite auf **Antrag einer betroffenen Person**.
3. Auf der Seite **Antrag einer betroffenen Person** unter **vom System generierte Protokolle** klicken Sie auf **Datenprotokollexport**.
    > [!NOTE]
    > Der **Datenprotokollexport** wird angezeigt. Beachten Sie, dass eine Liste der von Ihrer Organisation übermittelten Datenexportanfragen angezeigt wird.
4. Wenn Sie eine neue Anforderung für einen Benutzer erstellen möchten, klicken Sie auf **Anforderung zum Exportieren von Daten erstellen**.

Nachdem Sie eine neue Anforderung erstellt haben, wird sie auf der Seite **Datenprotokollexport** aufgelistet, wo Sie ihren Status nachverfolgen können. Nachdem eine Anforderung abgeschlossen ist, können Sie auf einen Link klicken, um auf die vom System generierten Protokolle zuzugreifen, die innerhalb von 30 Tagen nach Erstellung der Anforderung in den Azure-Speicherort Ihrer Organisation exportiert werden. Die Daten werden in gängigen, maschinenlesbaren Dateiformaten wie JSON oder XML gespeichert. Wenn Sie kein Azure-Konto und keinen Azure-Speicherort haben, müssen Sie ein Azure-Konto und/oder einen Azure-Speicherort für Ihre Organisation erstellen, damit das Datenprotokollexport-Tool die vom System generierten Protokolle exportieren kann.

Azure unterstützt dies, indem es Ihrer Organisation ermöglicht, die Daten im nativen JSON-Format in den angegebenen Container im Azure-Speicher zu exportieren. Artikel [Einführung in Microsoft Azure Storage – Blob-Speicher](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).

> [!IMPORTANT]
> Sie müssen ein Mandantenadministrator sein, um Benutzerdaten aus dem Mandanten exportieren können.

Die folgende Tabelle fasst den Zugriff auf und den Export von vom System generierten Protokollen zusammen:

| | |
|:----|:---|
| | |
|**Wie lange benötigt das Tool für den Datenprotokollexport von Microsoft, um eine Anforderung abzuschließen?**| Dies hängt von mehreren Faktoren ab. In den meisten Fällen sollte der Abschluss in einem oder zwei Tagen möglich sein, es kann jedoch auch bis zu 30 Tage dauern. |
|**Welches Format weist die Ausgabe auf?**| Die Ausgabe ist in maschinenlesbaren Dateien, z. B. XML, CSV oder JSON, strukturiert. |
|**Welche Daten werden durch das Tool für den Datenprotokollexport ausgegeben?**| Das Tool für den Datenprotokollexport gibt vom System generierte Protokolle aus, die Microsoft speichert. Die exportierten Daten umfassen mehrere Microsoft-Dienste, einschließlich Office 365, Azure und Dynamics. |
|***Wer hat Zugriff auf das Tool für den Datenprotokollexport und kann Zugriffsanforderungen für vom System generierte Protokolle senden?**| Globale Administratoren von Dynamics 365  haben Zugriff auf das DSGVO-Hilfsprogramm zur Verwaltung von Protokollen. |
|**Wie werden Daten an den Benutzer zurückgegeben?**| Die Daten werden an den Azure-Speicherort Ihrer Organisation exportiert; es ist Sache der Administratoren in Ihrer Organisation, zu bestimmen, wie sie diese Daten den Benutzern anzeigen/bereitstellen. |
|**Wie werden Daten in vom System generierten Protokollen dargestellt?**| Beispiel für ein vom System generiertes Protokoll im JSON-Format: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

> [!NOTE]
> Bei einigen Features ist das Exportieren oder Löschen personenbezogener Daten nicht möglich, um die Integrität derartiger Informationen aus Sicherheits- und Überwachungsgründen zu schützen.

### <a name="deleting-system-generated-logs"></a>Löschen von vom System generierten Protokollen

Um vom System generierte Protokolle zu löschen, die über eine Zugriffsanforderung abgerufen werden, müssen Sie den Benutzer aus dem Dienst entfernen und sein Azure Active Directory-Konto dauerhaft löschen. Anweisungen zum dauerhaften Löschen eines Benutzers finden Sie im Abschnitt [Löschen eines Benutzers](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user) in diesem Handbuch. Es ist wichtig zu beachten, dass das dauerhafte Löschen eines Benutzerkontos nach dem Start unwiderruflich ist.

Durch dauerhaftes Löschen eines Benutzerkontos werden die Daten des Benutzers innerhalb von 30 Tagen aus vom System generierten Protokollen für fast alle Dynamics 365-Dienste entfernt.

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/en-us/TrustCenter/Privacy/gdpr/default.aspx)
