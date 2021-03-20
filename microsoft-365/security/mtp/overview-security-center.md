---
title: Microsoft 365 Security Center – Übersicht
description: 'Vorteile im Microsoft 365 Security Center: Microsoft Defender für Office 365 (MDO) und Microsoft Defender für Endpunkt (MDE), mit Microsoft Defender for Identity (MDI) und Microsoft Cloud App Security (MCAS). In diesem Artikel werden die Fortschritte im Microsoft 365 Security Center für Administratoren erläutert.'
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 43e341111ad1cb9b64ac257903d0e79bf24df5bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903882"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Das vereinheitlichte Microsoft 365 Security Center – Übersicht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender für Office 365](../office-365-security/office-365-atp.md)

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](./mtp-pilot.md?ocid=cx-evalpilot).

Im verbesserten **Microsoft 365 Security Center** ([https://security.microsoft.com](https://security.microsoft.com)) werden Schutz, Erkennung, Untersuchung und Reaktion auf *E-Mail-*, *Zusammenarbeit*, *Identität* und *Geräte*-Bedrohungen in einem zentralen Portal kombiniert.

Das Microsoft 365 Security Center vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen wie Microsoft Defender Security Center und dem Office 365 Security & Compliance Center. Das Security Center legt wert auf den schnellen Zugriff auf Informationen, einfachere Layouts und das Zusammenbringen verwandter Informationen zur einfacheren Nutzung. Dieses Center umfasst:

- **[Microsoft Defender für Office 365](../office-365-security/office-365-atp.md)** Microsoft Defender für Office 365 hilft Organisationen, ihr Unternehmen mit einer Reihe von Features zur Verhinderung, Erkennung, Untersuchung und Suche zum Schutz von E-Mails und Office 365-Ressourcen zu schützen.
- **[Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** liefert präventiven Schutz, Erkennung nach einem Angriff, automatisierte Untersuchung und Reaktion für Geräte in Ihrer Organisation.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** ist Teil der Microsoft-Lösung *Extended Detection and Response* (XDR), die das Sicherheitsportfolio von Microsoft 365 nutzt, um Bedrohungsdaten domänenübergreifend automatisch zu analysieren und ein Bild eines Angriffs auf einem einzelnen Dashboard zu erstellen.

Wenn Sie Informationen zu den Aktualisierungen im Office 365 Security & Compliance Center oder im Microsoft Defender Security Center benötigen, lesen Sie:

- [Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Das erwartet Sie

Alle Sicherheitsinhalte, die Sie im Office 365 Security & Compliance Center (protection.office.com) und im Microsoft Defender Security Center (securitycenter.microsoft.com) verwenden, finden Sie jetzt im *Microsoft 365 Security Center*.

Das Microsoft 365 Security Center hilft Sicherheitsteams, Angriffe zu untersuchen und darauf zu reagieren, indem es Signale aus verschiedenen Workloads zu einer einzigen, einheitlichen Oberfläche sendet:

- Vorfälle und Benachrichtigungen
- Suchen
- Info-Center
- Bedrohungsanalyse

Das Microsoft 365 Security Center hebt beim Zusammenführen von Microsoft Defender für Office 365 und Microsoft Defender für Endpunkt *Einheit, Klarheit und gemeinsame Ziele* hervor. Die Zusammenlegung basierte auf den unten aufgeführten Prioritäten und erfolgte ohne Abstriche an den Fähigkeiten, die jede Sicherheitssuite in die Kombination einbrachte:

- gemeinsame Bausteine
- gemeinsame Terminologie
- gemeinsame Entitäten
- Featureparität mit anderen Workloads

## <a name="unified-investigations"></a>Vereinheitlichte Untersuchungen

Durch die Optimierung der Sicherheitscenter wird ein einzelner Bereich zum Untersuchen von Vorfällen in einer Microsoft 365-Organisation erstellt. Ein primäres Beispiel ist der Node **Vorfälle** auf der Schnellstartansicht des Microsoft 365 Security Centers.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Die Seite „Vorfälle“ in MDO.":::

Beispielsweise bringt Sie das Doppelklicken auf einen Vorfallnamen mit dem Schweregrad **Hoch** zu einer Seite, auf der der Vorteil von zusammenlaufenden Centers veranschaulicht wird.

![Mehrstufiger Vorfall mit Privilegien-Eskalation auf mehreren Endpunkten, wobei 16 betroffene Geräte und 9 betroffene Benutzer angezeigt werden.](../../media/converged-incident-info-3.png)

> [!TIP]
> Die konvergierte Registerkarte **Benutzer** ist ein guter Ort, um Ihre Anfragen zu beginnen. Auf dieser einzelnen Seite werden Informationen für Benutzer aus konvergierten Workloads (Microsoft Defender für Endpunkt, Microsoft Defender for Identity und MCAS, sofern verwendet) sowie aus einer Reihe von Quellen wie Windows Server Active Directory, Azure Active Directory, synchronisierten, lokalen Benutzern und Drittanbieterbenutzern angezeigt. Erfahren Sie mehr über [die neue Benutzererfahrung](investigate-users.md).

Vorfallinformationen zeigen die Spezifischen Benutzer/Identitäten und Geräte mit Risiken neben betroffenen Postfächern an. Es bezieht sich auch auf alle **Untersuchungsinformationen** und gesammelte **Beweise**. Dies erleichtert Administratoren und Teams für den Sicherheitsbetrieb das Pivotieren einer Warnung mit hohem Risiko für die betroffenen Benutzer und Postfächer. Auf der Registerkarten **Vorfall**, die sich oben auf dieser Seite befinden, sehen Sie weitere wichtige Sicherheitspivots, die von diesem einen Ort aus verfügbar sind.

> [!IMPORTANT]
> Am oberen Seitenanfang einer bestimmten Seite werden die Registerkarten **Zusammenfassung**, **Benachrichtigungen**, **Geräte**, **Benutzer**, **Postfächer**, **Untersuchungen** und **Beweise** angezeigt.

Durch Auswählen von **Untersuchungen** wird eine Seite geöffnet, die eine Grafik der stattfindenden Analyse zeigt und einen Status (z. B. **ausstehende Genehmigung**) zur Behebung auflistet. Nehmen Sie sich Zeit, um bestimmte Vorfälle in Ihrer Umgebung auszuwählen, führen Sie einen Drilldown in diese Registerkarten aus, und üben Sie das Erstellen eines Profils für verschiedene Arten von Bedrohungen. Die Vertrautheit kommt allen späteren dringenden Untersuchungen zugute.

## <a name="improved-processes"></a>Verbesserte Prozesse

Allgemeine Steuerelemente und Inhalte werden entweder an derselben Stelle angezeigt oder sind zu einem Datenfeed zusammengefasst, wodurch sie einfacher zu finden sind. Beispielsweise einheitliche Einstellungen.

### <a name="unified-settings"></a>Einheitliche Einstellungen

![auf "Rollen" geklickt und die Seite "Einstellungen" geöffnet, die allgemeine Einstellungen, Berechtigungen, APIs und Regeln enthält. Wählen Sie „Berechtigungen“ und dann „Rollen“ aus. Zeigt alle Rollen an](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Berechtigungen und Rollen

![Seite "Berechtigungen und Rollen" mit den Endpunkten "Rollen und Gruppen", "Rollen" und "Gerätegruppen".](../../media/converged-roles-5.png)

 Der Zugriff auf das Microsoft 365 Security Center ist mit globalen Azure Active Directory-Rollen oder mit benutzerdefinierten Rollen konfiguriert. Für Defender für Endpunkt, siehe [Zuweisen des Benutzerzugriffs auf das Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access). Für Defender für Office 365, siehe [Berechtigungen im Microsoft 365 Compliance Center und Microsoft 365 Security Center](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Weitere Informationen zum [Verwalten des Zugriffs auf Microsoft 365 Defender](mtp-permissions.md)
- Weitere Informationen zum [Erstellen benutzerdefinierter Rollen](custom-roles.md) im Microsoft 365 Security Center

> [!NOTE]
> Microsoft Defender für Endpunkt im Microsoft 365 Security Center unterstützt [das Gewähren von Zugriff auf verwaltete Sicherheitsdienstanbieter (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in der gleichen Weise, wie der Zugriff [im Microsoft Defender Security Center gewährt wird](./mssp-access.md).

### <a name="integrated-reports"></a>Integrierte Berichte

Auch Berichte sind im Microsoft 365 Security Center vereinheitlicht. Administratoren können mit einem allgemeinen Sicherheitsbericht beginnen und dann in bestimmte Berichte zu Endpunkten, E-Mail und Zusammenarbeit verzweigen. Die Links hier werden dynamisch basierend auf der Workloadkonfiguration generiert.

### <a name="quickly-view-your-microsoft-365-environment"></a>Schnelles Anzeigen Ihrer Microsoft 365-Umgebung

Die **Startseite** zeigt viele der allgemeinen Karten, die Sicherheitsteams benötigen. Die Zusammenstellung von Karten und Daten hängt von der Benutzerrolle ab. Da das Microsoft 365 Security Center die rollenbasierte Zugriffssteuerung verwendet, werden in unterschiedlichen Rollen Karten angezeigt, die für deren tägliche Arbeit von größerer Bedeutung sind.  

Diese Informationen auf einen Blick helfen Ihnen, über die neuesten Aktivitäten in Ihrer Organisation auf dem Laufenden zu bleiben. Das Microsoft 365 Security Center vereint Signale aus verschiedenen Quellen, um eine umfassenden Blick auf Ihre Microsoft 365-Umgebung zu präsentieren.

Die Karten können in vier Kategorien unterteilt werden:

- **Identitäten**: Überwachen Sie die Identitäten in Ihrer Organisation, und verfolgen Sie verdächtige oder riskante Verhaltensweisen nach. [Weitere Informationen zum Identitätsschutz](/azure/active-directory/identity-protection/overview-identity-protection).
- **Daten**: Hilft beim Nachverfolgen von Benutzeraktivitäten, die zu einer nicht autorisierten Datenweitergabe führen könnten.
- **Geräte**: Hier erhalten Sie aktuelle Informationen zu Benachrichtigungen, Sicherheitsverletzungsaktivitäten und anderen Bedrohungen auf Ihren Geräten.
- **Apps**: Gewinnen Sie Einblicke in die Verwendung von Cloud-Apps in Ihrer Organisation. [Weitere Informationen zu von Cloud App Security gefundenen Apps](/cloud-app-security/discovered-apps).

## <a name="threat-analytics-with-better-data-coverage"></a>Bedrohungsanalysen mit besserer Datenabdeckung
Verfolgen Sie aufkommende Bedrohungen und reagieren Sie darauf mit den folgenden integrierten Bedrohungsanalysen von Microsoft 365 Defender:

- Bessere Datenabdeckung zwischen Microsoft Defender für Endpunkt und Microsoft Defender für Office 365, so dass kombiniertes Vorfallmanagement, automatische Untersuchung, Behebung und proaktive oder reaktive Bedrohungssuche domänenübergreifend möglich sind. 
- E-Mail-bezogene Erkennungen und Begrenzungen durch Microsoft Defender für Office 365 zusätzlich zu den Endpunktdaten, die bereits von Microsoft Defender für Endpoint verfügbar sind.
- Eine Ansicht bedrohungsbezogener Vorfälle, die Benachrichtigungen zu durchgängigen Angriffsgeschichten in Microsoft Defender für Endpunkt und Microsoft Defender für Office 365 zusammenfasst, um den Arbeitsaufwand zu reduzieren sowie Ihre Untersuchung zu vereinfachen und zu beschleunigen.
- Angriffsversuche, die von Microsoft 365 Defender-Lösungen erkannt und blockiert wurden. Es gibt auch Daten, die Sie verwenden können, um vorbeugende Maßnahmen zu ergreifen, mit denen das Risiko einer weiteren Gefährdung entschärft und die Resilienz erhöht wird. 
- Verbessertes Design, das umsetzbare Informationen in den Vordergrund stellt, damit Sie schnell die Daten identifizieren können, auf die Sie sich dringend konzentrieren, die Sie untersuchen und die Sie aus den Berichten nutzen müssen.

## <a name="a-centralized-learning-hub"></a>Ein zentraler Lernhub

Das Microsoft 365 Security Center enthält einen Lernhub, der offizielle Anleitungen aus Ressourcen wie dem Microsoft-Security-Blog, der Microsoft-Security-Community auf YouTube und der offiziellen Dokumentation auf docs.microsoft.com auflistet.

Innerhalb des Learning Hubs stehen die Anleitungen für E-Mail & Zusammenarbeit (Microsoft Defender für Office 365 oder MDO) Seite an Seite mit den Lernressourcen für Endpunkt (Microsoft Defender für Endpunkt oder MDE) und Microsoft 365 Defender.

Der Lernhub wird mit Lernpfaden geöffnet, die nach Themen organisiert sind, wie "So untersuchen Sie mit Microsoft 365 Defender" und "Bewährte Methoden für Microsoft Defender für Office 365“. Dieser Abschnitt wird derzeit von der Sicherheitsproduktgruppe in Microsoft erstellt. Jeder Lernpfad spiegelt eine geplante Zeit wider, die es dauert, um die Konzepte zu durchlaufen. Beispiel: "Schritte, die sie unternehmen müssen, wenn ein Benutzerkonto von Microsoft Defender für Office 365 kompromittiert ist" dauert voraussichtlich 8 Minuten und ist ein wertvolles Lernprogramm für unterwegs.

Nachdem Sie sich durch den Inhalt geklickt haben, kann es hilfreich sein, für diese Website ein Lesezeichen zu setzen und Lesezeichen in einem Ordner "Sicherheit" oder "Kritisch" zu organisieren. Zum Anzeigen aller Lernpfade klicken Sie im Hauptbereich auf den Link "Alle anzeigen".

> [!NOTE]
> Es gibt hilfreiche **Filter** oben im Microsoft 365 Security Center-Lernhub, mit denen Sie zwischen Produkten (derzeit Microsoft 365 Defender, Microsoft Defender für Endpoint und Microsoft Defender für Office 365) auswählen können. Beachten Sie, dass die Anzahl der Lernressourcen für jeden Abschnitt aufgelistet ist, was Lernenden dabei helfen kann, zu verfolgen, wie viele Ressourcen für Schulung und Lernen zur Verfügung stehen.
>
> Neben dem Produktfilter werden aktuelle Themen, Ressourcentypen (von Videos bis Webinaren), Stufen der Vertrautheit oder Erfahrung mit Sicherheitsbereichen, Sicherheitsrollen und Produktfeatures aufgelistet.

## <a name="send-us-your-feedback"></a>Feedback senden

Wir freuen uns über Ihr Feedback. Wir suchen ständig nach Verbesserung. Wenn es also etwas gibt, das Sie gerne sehen würden, [senden Sie uns Ihr Microsoft 365 Defender-Feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

Sie können auch Feedback in diesem Artikel abgeben. Im Abschnitt "Feedback" am Ende unter "Senden und Anzeigen von Feedback für" sind die Optionen *Dieses Produkt* oder *Diese Seite*.

Verwenden Sie die Schaltfläche **Dieses Produkt** für *Prdukt*-Feedback:

1. Wählen Sie *Dieses Produkt* am Ende des Artikels aus.
    1. Klicken Sie mit der rechten Maustaste auf die Schaltfläche und dann auf "In einer neuen Registerkarte öffnen", wenn Sie diese Anweisungen weiterlesen möchten.
2. Damit navigieren Sie zum **UserVoice-Forum**.
3. Sie haben zwei Möglichkeiten:
    1. Scrollen Sie nach unten zum Textfeld *Wie können wir die Compliance verbessern oder Ihre Benutzer in Office 365 besser schützen?* und fügen Sie in *Microsoft 365 Security Center* ein. Sie können die Ergebnisse nach einer Idee wie Ihrer durchsuchen und für diese stimmen, oder Sie können die Schaltfläche für **Posten einer neuen Idee** verwenden.
    1. Wenn Sie sicher sind, dass dieses Problem bereits gemeldet wurde, und Sie es durch eine Stimme (oder Stimmen) hervorheben möchten, verwenden Sie das Feld *Feedback geben* auf der rechten Seite von UserVoice. Suchen Sie nach *Microsoft 365 Security Center*, **suchen Sie das Problem und verwenden Sie die Schaltfläche „Abstimmen“**, um den Status zu erhöhen.

Verwenden Sie *Diese Seite*, um Feedback zum Artikel selbst zu geben. Vielen Dank für Ihr Feedback. Ihre Stimme hilft uns, die Produkte zu verbessern.

### <a name="explore-what-the-security-center-has-to-offer"></a>Erkunden, was das Sicherheitscenter zu bieten hat

Erkunden Sie weiter die Features und Funktionen im Microsoft 365 Security Center:

- [Verwalten von Vorfällen und Benachrichtigungen](manage-incidents.md)
- [Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen](threat-analytics.md)
- [Das Info-Center](./mtp-action-center.md)
- [Gefahrensuche über Geräte, E-Mails, Apps und Identitäten hinweg](./advanced-hunting-query-emails-devices.md)
- [Regeln für die benutzerdefinierte Erkennung](./custom-detection-rules.md)
- [Benachrichtigungen für E-Mail & Zusammenarbeit](../../compliance/alert-policies.md#default-alert-policies)
- [Erstellen einer Phishingangriff-Simulation](../office-365-security/attack-simulation-training.md) und [Erstellen einer Nutzlast für die Schulung Ihrer Teams](../office-365-security/attack-simulation-training-payloads.md)
 
### <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center](overview-security-center.md)
- [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)