---
title: Microsoft 365 Security Center – Übersicht
description: Vorteile im Microsoft 365 Security Center, das Microsoft Defender für Office 365 (MDO) und Microsoft Defender for Endpoint (MDE) mit Microsoft Defender for Identity (MDI) und Microsoft Cloud App Security (MCAS) kombiniert. In diesem Artikel werden die Fortschritte im Microsoft 365 Security Center für Administratoren beschrieben.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, überwachen, Bericht, Identitäten, Daten, Geräte, Apps
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
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167201"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Übersicht über das einheitliche Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender für Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)

Das verbesserte **Microsoft 365 Security Center** ( ) kombiniert Schutz, Erkennung, Untersuchung und Reaktion auf E-Mails, Zusammenarbeit, Identität und Gerätebedrohungen in einem zentralen [https://security.microsoft.com](https://security.microsoft.com) Portal.    

Das Microsoft 365 Security Center vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen wie Microsoft Defender Security Center und dem Office 365 Security & Compliance Center. Das Security Center hebt den schnellen Zugriff auf Informationen, einfachere Layouts und das Zusammenbringen verwandter Informationen zur einfacheren Verwendung hervor. Dieses Center umfasst:

- **[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender für Office 365 hilft Organisationen dabei, ihr Unternehmen mit einer Reihe von Funktionen zur Verhinderung, Erkennung, Untersuchung und Suche zum Schutz von E-Mails und Office 365-Ressourcen zu schützen.
- **[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** bietet vorbeugenden Schutz, Erkennung nach einer Verletzung, automatisierte Untersuchung und Reaktion auf Geräte in Ihrer Organisation.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** ist Teil der Erweiterten Erkennungs- und Reaktionslösung *(Extended Detection and Response,* XDR) von Microsoft, die das Microsoft 365-Sicherheitsportfolio nutzt, um Bedrohungsdaten automatisch domänenübergreifend zu analysieren und ein Bild eines Angriffs auf einem einzelnen Dashboard zu erstellen.

Wenn Sie Informationen zu den Geänderten im Office 365 Security & Compliance Center oder im Microsoft Defender Security Center benötigen, lesen Sie:

- [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Was Sie erwarten können

Alle Sicherheitsinhalte, die Sie im Office 365 Security and Compliance Center (protection.office.com) und im Microsoft Defender Security Center (securitycenter.microsoft.com) verwenden, befinden sich jetzt im *Microsoft 365 Security Center.*

Das Microsoft 365 Security Center unterstützt Sicherheitsteams bei der Untersuchung und Reaktion auf Angriffe, indem Signale von verschiedenen Workloads in einer einzigen, einheitlichen Erfahrung eingespeisten werden:

- Vorfälle & Warnungen
- Suche
- Info-Center
- Bedrohungsanalyse

Das Microsoft 365 Security Center unterstreicht *Einheitlichkeit,* Klarheit und gemeinsame Ziele bei der Zusammenführung von Microsoft Defender für Office 365 und Microsoft Defender for Endpoint. Die Zusammenführung basierte auf den unten aufgeführten Prioritäten und wurde ohne Beeinträchtigung der Funktionen vorgenommen, die jede Sicherheitssuite zu der Kombination gebracht hat:

- Allgemeine Bausteine
- Allgemeine Terminologie
- Allgemeine Entitäten
- Featureparität mit anderen Workloads

## <a name="unified-investigations"></a>Einheitliche Untersuchungen

Durch die Optimierung von Sicherheitscentern wird ein einzelner Bereich für die Untersuchung von Vorfällen in einer Microsoft 365-Organisation erstellt. Ein primäres Beispiel ist der Knoten **"Vorfälle"** auf der Schnellstartstart-Website des Microsoft 365 Security Centers.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Die Seite &quot;Vorfälle&quot; in MDO.":::

Wenn Sie beispielsweise auf einen Vorfallnamen  mit hohem Schweregrad doppelklicken, gelangen Sie zu einer Seite, auf der die Vorteile der Konversierungscenter veranschaulicht werden.

![Mehrstufiger Vorfall mit Berechtigungseskalation auf mehreren Endpunkten, zeigt 16 betroffener Geräte und neun betroffener Benutzer.](../../media/converged-incident-info-3.png)

> [!TIP]
> Die Registerkarte  "Konvergente Benutzer" ist ein guter Ort, um Ihre Anfragen zu beginnen. Auf dieser einzelnen Seite werden Informationen für Benutzer aus konvergenten Workloads (Microsoft Defender für Endpoint, Microsoft Defender for Identity und MCAS, sofern sie genutzt werden) und einer Reihe von Quellen angezeigt, z. B. lokales Active Directory, Azure Active Directory, synchronisierte, lokale und Drittanbieterbenutzer. Erfahren Sie mehr über [die neue Benutzererfahrung.](investigate-users.md)

Vorfallinformationen enthalten Neben den betroffenen Postfächern Benutzer-/Identitätsinformationen und Gefährdete Geräte. Sie bezieht sich auch auf alle **Untersuchungsinformationen und** erfasste **Nachweise.** Dies erleichtert Administratoren und Sicherheitsteams das Pivotieren von einer Warnung mit hohem Risiko für die betroffenen Benutzer und Postfächer. Wenn Sie sich **die Registerkarten** "Vorfälle" oben auf dieser Seite anschauen, stehen an diesem zentralen Ort weitere wichtige Sicherheits pivots zur Verfügung.

> [!IMPORTANT]
> Am oberen Rand jeder Seite für einen bestimmten Vorfall sehen Sie die Registerkarten **Zusammenfassung,** Warnungen, Geräte **,** **Benutzer,** **Postfächer,** Untersuchungen und Nachweise.   

Wenn **Sie "Untersuchungen"** auswählen, wird eine Seite mit einer Grafik der durchgeführten Analyse geöffnet und ein Status (z. B. ausstehende **Genehmigung)** zur Behebung aufgeführt. Nehmen Sie sich Zeit, um bestimmte Vorfälle in Ihrer Umgebung auszuwählen, führen Sie einen Drilldown zu diesen Registerkarten durch, und erstellen Sie ein Profil für verschiedene Arten von Bedrohungen. Vertrautheit wird bei späteren, dringenden Untersuchungen von Vorteil sein.

## <a name="improved-processes"></a>Verbesserte Prozesse

Allgemeine Steuerelemente und Inhalte werden entweder an derselben Stelle angezeigt oder sind zu einem einzigen Datenfeed zusammengefasst, was die Suche erleichtert. Beispiel: einheitliche Einstellungen.

### <a name="unified-settings"></a>Einheitliche Einstellungen

![Klicken Sie auf "Rollen" und öffnen Sie die Seite "Einstellungen", die allgemeine Einstellungen, Berechtigungen, APIs und Regeln enthält. Öffnen Sie "Berechtigungen" und dann "Rollen". Zeigt alle Rollen an](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Berechtigungen & Rollen

![Seite & "Berechtigungen" mit Endpunktrollen & Gruppen, Rollen und Gerätegruppen.](../../media/converged-roles-5.png)

 Der Zugriff auf das Microsoft 365 Security Center ist mit globalen Azure Active Directory-Rollen oder mithilfe von benutzerdefinierten Rollen konfiguriert. For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access). Informationen zu Defender für Office 365 finden Sie unter ["Berechtigungen" im Microsoft 365 Compliance Center und im Microsoft 365 Security Center.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Weitere Informationen zum Verwalten [des Zugriffs auf Microsoft 365 Defender](mtp-permissions.md)
- Weitere Informationen zum Erstellen [benutzerdefinierter Rollen](custom-roles.md) im Microsoft 365 Security Center

### <a name="integrated-reports"></a>Integrierte Berichte

Berichte sind auch im Microsoft 365 Security Center vereinheitlicht. Administratoren können mit einem allgemeinen Sicherheitsbericht beginnen und in bestimmte Berichte zu Endpunkten, E-Mails und & verzweigen. Die links hier werden dynamisch basierend auf der Konfiguration der Arbeitsauslastung generiert.

### <a name="quickly-view-your-microsoft-365-environment"></a>Schnelles Anzeigen Ihrer Microsoft 365-Umgebung

Auf **der Startseite** werden viele der gängigen Karten angezeigt, die Sicherheitsteams benötigen. Die Zusammensetzung von Karten und Daten hängt von der Benutzerrolle ab. Da das Microsoft 365 Security Center die rollenbasierte Zugriffssteuerung verwendet, sehen verschiedene Rollen Karten, die für ihre täglichen Aufträge aussagekräftiger sind.  

Diese Informationen auf einen Blick helfen Ihnen, mit den neuesten Aktivitäten in Ihrer Organisation auf dem Neuesten zu bleiben. Das Microsoft 365 Security Center vereint Signale aus verschiedenen Quellen, um eine ganzheitliche Ansicht Ihrer Microsoft 365-Umgebung zu präsentieren.

Die Karten fallen in die folgenden Kategorien:

- **Identitäten**– Überwachen Sie die Identitäten in Ihrer Organisation, und verfolgen Sie verdächtige oder riskante Verhaltensweisen. [Weitere Informationen zum Identitätsschutz.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Daten** – Helfen Beim Nachverfolgen von Benutzeraktivitäten, die zu einer nicht autorisierten Offenlegung von Daten führen können.
- **Geräte** – Erhalten Sie aktuelle Informationen zu Warnungen, Sicherheitsverletzungen und anderen Bedrohungen auf Ihren Geräten.
- **Apps** – Erhalten Sie Einen Einblick in die Verwendung von Cloud-Apps in Ihrer Organisation. [Erfahren Sie mehr über von Cloud App Security ermittelte Apps.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Bedrohungsanalyse mit besserer Datenabdeckung
Verfolgen und reagieren Sie auf neue Bedrohungen mit der folgenden integrierten Microsoft 365 Defender Threat Analytics-Erfahrung:

- Bessere Datenabdeckung zwischen Microsoft Defender für Endpoint und Microsoft Defender für Office 365, wodurch eine kombinierte Vorfallverwaltung, automatische Untersuchung, Behebung und proaktive oder reaktive Suche nach bedrohungen domänenübergreifend möglich ist. 
- E-Mail-bezogene Erkennungen und Gegenmaßnahmen von Microsoft Defender für Office 365, zusätzlich zu den bereits von Microsoft Defender für Endpoint verfügbaren Endpunktdaten.
- Eine Ansicht von bedrohungsbezogenen Vorfällen, die Warnungen in End-to-End-Angriffsgeschichten in Microsoft Defender für Endpoint und Microsoft Defender für Office 365 aggregiert, um die Arbeitswarteschlange zu reduzieren sowie Ihre Untersuchung zu vereinfachen und zu beschleunigen.
- Angriffsversuche, die von Microsoft 365 -Defender-Lösungen erkannt und blockiert werden. Es gibt auch Daten, die Sie verwenden können, um vorbeugende Maßnahmen zu ergreifen, die das Risiko einer weiteren Gefährdung verringern und die Resilienz erhöhen. 
- Verbessertes Design, das aktionenfähige Informationen in den Blickpunkt rückt, damit Sie Daten schnell identifizieren können, um sich dringend auf die Berichte zu konzentrieren, sie zu untersuchen und zu nutzen.

## <a name="a-centralized-learning-hub"></a>Ein zentraler Lernhub

Das Microsoft 365 Security Center enthält einen Lernhub, der offizielle Anleitungen aus Ressourcen wie dem Microsoft-Sicherheitsblog, der Microsoft-Sicherheits-Community auf YouTube und der offiziellen Dokumentation auf docs.microsoft.com.

Innerhalb des Lernhubs ist die Anleitung zur E-Mail-&-Zusammenarbeit (Microsoft Defender für Office 365 oder MDO) mit Endpoint (Microsoft Defender for Endpoint oder MDE) und Microsoft 365 Defender Lernressourcen nebeneinander.

Der Lernhub wird mit Lernpfaden geöffnet, die sich um Themen wie "Untersuchen der Verwendung von Microsoft 365 Defender?" herum organisieren. und "Bewährte Methoden für Microsoft Defender für Office 365". Dieser Abschnitt wird derzeit von der Sicherheitsproduktgruppe in Microsoft behandelt. Jeder Lernpfad spiegelt eine projizierte Zeit wider, die für die Durcharbeitung der Konzepte benötigt wird. Beispiel: "Schritte, die bei einer Berücksichtigung eines Microsoft Defender für Office 365-Benutzerkontos unternommen werden müssen", werden 8 Minuten dauern und sind ein wertvolles Lernprojekt.

Nachdem Sie auf den Inhalt geklickt haben, kann es hilfreich sein, diese Website mit einem Lesezeichen zu versehen und Lesezeichen in einem Ordner "Sicherheit" oder "Kritisch" zu organisieren. Um alle Lernpfade zu sehen, klicken Sie im Hauptbereich auf "Alle anzeigen".

> [!NOTE]
> Es gibt  hilfreiche Filter am oberen Rand des Microsoft 365 Security Center-Lernhubs, mit dem Sie zwischen Produkten (derzeit Microsoft 365 Defender, Microsoft Defender für Endpoint und Microsoft Defender für Office 365) wählen können. Beachten Sie, dass die Anzahl der Lernressourcen für jeden Abschnitt aufgeführt ist, wodurch Lernende nachverfolgen können, über wie viele Ressourcen sie für Schulungen und Schulungen verfügen.
>
> Zusammen mit dem Produktfilter werden aktuelle Themen, Ressourcentypen (von Videos bis Webinare), Erfahrungsstufen mit Sicherheitsbereichen, Sicherheitsrollen und Produktfeatures aufgelistet.

## <a name="send-us-your-feedback"></a>Senden Sie uns Ihr Feedback

Wir benötigen Ihr Feedback. We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

Sie können auch Feedback aus diesem Artikel abgeben. Im Abschnitt "Feedback" am Ende unter "Senden und Anzeigen von Feedback für" sind die Optionen dieses *Produkt* oder *diese Seite*.

Verwenden Sie **die Schaltfläche "Dieses Produkt"** für *Produktfeedback:*

1. Wählen *Sie dieses Produkt* am Ende des Artikels aus.
    1. Klicken Sie mit der rechten Maustaste auf die Schaltfläche und dann auf "In einer neuen Registerkarte öffnen", wenn Sie diese Wegbeschreibungen weiter lesen möchten.
2. Dies navigiert zum **UserVoice-Forum.**
3. Sie haben zwei Optionen:
    1. Scrollen Sie nach unten zum Textfeld Wie können wir die Compliance verbessern oder Ihre Benutzer *in Office 365* besser schützen? Und fügen Sie sie im *Microsoft 365 Security Center ein.* Sie können die Ergebnisse nach einer Idee wie Ihrer suchen und sie abstimmen oder die Schaltfläche für **eine neue Idee posten verwenden.**
    1. Wenn Sie sicher sind, dass dieses Problem bereits gemeldet wurde und ihr Profil  mit einer Stimme (oder Stimmen) erhöhen möchten, verwenden Sie das Feld "Feedback geben" auf der rechten Seite von UserVoice. Suchen Sie *nach Microsoft 365 Security Center,* suchen Sie das **Problem,** und verwenden Sie die Abstimmungsschaltfläche, um den Status zu erhöhen.

Verwenden *Sie diese Seite* für Feedback zum Artikel selbst. Vielen Dank für Ihr Feedback. Ihre Stimme hilft uns, Produkte zu verbessern.

### <a name="explore-what-the-security-center-has-to-offer"></a>Entdecken Sie, was das Security Center zu bieten hat

Erkunden Sie die Features und Funktionen im Microsoft 365 Security Center:

- [Verwalten von Vorfällen und Warnungen](manage-incidents.md)
- [Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen](threat-analytics.md)
- [Das Info-Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Suche nach Bedrohungen auf allen Geräten, E-Mails, Apps und Identitäten](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Benutzerdefinierte Erkennungsregeln](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Benachrichtigungen & Zusammenarbeit per E-Mail](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Erstellen einer Phishingangriffssimulation](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) und [Erstellen einer Nutzlast für die Schulung Ihrer Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center](overview-security-center.md)
- [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)
