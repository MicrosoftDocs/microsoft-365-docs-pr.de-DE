---
title: Übersicht über Microsoft 365 Security Center, die MDO, MDE, MDI und MCAS kombiniert
description: 'Vorteile im Microsoft 365 Security Center: Microsoft Defender für Office 365 (MDO) und Microsoft Defender für Endpunkt (MDE), mit Microsoft Defender for Identity (MDI) und Microsoft Cloud App Security (MCAS). In diesem Artikel werden die Fortschritte im Microsoft 365 Security Center für Administratoren erläutert.'
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
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
ms.openlocfilehash: 3f71e5aa37ad9184a21bf92232951d8884ee2577
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782513"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Das vereinheitlichte Microsoft 365 Security Center – Übersicht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).

Im verbesserten **Microsoft 365 Security Center** ([https://security.microsoft.com](https://security.microsoft.com)) werden Schutz, Erkennung, Untersuchung und Reaktion auf *E-Mail-*, *Zusammenarbeit*, *Identität* und *Geräte*-Bedrohungen in einem zentralen Portal kombiniert.

Das Microsoft 365 Security Center vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen wie Microsoft Defender Security Center und dem Office 365 Security & Compliance Center. Das Security Center legt wert auf den schnellen Zugriff auf Informationen, einfachere Layouts und das Zusammenbringen verwandter Informationen zur einfacheren Nutzung. Dieses Center umfasst:

- **[Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender für Office 365 hilft Organisationen, ihr Unternehmen mit einer Reihe von Features zur Verhinderung, Erkennung, Untersuchung und Suche zum Schutz von E-Mails und Office 365-Ressourcen zu schützen.
- **[Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** liefert präventiven Schutz, Erkennung nach einem Angriff, automatisierte Untersuchung und Reaktion für Geräte in Ihrer Organisation.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** ist Teil der Microsoft-Lösung *Extended Detection and Response* (XDR), die das Sicherheitsportfolio von Microsoft 365 nutzt, um Bedrohungsdaten domänenübergreifend automatisch zu analysieren und ein Bild eines Angriffs auf einem einzelnen Dashboard zu erstellen.

Wenn Sie Informationen zu den Aktualisierungen im Office 365 Security & Compliance Center oder im Microsoft Defender Security Center benötigen, lesen Sie:

- [Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)

> [!NOTE]
> Das Microsoft 365 Sicherheitsportal verwendet und erzwingt vorhandenen rollenbasierten Zugriff und verschenken jedes Sicherheitsmodell in das einheitliche Portal. Jede zusammengeführte Workload (z. B. MDO oder MDE) verfügt über einen eigenen rollenbasierten Zugriff. Die bereits in den Produkten enthaltenen Rollen werden automatisch im Microsoft 365 Sicherheitsportal zusammengeführt. Rollen und Berechtigungen für MCAS werden jedoch weiterhin in MCAS verarbeitet.

## <a name="what-to-expect"></a>Das erwartet Sie

Alle Sicherheitsinhalte, die Sie im Office 365 Security & Compliance Center (protection.office.com) und im Microsoft Defender Security Center (securitycenter.microsoft.com) verwenden, finden Sie jetzt im *Microsoft 365 Security Center*.

Microsoft 365 Security Center hilft Sicherheitsteams dabei, Angriffe zu untersuchen und darauf zu reagieren, indem Signale aus verschiedenen Workloads in eine Reihe von einheitlichen Umgebungen für Folgendes integriert werden:

- Vorfälle und Benachrichtigungen
- Suchen
- Info-Center
- Bedrohungsanalyse

Das Microsoft 365 Security Center hebt beim Zusammenführen von Microsoft Defender für Office 365 und Microsoft Defender für Endpunkt *Einheit, Klarheit und gemeinsame Ziele* hervor. Die Zusammenführung basierte auf den unten aufgeführten Prioritäten und wurde ohne Einbußen an den Funktionen vorgenommen, die jede Sicherheitssuite in die Kombination von:

- Allgemeine Bausteine
- Allgemeine Terminologie
- Allgemeine Entitäten
- Featureparität mit anderen Workloads

> [!NOTE]
> Auf das einheitliche Microsoft 365 Security Center kann zugegriffen werden, ohne dass Kunden Migrationsschritte ausführen oder eine neue Lizenz erwerben müssen. Beispielsweise kann auf dieses neue Portal für Administratoren mit einem E3-Abonnement zugegriffen werden, genau wie auf diejenigen mit Microsoft Defender für Office 365 Plan 1 und Plan 2. Exchange Online Protection- oder MDO Plan 1-Kunden werden jedoch nur die Sicherheitsfeatures angezeigt, die ihre Abonnementlizenz unterstützt. Das Ziel des neuen Centers besteht darin, die Sicherheit zu zentralisieren.

## <a name="unified-investigations"></a>Vereinheitlichte Untersuchungen

Durch das Zusammenstellen von Sicherheitscentern wird ein einzelner Ort für die Untersuchung von Sicherheitsvorfällen über Microsoft 365 hinweg erstellt. Ein **primäres** Beispiel sind Vorfälle unter **Vorfällen & Warnungen** in der Schnellstartleiste des Microsoft 365 Security Centers.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Security Center.":::

Wenn Sie einen Vorfallnamen auswählen, wird eine Seite angezeigt, die den Wert der Zusammenführung von Sicherheitscentern veranschaulicht.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Beispiel für die Seite &quot;Zusammenfassung&quot; für einen Vorfall im Microsoft 365 Security Center":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

Oben auf einer Vorfallseite werden die **Registerkarten "Zusammenfassung",** **"Warnungen",** **"Geräte",** **"Benutzer",** **"Postfächer",** **"Untersuchungen"** und **"Nachweise"** angezeigt. Wählen Sie diese Registerkarten aus, um ausführlichere Informationen zu finden. Auf der Registerkarte **"Benutzer"** werden beispielsweise Informationen für Benutzer aus zusammengeführten Workloads (Microsoft Defender für Endpunkt, Microsoft Defender for Identity und Microsoft Cloud App Security) sowie eine Reihe von Quellen angezeigt, z. B. lokale Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD) und Identitätsanbieter von Drittanbietern. Weitere Informationen finden Sie unter Untersuchen von [Benutzern.](investigate-users.md)

Nehmen Sie sich Zeit, um die Vorfälle in Ihrer Umgebung zu überprüfen, führen Sie einen Drilldown zu diesen Registerkarten durch, und üben Sie es, ein Verständnis dafür zu entwickeln, wie Sie auf die Informationen zugreifen können, die für Vorfälle für verschiedene Arten von Bedrohungen bereitgestellt werden.

Weitere Informationen finden Sie [unter Vorfälle im Microsoft 365 Security Center.](incidents-overview.md)

## <a name="improved-processes"></a>Verbesserte Prozesse

Allgemeine Steuerelemente und Inhalte werden entweder an derselben Stelle angezeigt oder sind zu einem Datenfeed zusammengefasst, wodurch sie einfacher zu finden sind. Beispielsweise einheitliche Einstellungen.

### <a name="unified-settings"></a>Einheitliche Einstellungen

![auf "Rollen" geklickt und die Seite "Einstellungen" geöffnet, die allgemeine Einstellungen, Berechtigungen, APIs und Regeln enthält. Wählen Sie „Berechtigungen“ und dann „Rollen“ aus. Zeigt alle Rollen an](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Berechtigungen und Rollen

![Seite "Berechtigungen und Rollen" mit den Endpunkten "Rollen und Gruppen", "Rollen" und "Gerätegruppen".](../../media/converged-roles-5.png)

 Der Zugriff auf das Microsoft 365 Security Center ist mit globalen Azure Active Directory-Rollen oder mit benutzerdefinierten Rollen konfiguriert. Für Defender für Endpunkt, siehe [Zuweisen des Benutzerzugriffs auf das Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access). Für Defender für Office 365, siehe [Berechtigungen im Microsoft 365 Compliance Center und Microsoft 365 Security Center](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Weitere Informationen zum [Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md)
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

> [!TIP]
> Es gibt viele andere Lernmöglichkeiten in [Microsoft Learn.](https://docs.microsoft.com/e/learn/) Sie finden Zertifizierungsschulungen wie [Kurs MS-500T02-A: Implementieren von Microsoft 365 Threat Protection.](https://docs.microsoft.com/learn/certifications/courses/ms-500t02)

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
- [Das Info-Center](m365d-action-center.md)
- [Gefahrensuche über Geräte, E-Mails, Apps und Identitäten hinweg](./advanced-hunting-query-emails-devices.md)
- [Regeln für die benutzerdefinierte Erkennung](./custom-detection-rules.md)
- [Benachrichtigungen für E-Mail & Zusammenarbeit](../../compliance/alert-policies.md#default-alert-policies)
- [Erstellen einer Phishingangriff-Simulation](../office-365-security/attack-simulation-training.md) und [Erstellen einer Nutzlast für die Schulung Ihrer Teams](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center](overview-security-center.md)
- [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)