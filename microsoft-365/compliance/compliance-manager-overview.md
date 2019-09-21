---
title: Übersicht über den Microsoft Compliance-Manager
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: c88b45fb568b0fe29bc967676ea09e89e9084a62
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081030"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft Compliance-Manager (Vorschau)

> [!IMPORTANT]
> Der Compliance-Manager ist nicht in Office 365, betrieben von 21Vianet, Office 365 Deutschland, Office 365 US Government Community High (GCC) High oder Office 365 Department of Defense verfügbar.

[Microsoft Compliance Manager (Preview)](https://servicetrust.microsoft.com/ComplianceManager) ist ein kostenloses Workflow basiertes Risiko Bewertungstool, mit dem Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services verfolgen, zuweisen und überprüfen können. Als Teil Ihres Microsoft 365-, Office 365-oder Azure Active Directory-Abonnements unterstützt Compliance Manager das Verwalten von behördlichen Vorschriften im Rahmen des Modells für die gemeinsame Verantwortung für Microsoft Cloud Services. Compliance-Manager bietet ein zentralisiertes Dashboard zum Anzeigen von Standards, Regeln und Steuerungs Implementierungsdetails sowie Testergebnisse für Microsoft-Dienst Bewertungen. Es enthält auch Tools, mit denen Sie benutzerdefinierte Steuerelement Implementierungen und die für Ihre Organisation spezifische Konformitäts Verfolgung verwalten können.

Mit dem Compliance-Manager kann Ihre Organisation:
  
- Kombinieren detaillierter Compliance-Informationen von Microsoft für Auditoren und Regulatoren zu seinen Cloud-Diensten mit Ihrer Compliance-Selbsteinschätzung für Standards und Vorschriften, die für Ihre Organisation gelten. Dazu gehören Normen und Verordnungen, die von der internationalen Organisation für Normung (ISO), dem National Institute of Standards and Technology (NIST), der Krankenversicherung Portabilität und dem Rechenschaftspflicht Gesetz (HIPAA), den allgemeinen Daten beschrieben werden. Protection Regulation (dsgvo) und viele andere.
- Ermöglicht Ihnen, Compliance-und bewertungsbezogene Aktivitäten zuzuweisen, nachzuverfolgen und zu erfassen, mit deren Hilfe Ihre Organisation Team Barrieren überwinden kann, um Ihre Compliance-Ziele zu erreichen.
- Stellen Sie eine Konformitätsbewertung zur Verfügung, damit Sie Ihren Fortschritt nachverfolgen und Überwachungssteuerelemente priorisieren können, mit denen die Gefährdung Ihrer Organisation reduziert wird.
- Stellen Sie ein sicheres Repository bereit, mit dem Sie Beweise und andere Artefakte im Zusammenhang mit ihren Compliance-Aktivitäten hochladen und verwalten können.
- Erstellen Sie ausführliche Microsoft Excel Berichte, in denen Compliance-Aktivitäten dokumentiert werden, die von Microsoft und Ihrer Organisation für Auditoren, Regulatoren und andere Konformitäts Prüfer ausgeführt wurden.

> [!NOTE]
> Die im Compliance-Manager bereitgestellten Kundenaktionen sind Empfehlungen; Es liegt in Ihrer Organisation, die Wirksamkeit dieser Empfehlungen in ihrem jeweiligen regulatorischen Umfeld vor der Implementierung zu bewerten. Im Compliance-Manager gefundene Empfehlungen sollten nicht als Garantie für die Compliance interpretiert werden.

## <a name="compliance-manager-relationships"></a>Compliance-Manager-Beziehungen

Compliance-Manager verwendet mehrere Komponenten, die Sie bei ihren Compliance-Verwaltungsaktivitäten unterstützen. Diese Komponenten arbeiten zusammen, um einen vollständigen Verwaltungs Workflow und problemlose Kompatibilitätsberichte für Auditoren bereitzustellen.

Das Diagramm zeigt die Beziehungen zwischen den primären Komponenten von Compliance-Manager:

![Beziehungen in Compliance-Manager, Version 3](media/compliance-manager-relationships.png)

## <a name="groups"></a>Gruppen

[Gruppen](working-with-compliance-manager.md#groups) sind Container, die es Ihnen ermöglichen, Bewertungen zu organisieren und allgemeine Informations-und Workflowaufgaben Zwischenbewertungen mit denselben oder Verwandten, vom Kunden verwalteten Steuerelementen freizugeben. Wenn zwei unterschiedliche Bewertungen in derselben Gruppe das vom Kunden verwaltete Steuerelement gemeinsam nutzen, wird der Abschluss der Implementierungsdetails, des Tests und des Status für das Steuerelement in allen anderen Bewertungen in der Gruppe automatisch mit dem gleichen Steuerelement synchronisiert. Dadurch werden die zugewiesenen Aktionselemente für jedes Steuerelement in der gesamten Gruppe vereinheitlicht und Arbeits Duplikate reduziert. Sie können auch festlegen, dass Gruppen zum Organisieren verwendet werden. Assessments nach Jahr, Bereich, Konformitäts Standard oder anderen Gruppierungen, die Ihnen bei der Organisation Ihrer Compliance-arbeiten helfen.

## <a name="assessments"></a>Bewertungen

Bei [Assessments](working-with-compliance-manager.md#assessments) handelt es sich um Container, mit denen Sie Steuerelemente basierend auf Zuständigkeiten zwischen Microsoft und Ihrer Organisation für die Bewertung der Sicherheits-und Konformitätsrisiken von Cloud-Diensten organisieren können. Mithilfe von Assessments können Sie Datenschutzgarantien implementieren, die durch einen Compliance-Standard und entsprechende Datenschutzstandards, Verordnungen oder Gesetze festgelegt sind. Sie unterstützen Sie beim Erkennen Ihrer Datenschutz-und Compliance-Haltung gegenüber dem ausgewählten Industriestandard für den ausgewählten Microsoft Cloud-Dienst. Die Bewertungen werden durch die Implementierung von Steuerelementen vervollständigt, die in der Bewertung enthalten sind, die einem Zertifizierungsstandard zugeordnet ist.

Standardmäßig erstellt Compliance-Manager die folgenden Bewertungen für Ihre Organisation:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 dsgvo

Die Bewertungen umfassen mehrere Komponenten:
  
- **In-Scope-Dienste**: jede Bewertung gilt für eine bestimmte Gruppe von Microsoft-Diensten.
- Von **Microsoft verwaltete Steuerelemente**: Microsoft implementiert und verwaltet für jeden clouddienst eine Reihe von Konformitätskontrollen für zutreffende Standards und Vorschriften.
- Von **Kunden verwaltete Steuerelemente**: Dies ist die Auflistung von Steuerelementen, die von Ihrer Organisation implementiert werden, wenn Sie Aktionen für jedes Steuerelement ausführen.
- **Bewertungsfaktor**: der Prozentsatz der Gesamtpunktzahl für vom Kunden verwaltete Steuerelemente in der Bewertung. Auf diese Weise können Sie die Implementierung der jedem Steuerelement zugewiesenen Aktionen nachverfolgen.

## <a name="controls"></a>Steuerelemente

[Steuerelemente](working-with-compliance-manager.md#controls-and-actions) sind Compliance-Prozesscontainer im Compliance-Manager, die definieren, wie Compliance-Aktivitäten verwaltet werden. Diese Steuerelemente sind in Steuerelementfamilien organisiert, die mit der Bewertungsstruktur für entsprechende Zertifizierungen oder Verordnungen übereinstimmen.

- **Steuerelement-ID**: der Name des ausgewählten Steuerelements aus der entsprechenden Zertifizierung oder Verordnung.
- **Steuerelement Titel**: der Titel für die Steuerelement-ID aus der entsprechenden Zertifizierung oder Verordnung.
- **Artikel-ID**: Dieses Feld ist nur für dsgvo-Bewertungen und gibt die entsprechende dsgvo-Artikelnummer an.
- **Description**: Text of Control aus der entsprechenden Zertifizierung oder Verordnung. Aufgrund von Copyright-Einschränkungen wird ein Link zu relevanten Informationen für ISO-Standards aufgeführt.

![Steuerelemente in Compliance-Manager Version 3](media/compliance-manager-controls.png)

Es gibt drei Arten von Steuerelementen im Compliance-Manager, von **Microsoft verwaltete Steuer**Elemente, von **Kunden verwalteten**Steuerelementen und von Steuerelementen für **gemeinsame Verwaltung** .

### <a name="microsoft-managed-controls"></a>Von Microsoft verwaltete Steuerelemente

Für jeden clouddienst implementiert und verwaltet Microsoft eine Reihe von Steuerelementen im Rahmen der Einhaltung verschiedener Standards und Bestimmungen von Microsoft. Jedes Steuerelement enthält Details darüber, wie Microsoft das Steuerelement implementiert hat und wie und wann diese Implementierung von Microsoft und/oder von einem unabhängigen Drittanbieter Prüfer getestet und validiert wurde.

### <a name="customer-managed-controls"></a>Vom Kunden verwaltete Steuerelemente

Dies ist die Sammlung von Steuerelementen, die von Ihrer Organisation verwaltet werden. Ihre Organisation ist für die Implementierung durch das Kunden verwaltete Steuerelement im Rahmen Ihres Konformitäts Prozesses für einen bestimmten Standard oder eine bestimmte Richtlinie verantwortlich. Von Kunden verwaltete Steuerelemente werden in Kontroll Familien für die entsprechende Zertifizierung oder Regulierung organisiert. Verwenden Sie die von Kunden verwalteten Steuerelemente, um die empfohlenen Aktionen zu implementieren, die von Microsoft als Teil Ihrer Compliance-Aktivitäten vorgeschlagen werden. Ihre Organisation kann die normativen Anleitungen und empfohlenen Kundenaktionen in jeder vom Kunden verwalteten Steuerung verwenden, um den Implementierungs-und Bewertungsprozess für dieses Steuerelement zu verwalten.

Kunden verwaltete Steuerelemente in Assessments verfügen außerdem über integrierte Workflow Verwaltungsfunktionen, mit deren Hilfe Sie den Fortschritt der Abschlussprüfung verwalten und nachverfolgen können. Mit dieser Workflow Funktionalität haben Sie folgende Möglichkeiten:

- Zuweisen von Aktionselementen für jedes Steuerelement
- Nachverfolgen von zugewiesenen Aktionselementen
- Hochladen von Beweisen für die Implementierung des Steuerelements
- Dokumentieren des Tests und der Überprüfung des Steuerelements
- Die Aktionselemente als implementiert und getestet markieren

Beispielsweise weist ein Compliance Officer in Ihrer Organisation einem IT-Administrator ein Aktionselement zu, in dem die erforderlichen Berechtigungen zum Ausführen der empfohlenen Aktion erforderlich sind. Der IT-Administrator lädt den Nachweis der Implementierungsaufgaben (Screenshots von Konfigurations-oder Richtlinieneinstellungen) und weist das Aktionselement dem Compliance Officer zurück, wenn es abgeschlossen ist. Der Compliance Officer wertet den gesammelten Beweis aus, testet die Implementierung des Steuerelements und zeichnet das Implementierungsdatum und die Testergebnisse im Compliance-Manager auf.

### <a name="shared-management-controls"></a>Gemeinsame Verwaltungssteuerelemente

Ein freigegebenes Steuerelement bezieht sich auf ein beliebiges Steuerelement, bei dem Microsoft und Kunden beide Aufgaben für die Implementierung teilen Beispielsweise erfordern Steuerelemente im Zusammenhang mit der Personal Prüfung, der Konto-und Kennwortverwaltung sowie der Verschlüsselung Aktionen sowohl von Microsoft als auch von Kunden.

## <a name="action-items"></a>Aktionselemente

[Aktionen Elemente](working-with-compliance-manager.md#controls-and-actions) sind in vom Kunden verwalteten Steuerelementen als Teil der integrierten Workflow Verwaltungsfunktionen enthalten, die Sie zum Verwalten und Nachverfolgen des Fortschritts für den Abschluss der Bewertung verwenden können.

Personen in Ihrer Organisation können den Compliance-Manager verwenden, um die vom Kunden verwalteten Steuerelemente aus allen Bewertungen zu überprüfen, denen Sie zugewiesen sind. Wenn ein Benutzer sich beim Compliance-Manager anmeldet und das **Aktionselemente** -Dashboard öffnet, wird eine Liste der Ihnen zugewiesenen Aktionselemente angezeigt. Je nach der dem Benutzer zugewiesenen Compliance-Manager-Rolle können Sie Implementierungs-oder Testdetails bereitstellen, den Status aktualisieren oder Aktionselemente zuweisen.

Zertifizierungs Steuerelemente werden in der Regel von einer Person implementiert und von einer anderen getestet. Wenn beispielsweise Aktionselemente, die anfänglich einer Person zugewiesen wurden, für die Implementierung abgeschlossen sind, werden der nächsten Person Aktionselemente zugewiesen, um Beweise zu testen und hochzuladen. Jeder Benutzer mit ausreichenden Berechtigungen für Steuerelement Zuweisungen kann Aktionselemente zuweisen und neu zuweisen. Dies ermöglicht eine zentrale Verwaltung von Steuerungs Zuweisungen und das dezentrale Routing von Aktionselementen zwischen Implementierern und Testern.

## <a name="permissions"></a>Berechtigungen

Compliance-Manager verwendet ein [Berechtigungsmodell](working-with-compliance-manager.md#permissions)für die rollenbasierte Zugriffssteuerung. Standardmäßig verfügt jeder Benutzer in Ihrer Organisation mit Azure Active Directory (Azure AD) über Vollzugriff und kann beliebige Aktionen im Compliance-Manager ausführen. Nachdem die rollenbasierte Zugriffssteuerung von Ihrer Organisation implementiert wurde, wird jedem Benutzer, der keiner definierten Compliance-Manager-Rolle zugewiesen ist, Gastzugriff zugewiesen. Microsoft-Dienstmitarbeiter haben keinen ständigen Zugriff auf Daten, die Sie eingeben oder hochladen.

Um von Standardberechtigungen zu wechseln und ein vollständig rollenbasiertes Zugriffssteuerungsmodell zu implementieren, muss jeder Compliance-Manager-Rolle mindestens ein Benutzer hinzugefügt werden. Nachdem ein Benutzer einer Rolle hinzugefügt wurde, werden die Berechtigungen zum Ausführen der dieser Rolle zugewiesenen Aktionen aus den standardmäßigen Berechtigungssätzen entfernt, die allen Benutzern zur Verfügung stehen. Nur Benutzer, die mit der Rolle bereitgestellt werden, können auf den Compliance-Manager zugreifen und die von dieser Rolle zulässigen Aktionen ausführen.

Wenn Sie der Rolle einen Benutzer hinzufügen, um Bewertungen zu verwalten, können nur Mitglieder dieser Rolle Bewertungen verwalten. Wenn Sie der Rolle keinen Benutzer hinzufügen, der Benutzern das Lesen der Daten in Assessments ermöglicht, können alle Benutzer in Ihrer Organisation auf den Compliance-Manager zugreifen und Daten in einer beliebigen Bewertung lesen.
  
## <a name="manage-evidence"></a>Verwalten von beweisen

Compliance-Manager kann Beweise für Ihre Implementierungsaufgaben zum Ausführen von Tests und zur Validierung von von Kunden verwalteten Steuerelementen speichern. Evidence enthält Dokumente, Tabellenkalkulationen, Screenshots, Bilder, Skripts, Skriptausgabe Dateien und andere Dateien. Compliance-Manager erhält auch automatisch Telemetrie und erstellt einen Evidence Record für Aktionselemente, die mit Secure Score integriert sind. Alle Daten, die als Beweismaterial in den Compliance-Manager hochgeladen wurden, werden in den USA auf Microsoft-Cloud-Speicher Standorten gespeichert. Diese Daten werden in Azure-Regionen in Südostasien und Westeuropa repliziert.

## <a name="templates"></a>Vorlagen

Compliance-Manager stellt vorkonfigurierte [Vorlagen](working-with-compliance-manager.md#templates) für Bewertungen bereit und ermöglicht es Ihnen, angepasste Vorlagen für von Kunden verwaltete Steuerelemente für Ihre Compliance-Anforderungen zu erstellen. Neue Vorlagen werden erstellt, indem Steuerelementinformationen aus einer Excel-Datei importiert werden, oder Sie können eine Vorlage aus einer Kopie einer vorhandenen Vorlage erstellen.

Die im Compliance-Manager enthaltenen vorkonfigurierten Vorlagen lauten wie folgt:
 
- [ISO 27001:2013](https://www.iso.org/obp/ui/#iso:std:iso-iec:27001:ed-2:v1:en)
- [ISO 27018:2019](https://www.iso.org/obp/ui/#iso:std:iso-iec:27018:ed-2:v1:en)
- [NIST 800-53](https://csrc.nist.gov/publications/detail/sp/800-53/rev-4/final)
- [NIST 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)
- [NIST-Cyber-Framework (CSF)](https://www.nist.gov/cyberframework)
- [Cloud Security Alliance (CSA) Cloud Control Matrix (CCM) 3.0.1](https://cloudsecurityalliance.org/working-groups/cloud-controls-matrix/#_overview)
- [Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet](https://ithandbook.ffiec.gov/it-booklets/information-security.aspx) 
- [HIPAA](https://www.hhs.gov/hipaa/for-professionals/index.html) / -[HITECH](https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html)
- [FedRAMP moderat](https://www.fedramp.gov/documents/)
- [Dsgvo der Europäischen Union](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN)

## <a name="compliance-score"></a>Kompatibilitätsbewertung

Das [Kompatibilitäts Ergebnis](compliance-score-methodology.md) ist eine zentrale Komponente von Compliance-Manager, die Ihrem Unternehmen hilft, die Compliance zu verstehen und zu verwalten. Wie bei der [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md)ist das Kompatibilitäts Ergebnis ein verhaltensbasiertes Bewertungssystem für Aktivitäten im Zusammenhang mit dem Datenschutz, der Datenschutz und der Sicherheit in Ihrer Organisation. Die Konformitätsbewertung für eine Bewertung ist ein Ausdruck der Übereinstimmung mit einer bestimmten Norm oder Verordnung. Je höher die numerische Punktzahl ist, desto besser ist die Konformitäts Haltung für die Bewertung. Das Verständnis der Methodik für die Konformitätsbewertung ist entscheidend für die Priorisierung erforderlicher Aktionen durch vom Kunden verwaltete Steuerelemente.
  
> [!IMPORTANT]
> Die Compliance-Bewertung drückt kein absolutes Maß für die Einhaltung eines bestimmten Standards oder einer bestimmten Vorschrift in der Organisation aus. Sie drückt vielmehr den Umfang aus, in dem Sie Steuerelemente einsetzen, durch die die Risiken für persönliche Daten und den Datenschutz reduziert werden können. Kein Dienst kann garantieren, dass Sie einen Standard oder eine Vorschrift einhalten. Die Compliance-Bewertung sollte in keinster Weise als eine Garantie verstanden werden.

## <a name="secure-score-integration"></a>Integration von Secure Score

Compliance-Manager ist in [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) integriert, um den Kompatibilitäts Bewertungs Wert für synchronisierte Aktionselemente automatisch mit einem sicheren Bewertungs Guthaben zu versehen. Dies ist für einzelne Aktionselemente konfigurierbar und stellt eine kontinuierliche Aktualisierung zwischen den Elementen bereit.

Sie haben beispielsweise eine sicherheitsbezogene Anforderung zum Aktivieren der Azure-Rechteverwaltung in Ihrer Organisation, die auch für ein Compliance-bezogenes Aktionselement gilt. Wenn Azure Rights Management aktiviert und von Secure Score verarbeitet wird, erhält Compliance-Manager eine Benachrichtigung über das Update, und die Bewertung für das Aktionselement wird automatisch mit Abschluss Kredit aktualisiert.

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Beginnen Sie [mit der Zusammenarbeit mit Compliance-Manager](working-with-compliance-manager.md) , um behördliche Compliance-Aktivitäten für Ihre Organisation zu verwalten.

## <a name="resources"></a>Ressourcen

- [Interaktiver Leitfaden: bewerten und verbessern der Datenschutz Steuerung mit Compliance-Manager](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft-Sicherheits-, Datenschutz-und Compliance-Tech-Community](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
