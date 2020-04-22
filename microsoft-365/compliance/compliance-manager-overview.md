---
title: Übersicht über den Microsoft Compliance-Manager
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 31a56f7cba8bb8957d758ca2905853f26d1f8edf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632990"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft Compliance-Manager (Vorschau)

> [!IMPORTANT]
> Der Compliance-Manager ist nicht in Office 365, betrieben von 21Vianet, Office 365 Deutschland, Office 365 US Government Community High (GCC) High oder Office 365 Department of Defense verfügbar.

**In diesem**Artikel erfahren Sie, was Compliance-Manager ist und welche Hauptkomponenten Sie kennen.

**Erfahren Sie mehr über Updates**: Wir haben mehrere Updates im April 2020 Public Preview Release veröffentlicht. In den Versionshinweisen zu [Compliance-Manager](compliance-manager-release-notes.md) finden Sie Informationen zu neuen und bekannten Problemen.

## <a name="what-is-compliance-manager"></a>Was ist Compliance-Manager?

Der [Microsoft Compliance-Manager (Preview)](https://servicetrust.microsoft.com/ComplianceManager) ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft Service Trust-Portal zum Verwalten von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services. Als Teil Ihres Microsoft 365-, Office 365-oder Azure Active Directory-Abonnements unterstützt Compliance Manager das Verwalten von behördlichen Vorschriften im Rahmen des Modells für die gemeinsame Verantwortung für Microsoft Cloud Services.

Mit dem Compliance-Manager kann Ihre Organisation:
  
- Kombinieren detaillierter Compliance-Informationen von Microsoft für Auditoren und Regulatoren zu seinen Cloud-Diensten mit Ihrer Compliance-Selbsteinschätzung für Standards und Vorschriften, die für Ihre Organisation gelten. Dazu gehören Normen und Verordnungen, die von der internationalen Organisation für Normung (ISO), dem National Institute of Standards and Technology (NIST), der Krankenversicherung Portabilität und dem Accounting Act (HIPAA), der allgemeinen Datenschutzverordnung (dsgvo) und vielen anderen beschrieben werden.
- Ermöglicht Ihnen, Compliance-und bewertungsbezogene Aktivitäten zuzuweisen, nachzuverfolgen und zu erfassen, mit deren Hilfe Ihre Organisation Team Barrieren überwinden kann, um Ihre Compliance-Ziele zu erreichen.
- Stellen Sie eine Konformitätsbewertung zur Verfügung, damit Sie Ihren Fortschritt nachverfolgen und Überwachungssteuerelemente priorisieren können, mit denen die Gefährdung Ihrer Organisation reduziert wird.
- Stellen Sie ein sicheres Repository bereit, mit dem Sie Beweise und andere Artefakte im Zusammenhang mit ihren Compliance-Aktivitäten hochladen und verwalten können.
- Erstellen Sie ausführliche Microsoft Excel Berichte, in denen Compliance-Aktivitäten dokumentiert werden, die von Microsoft und Ihrer Organisation für Auditoren, Regulatoren und andere Konformitäts Prüfer ausgeführt wurden.

> [!NOTE]
> Die im Compliance-Manager bereitgestellten Kundenaktionen sind Empfehlungen; Es liegt in Ihrer Organisation, die Wirksamkeit dieser Empfehlungen in ihrem jeweiligen regulatorischen Umfeld vor der Implementierung zu bewerten. Empfehlungen aus dem Compliance-Manager sollten nicht als eine Garantie für Compliance interpretiert werden.

## <a name="relationship-to-compliance-score"></a>Beziehung zur Konformitätsbewertung

[Microsoft Compliance Score (Preview)](compliance-score.md) ist ein Feature im Microsoft 365 Compliance Center, das eine Ansicht auf oberster Ebene in der Compliance-Position Ihrer Organisation bereitstellt. Sie berechnet eine auf Risiken basierende Bewertung, die Ihren Fortschritt bei der Durchführung von Maßnahmen misst, mit denen sich Risiken hinsichtlich des Datenschutzes und regulatorischer Standards verringern lassen. Die Kenntnis ihrer allgemeinen Konformitätsbewertung hilft Ihrer Organisation, die Compliance zu verstehen und zu verwalten. Grundlegendes [zur Berechnung der Konformitätsbewertung](compliance-score-methodology.md)

Compliance-Manager teilt dasselbe Back-End mit Kompatibilitätsbewertung. Während der öffentlichen Vorschauphase für beide Tools ist Compliance-Manager der Ort, an dem Sie Ihre Bewertungen und Implementierungen von benutzerdefinierten Steuerelementen verwalten. Erfahren Sie mehr über die [Beziehung zwischen Compliance Score und Compliance-Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).
  
> [!IMPORTANT]
> Die Compliancebewertung ist kein absolutes Maß für die Einhaltung bestimmter Standards oder Vorschriften durch die Organisation. Sie drückt aus, inwieweit Sie Kontrollmechanismen eingeführt haben, die die Risiken für personenbezogene Daten und die Privatsphäre des Einzelnen verringern können. Kein Dienst kann gewährleisten, dass Sie mit einem Standard oder einer Verordnung konform sind, und der Kompatibilitäts Faktor sollte nicht als Garantie in irgendeiner Weise interpretiert werden.

## <a name="compliance-manager-components"></a>Compliance-Manager-Komponenten

Compliance-Manager verwendet mehrere Komponenten, die Sie bei ihren Compliance-Verwaltungsaktivitäten unterstützen. Diese Komponenten arbeiten zusammen, um einen vollständigen Verwaltungs Workflow und problemlose Kompatibilitätsberichte für Auditoren bereitzustellen.

Das Diagramm zeigt die Beziehungen zwischen den primären Komponenten von Compliance-Manager:

![Beziehungen in Compliance-Manager, Version 3](../media/compliance-manager-relationships.png)

## <a name="groups"></a>Gruppen

[Gruppen](working-with-compliance-manager.md#groups) sind Container, die es Ihnen ermöglichen, Bewertungen zu organisieren und allgemeine Informations-und Workflowaufgaben Zwischenbewertungen mit denselben oder Verwandten, vom Kunden verwalteten Steuerelementen freizugeben. Wenn zwei unterschiedliche Bewertungen in derselben Gruppe das vom Kunden verwaltete Steuerelement gemeinsam nutzen, wird der Abschluss der Implementierungsdetails, des Tests und des Status für das Steuerelement in allen anderen Bewertungen in der Gruppe automatisch mit dem gleichen Steuerelement synchronisiert. Dadurch werden die zugewiesenen Aktionselemente für jedes Steuerelement in der gesamten Gruppe vereinheitlicht und Arbeits Duplikate reduziert. Sie können auch festlegen, dass Gruppen zum Organisieren verwendet werden. Assessments nach Jahr, Bereich, Konformitäts Standard oder anderen Gruppierungen, die Ihnen bei der Organisation Ihrer Compliance-arbeiten helfen.

## <a name="assessments"></a>Bewertungen

Bei [Assessments](working-with-compliance-manager.md#assessments) handelt es sich um Container, mit denen Sie Steuerelemente basierend auf den Zuständigkeiten zwischen Microsoft und Ihrer Organisation für die Bewertung der Sicherheits-und Konformitätsrisiken von Cloud-Diensten organisieren können. Mithilfe von Assessments können Sie Datenschutzgarantien implementieren, die durch einen Compliance-Standard und entsprechende Datenschutzstandards, Verordnungen oder Gesetze festgelegt sind. Sie unterstützen Sie beim Erkennen Ihrer Datenschutz-und Compliance-Haltung gegenüber dem ausgewählten Industriestandard für den ausgewählten Microsoft Cloud-Dienst. Die Bewertungen werden durch die Implementierung von Steuerelementen vervollständigt, die in der Bewertung enthalten sind, die einem Zertifizierungsstandard zugeordnet ist.

Standardmäßig erstellt Compliance-Manager die folgenden Bewertungen für Ihre Organisation:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 dsgvo

Assessments weisen mehrere Komponenten auf:
  
- **In-Scope-Dienste**: jede Bewertung gilt für eine bestimmte Gruppe von Microsoft-Diensten.
- Von **Microsoft verwaltete Steuerelemente**: Microsoft implementiert und verwaltet für jeden clouddienst eine Reihe von Konformitätskontrollen für zutreffende Standards und Vorschriften.
- Vom **Kunden verwaltete Steuerelemente**: diese Steuerelemente werden von Ihrer Organisation implementiert, wenn Sie für jedes Steuerelement Aktionen ausführen.
- **Bewertungsfaktor**: der Prozentsatz der Gesamtpunktzahl für vom Kunden verwaltete Steuerelemente in der Bewertung. Auf diese Weise können Sie die Implementierung der jedem Steuerelement zugewiesenen Aktionen nachverfolgen.

## <a name="controls"></a>Steuerelemente

[Steuerelemente](working-with-compliance-manager.md#controls-and-actions) sind Compliance-Prozesscontainer im Compliance-Manager, die definieren, wie Compliance-Aktivitäten verwaltet werden. Diese Steuerelemente sind in Steuerelementfamilien organisiert, die mit der Bewertungsstruktur für entsprechende Zertifizierungen oder Verordnungen übereinstimmen.

- **Steuerelement-ID**: der Name des ausgewählten Steuerelements aus der entsprechenden Zertifizierung oder Verordnung.
- **Steuerelement Titel**: der Titel für die Steuerelement-ID aus der entsprechenden Zertifizierung oder Verordnung.
- **Artikel-ID**: Dieses Feld ist nur für dsgvo-Bewertungen und gibt die entsprechende dsgvo-Artikelnummer an.
- **Description**: Text of Control aus der entsprechenden Zertifizierung oder Verordnung. Aufgrund von Copyright-Einschränkungen wird ein Link zu relevanten Informationen für ISO-Standards aufgeführt.

![Steuerelemente in Compliance-Manager Version 3](../media/compliance-manager-controls.png)

Es gibt drei Arten von Steuerelementen im Compliance-Manager, von **Microsoft verwaltete Steuer**Elemente, von **Kunden verwalteten**Steuerelementen und von Steuerelementen für die **gemeinsame Verwaltung**.

### <a name="microsoft-managed-controls"></a>Von Microsoft verwaltete Steuerelemente

Für jeden clouddienst implementiert und verwaltet Microsoft eine Reihe von Steuerelementen im Rahmen der Einhaltung verschiedener Standards und Bestimmungen von Microsoft. Jedes Steuerelement enthält Details darüber, wie Microsoft das Steuerelement implementiert hat und wie und wann diese Implementierung von Microsoft und/oder von einem unabhängigen Drittanbieter Prüfer getestet und validiert wurde.

### <a name="customer-managed-controls"></a>Vom Kunden verwaltete Steuerelemente

Vom Kunden verwaltete Steuerelemente werden von Ihrer Organisation verwaltet. Ihre Organisation ist für die Implementierung durch das Kunden verwaltete Steuerelement im Rahmen Ihres Konformitäts Prozesses für einen bestimmten Standard oder eine bestimmte Richtlinie verantwortlich. Von Kunden verwaltete Steuerelemente werden in Kontroll Familien für die entsprechende Zertifizierung oder Regulierung organisiert. Verwenden Sie die von Kunden verwalteten Steuerelemente, um die empfohlenen Aktionen zu implementieren, die von Microsoft als Teil Ihrer Compliance-Aktivitäten vorgeschlagen werden. Ihre Organisation kann die normativen Anleitungen und empfohlenen Kundenaktionen in jeder vom Kunden verwalteten Steuerung verwenden, um den Implementierungs-und Bewertungsprozess für dieses Steuerelement zu verwalten.

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

Personen in Ihrer Organisation können den Compliance-Manager verwenden, um die vom Kunden verwalteten Steuerelemente aus allen Bewertungen zu überprüfen, denen Sie zugewiesen sind. Wenn ein Benutzer sich beim Compliance-Manager anmeldet und das **Aktionselemente**-Dashboard öffnet, wird eine Liste der ihm zugewiesenen Aktionselemente angezeigt. Je nach der Compliance-Manager-Rolle, die dem Benutzer zugewiesen wurde, kann er Implementierungs- oder Testdetails bereitstellen, den Status hochladen oder Aktionselemente zuweisen.

Zertifizierungs Steuerelemente werden in der Regel von einer Person implementiert und von einer anderen getestet. Wenn beispielsweise Aktionselemente, die anfänglich einer Person zugewiesen wurden, für die Implementierung abgeschlossen sind, werden diese Aktionselemente der nächsten Person zugewiesen, um Beweise zu testen und hochzuladen. Jeder Benutzer mit ausreichenden Berechtigungen für Steuerelement Zuweisungen kann Aktionselemente zuweisen und neu zuweisen. Dies ermöglicht eine zentrale Verwaltung von Steuerungs Zuweisungen und das dezentrale Routing von Aktionselementen zwischen Implementierern und Testern.

Beachten Sie, dass **Verbesserungs Aktionen** im Kompatibilitäts Bewertungsergebnis das Äquivalent von **Aktionselementen** im Compliance-Manager sind.

## <a name="permissions"></a>Berechtigungen

Compliance-Manager verwendet ein Berechtigungsmodell der rollenbasierten Zugriffssteuerung. Nur Benutzer, denen eine Benutzerrolle zugewiesen ist, können auf Compliance-Manager zugreifen, und welche Aktionen ein Benutzer ausführen darf, wird durch den jeweiligen Rollentyp eingeschränkt. Zeigt [eine Tabelle](working-with-compliance-manager.md#permissions) mit den für jede Berechtigung zulässigen Aktionen an.

Der Portaladministrator für Compliance-Manager kann die Berechtigungen für andere Benutzer im Compliance-Manager festlegen, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie im Dropdownmenü Top **more** die Option **Admin**und dann **Settings**aus.
2. Wählen Sie hier die Rolle aus, die Sie zuweisen möchten, und fügen Sie dann den Mitarbeiter hinzu, den Sie dieser Rolle zuweisen möchten. Die Benutzer können dann bestimmte Aktionen ausführen.

Benutzer, denen die [globale Leserrolle in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader) zugewiesen ist, verfügen über eine schreibgeschützte Berechtigung für den Zugriff auf den Compliance-Manager. Sie können jedoch keine Daten bearbeiten oder Aktionen im Compliance-Manager durchführen.

Es gibt keine standardmäßige **Gastzugriffs** Rolle mehr. Jedem Benutzer muss eine Rolle zugewiesen werden, damit er auf Compliance-Manager zugreifen und darin arbeiten kann.
  
## <a name="manage-evidence"></a>Verwalten von beweisen

Compliance-Manager kann Beweise für Ihre Implementierungsaufgaben zum Testen und zur Validierung von von Kunden verwalteten Steuerelementen speichern. Evidence enthält Dokumente, Tabellenkalkulationen, Screenshots, Bilder, Skripts, Skriptausgabe Dateien und andere Dateien. Compliance-Manager erhält auch automatisch Telemetrie und erstellt einen Evidence Record für Aktionselemente, die mit Secure Score integriert sind. Alle Daten, die als Beweismaterial in den Compliance-Manager hochgeladen wurden, werden in den USA auf Microsoft-Cloud-Speicher Standorten gespeichert. Diese Daten werden in Azure-Regionen in Südostasien und Westeuropa repliziert.

## <a name="templates"></a>Vorlagen

Compliance-Manager stellt vorkonfigurierte [Vorlagen](working-with-compliance-manager.md#templates) für Bewertungen bereit und ermöglicht es Ihnen, angepasste Vorlagen für von Kunden verwaltete Steuerelemente für Ihre Compliance-Anforderungen zu erstellen. Neue Vorlagen werden erstellt, indem Steuerelementinformationen aus einer Excel-Datei importiert werden, oder Sie können eine Vorlage aus einer Kopie einer vorhandenen Vorlage erstellen.

Die im Compliance-Manager enthaltenen vorkonfigurierten Vorlagen lauten wie folgt:

1. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
4. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
5. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
6. [NIST-Cyber-Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
7. [Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet](https://go.microsoft.com/fwlink/?linkid=2109077) 
9. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / -[HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)
10. [FedRAMP moderat](https://go.microsoft.com/fwlink/?linkid=2108869)
11. [Dsgvo der Europäischen Union](https://go.microsoft.com/fwlink/?linkid=2108870)
12. [California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Vorschau)
13. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Vorschau)
14. [Microsoft 365-Datenschutz Basis](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

## <a name="secure-score-integration"></a>Integration von Secure Score

Compliance-Manager ist in [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) integriert, um den Kompatibilitäts Bewertungs Wert für synchronisierte Aktionselemente automatisch mit einem sicheren Bewertungs Guthaben zu versehen. Dies ist für einzelne Aktionselemente oder alle Aktionen Global konfigurierbar und stellt Aktualisierungen von Secure Score zur Verfügung.

Sie haben beispielsweise eine sicherheitsbezogene Anforderung zum Aktivieren der Azure-Rechteverwaltung in Ihrer Organisation, die auch für ein Compliance-bezogenes Aktionselement gilt. Wenn Azure Rights Management aktiviert und von Secure Score verarbeitet wird, erhält Compliance-Manager eine Benachrichtigung über das Update, und die Bewertung für das Aktionselement wird automatisch mit Abschluss Kredit aktualisiert.

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Beginnen Sie [mit der Zusammenarbeit mit Compliance-Manager](working-with-compliance-manager.md) , um behördliche Compliance-Aktivitäten für Ihre Organisation zu verwalten.

## <a name="resources"></a>Ressourcen

- [Interaktiver Leitfaden: bewerten und verbessern der Datenschutz Steuerung mit Compliance-Manager](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft-Sicherheits-, Datenschutz-und Compliance-Tech-Community](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)