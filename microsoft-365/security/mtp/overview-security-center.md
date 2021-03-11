---
title: Microsoft 365 Security Center – Übersicht
description: Vorteile im Microsoft 365 Security Center, in dem Microsoft Defender für Office 365 (MDO) und Microsoft Defender for Endpoint (MDE) mit Microsoft Defender for Identity (MDI) und Microsoft Cloud App Security (MCAS) kombiniert werden. In diesem Artikel werden die Microsoft 365 Security Center-Fortschritte für Administratoren beschrieben.
keywords: Security, Malware, Microsoft 365, M365, Security Center, monitor, report, identities, data, devices, apps
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
ms.openlocfilehash: 87149ab9c99168d62f5114555a46b8bfaee83ab2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712102"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Übersicht über das einheitliche Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender für Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [Ihr Pilotprojekt in der Produktion ausführen.](https://aka.ms/m365d-pilotplaybook)

Das verbesserte **Microsoft 365 Security Center** ( ) kombiniert Schutz, Erkennung, Untersuchung und Reaktion auf E-Mails, Zusammenarbeit, Identität und Gerätebedrohungen in einem zentralen [https://security.microsoft.com](https://security.microsoft.com) Portal.    

Microsoft 365 Security Center vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen wie Microsoft Defender Security Center und dem Office 365 Security & Compliance Center. Das Sicherheitscenter legt Wert auf schnellen Zugriff auf Informationen, einfachere Layouts und das Zusammenbringen verwandter Informationen zur einfacheren Verwendung. Dieses Center umfasst:

- **[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender für Office 365 hilft Organisationen, ihr Unternehmen mit einer Reihe von Funktionen zur Verhinderung, Erkennung, Untersuchung und Suche zum Schutz von E-Mails und Office 365-Ressourcen zu schützen.
- **[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** bietet vorbeugenden Schutz, Erkennung nach Sicherheitsverletzungen, automatisierte Untersuchung und Reaktion auf Geräte in Ihrer Organisation.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** ist Teil der Microsoft *Extended Detection and Response* (XDR)-Lösung, die das Microsoft 365-Sicherheitsportfolio nutzt, um Bedrohungsdaten automatisch domänenübergreifend zu analysieren und ein Bild eines Angriffs auf einem einzelnen Dashboard zu erstellen.

Wenn Sie Informationen zu den Geänderten im Office 365 Security & Compliance Center oder im Microsoft Defender Security Center benötigen, lesen Sie:

- [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Was zu erwarten ist

Alle Sicherheitsinhalte, die Sie im Office 365 Security and Compliance Center (protection.office.com) und im Microsoft Defender Security Center (securitycenter.microsoft.com) verwenden, finden Sie jetzt im *Microsoft 365 Security Center*.

Microsoft 365 Security Center hilft Sicherheitsteams bei der Untersuchung und Reaktion auf Angriffe, indem Signale von verschiedenen Arbeitsauslastungen in einer einzigen, einheitlichen Besensung gesammelt werden:

- Vorfälle & Warnungen
- Hunting
- Info-Center
- Bedrohungsanalyse

Das Microsoft 365 Security Center unterstreicht *Einheitlichkeit,* Klarheit und gemeinsame Ziele bei der Zusammenführung von Microsoft Defender für Office 365 und Microsoft Defender für Endpoint. Die Zusammenführung basierte auf den unten aufgeführten Prioritäten und wurde ohne Beeinträchtigung der Funktionen vorgenommen, die die einzelnen Sicherheitssuiten für die Kombination mit sich gebracht haben:

- Häufige Bausteine
- Allgemeine Terminologie
- Allgemeine Entitäten
- Featureparität mit anderen Workloads

## <a name="unified-investigations"></a>Einheitliche Untersuchungen

Durch die Optimierung von Sicherheitscentern wird ein einzelner Bereich für die Untersuchung von Vorfällen in einer Microsoft 365-Organisation erstellt. Ein primäres Beispiel ist der **Knoten Incidents** beim Schnellstart des Microsoft 365 Security Centers.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Die Seite Vorfälle in MDO.":::

Wenn Sie beispielsweise auf einen Vorfallnamen  mit hohem Schweregrad doppelklicken, gelangen Sie zu einer Seite, die den Vorteil von konvergenden Centern veranschaulicht.

![Mehrstufiger Vorfall mit Rechteeskalation auf mehreren Endpunkten, siehe 16 betroffener Geräte und 9 betroffener Benutzer.](../../media/converged-incident-info-3.png)

> [!TIP]
> Die Registerkarte  Konvergente Benutzer ist ein guter Ort, um Ihre Anfragen zu beginnen. Auf dieser einzelnen Seite werden Informationen für Benutzer aus konvergenten Arbeitsauslastungen (Microsoft Defender for Endpoint, Microsoft Defender for Identity und MCAS, sofern sie genutzt werden) und einer Reihe von Quellen wie lokalem Active Directory, Azure Active Directory, synchronisierten, lokalen und Drittanbieterbenutzern angezeigt. Erfahren Sie mehr [über die neue Benutzererfahrung](investigate-users.md).

Informationen zu Vorfällen zeigen neben betroffenen Postfächern Benutzer-/Identitätsspezifische und risikogefährdete Geräte an. Sie bezieht sich auch auf alle **Untersuchungsinformationen und** gesammelten **Nachweise.** Dies erleichtert Administratoren und Sicherheitsteams das Pivotieren von einer Warnung mit hohem Risiko für die betroffenen Benutzer und Postfächer. Wenn Sie **sich** die Registerkarten Vorfall oben auf dieser Seite anschauen, sind weitere wichtige Sicherheitsdrehpunkte an diesem einzelnen Speicherort verfügbar.

> [!IMPORTANT]
> Am oberen Rand jeder Seite für einen bestimmten Vorfall werden die Registerkarten  **Zusammenfassung** **,** Warnungen , **Geräte**, **Benutzer**, **Postfächer,** Untersuchungen und Nachweise angezeigt. 

Wenn **Sie Untersuchungen** auswählen, wird eine Seite geöffnet, die eine Grafik der durchgeführten Analyse enthält und einen Status (z. B. ausstehende Genehmigung ) zur Behebung auflistet.  Nehmen Sie sich Zeit, um bestimmte Vorfälle in Ihrer Umgebung auszuwählen, einen Drilldown auf diese Registerkarten zu erstellen und ein Profil für verschiedene Arten von Bedrohungen zu erstellen. Die Vertrautheit nützt späteren dringenden Untersuchungen.

## <a name="improved-processes"></a>Verbesserte Prozesse

Allgemeine Steuerelemente und Inhalte werden entweder am gleichen Ort angezeigt oder zu einem Einzigen Datenfeed verdichtet, wodurch die Suche erleichtert wird. Beispielsweise einheitliche Einstellungen.

### <a name="unified-settings"></a>Einheitliche Einstellungen

![klicken Sie auf "Rollen" und öffnen Sie die Seite Einstellungen, die allgemeine Einstellungen, Berechtigungen, APIs und Regeln enthält. Öffnen Sie Berechtigungen und dann Rollen. Zeigt alle Rollen an](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Berechtigungen & Rollen

![Seite & Berechtigungen mit Endpunktrollen & Gruppen, Rollen und Gerätegruppen.](../../media/converged-roles-5.png)

 Der Zugriff auf das Microsoft 365 Security Center ist mit globalen Azure Active Directory-Rollen oder mit benutzerdefinierten Rollen konfiguriert. Informationen zu Defender for Endpoint finden Sie unter [Assign user access to Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access). Informationen zu Defender für Office 365 finden Sie unter [Berechtigungen im Microsoft 365 Compliance Center und Microsoft 365 Security Center](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Weitere Informationen zum Verwalten [des Zugriffs auf Microsoft 365 Defender](mtp-permissions.md)
- Weitere Informationen zum Erstellen [benutzerdefinierter Rollen](custom-roles.md) im Microsoft 365 Security Center

### <a name="integrated-reports"></a>Integrierte Berichte

Berichte werden auch im Microsoft 365 Security Center vereinheitlicht. Administratoren können mit einem allgemeinen Sicherheitsbericht beginnen und in bestimmte Berichte zu Endpunkten, E-Mails und & verzweigen. Die links hier werden dynamisch basierend auf der Arbeitsauslastungskonfiguration generiert.

### <a name="quickly-view-your-microsoft-365-environment"></a>Schnelles Anzeigen Ihrer Microsoft 365-Umgebung

Die **Startseite** zeigt viele der gängigen Karten, die Sicherheitsteams benötigen. Die Zusammensetzung von Karten und Daten hängt von der Benutzerrolle ab. Da das Microsoft 365 Security Center die rollenbasierte Zugriffssteuerung verwendet, werden verschiedenen Rollen Karten mit bedeutungsbasierter Bedeutung für ihre täglichen Aufträge zur Verfügung stehen.  

Diese Informationen auf einen Blick helfen Ihnen, mit den neuesten Aktivitäten in Ihrer Organisation mithalten zu können. Das Microsoft 365 Security Center vereint Signale aus verschiedenen Quellen, um eine ganzheitliche Ansicht Ihrer Microsoft 365-Umgebung zu präsentieren.

Die Karten fallen in die folgenden Kategorien:

- **Identitäten**– Überwachen Sie die Identitäten in Ihrer Organisation, und verfolgen Sie verdächtige oder riskante Verhaltensweisen. [Weitere Informationen zum Identitätsschutz](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).
- **Daten** – Helfen Sie beim Nachverfolgen von Benutzeraktivitäten, die zu einer nicht autorisierten Offenlegung von Daten führen können.
- **Geräte** – Erhalten Sie aktuelle Informationen zu Warnungen, Verletzungsaktivitäten und anderen Bedrohungen auf Ihren Geräten.
- **Apps** – Erhalten Sie Einblick in die Verwendung von Cloud-Apps in Ihrer Organisation. [Erfahren Sie mehr über von Cloud App Security ermittelte Apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).

## <a name="threat-analytics-with-better-data-coverage"></a>Bedrohungsanalyse mit besserer Datenabdeckung
Verfolgen und reagieren Sie auf neue Bedrohungen mit der folgenden integrierten Microsoft 365 Defender Threat Analytics-Erfahrung:

- Bessere Datenabdeckung zwischen Microsoft Defender for Endpoint und Microsoft Defender für Office 365, wodurch eine kombinierte Vorfallverwaltung, automatische Untersuchung, Korrektur und proaktive oder reaktive Bedrohungssuche in domänenübergreifend möglich sind. 
- E-Mail-bezogene Erkennungen und Gegenmaßnahmen von Microsoft Defender für Office 365 zusätzlich zu den bereits von Microsoft Defender for Endpoint verfügbaren Endpunktdaten.
- Eine Ansicht von bedrohungsbezogenen Vorfällen, die Warnungen in End-to-End-Angriffsmeldungen in Microsoft Defender for Endpoint und Microsoft Defender für Office 365 aggregieren, um die Arbeitswarteschlange zu reduzieren und Ihre Untersuchung zu vereinfachen und zu beschleunigen.
- Angriffsversuche, die von Microsoft 365 Defender-Lösungen erkannt und blockiert werden. Es gibt auch Daten, die Sie verwenden können, um vorbeugende Maßnahmen zu ergreifen, um das Risiko einer weiteren Gefährdung zu verringern und die Ausfallsicherheit zu erhöhen. 
- Erweitertes Design, das aktionenfähige Informationen ins Rampenlicht rückt, damit Sie Daten schnell identifizieren können, um sich dringend auf die Berichte zu konzentrieren, sie zu untersuchen und zu nutzen.

## <a name="a-centralized-learning-hub"></a>Ein zentraler Lernhub

Das Microsoft 365 Security Center enthält einen Lernhub, der offizielle Anleitungen aus Ressourcen wie dem Microsoft-Sicherheitsblog, der Microsoft-Sicherheitsgemeinschaft auf YouTube und der offiziellen Dokumentation unter docs.microsoft.com.

Innerhalb des Lernhubs ist die Anleitung zur E-Mail-&-Zusammenarbeit (Microsoft Defender für Office 365 oder MDO) seiteseitig mit Endpoint (Microsoft Defender for Endpoint oder MDE) und Microsoft 365 Defender-Lernressourcen.

Der Lernhub wird mit Lernpfaden geöffnet, die sich um Themen wie "How to Investigate Using Microsoft 365 Defender?" herum organisieren. und "Microsoft Defender for Office 365 Best Practices". Dieser Abschnitt wird derzeit von der Sicherheitsproduktgruppe in Microsoft kuratiert. Jeder Lernpfad spiegelt eine projizierte Zeit wider, die benötigt wird, um die Konzepte zu durcharbeiten. Beispielsweise wird "Schritte, die unternommen werden müssen, wenn ein Microsoft Defender for Office 365-Benutzerkonto gefährdet ist" auf 8 Minuten projiziert und ist ein wertvolles Lernprojekt.

Nachdem Sie auf den Inhalt geklickt haben, kann es hilfreich sein, diese Website als Lesezeichen zu markieren und Lesezeichen in einem Ordner "Sicherheit" oder "Kritisch" zu organisieren. Klicken Sie auf den Link Alle anzeigen im Hauptbereich, um alle Lernpfade zu sehen.

> [!NOTE]
> Es gibt  hilfreiche Filter am oberen Rand des Microsoft 365 Security Center-Lernhubs, mit dem Sie zwischen Produkten wählen können (derzeit Microsoft 365 Defender, Microsoft Defender for Endpoint und Microsoft Defender für Office 365). Beachten Sie, dass die Anzahl der Lernressourcen für jeden Abschnitt aufgelistet ist, wodurch lernende Benutzer nachverfolgen können, wie viele Ressourcen sie für Schulungen und Schulungen zur Verfügung haben.
>
> Zusammen mit dem Produktfilter werden aktuelle Themen, Ressourcentypen (von Videos bis Webinare), Ebenen der Vertrautheit oder Erfahrung mit Sicherheitsbereichen, Sicherheitsrollen und Produktfeatures aufgelistet.

## <a name="send-us-your-feedback"></a>Senden Sie uns Ihr Feedback

Wir benötigen Ihr Feedback. We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

Sie können auch Feedback aus diesem Artikel hinterlassen. Im Abschnitt "Feedback" am Ende unter "Feedback übermitteln und anzeigen für" sind die Optionen *Dieses Produkt* oder *Diese Seite*.

Verwenden Sie die **Schaltfläche Dieses Produkt** für *Produktfeedback:*

1. Wählen *Sie Dieses Produkt* am Ende des Artikels aus.
    1. Klicken Sie mit der rechten Maustaste auf die Schaltfläche und auf eine neue Registerkarte öffnen, wenn Sie diese Anweisungen weiter lesen möchten.
2. Dadurch wird zum **UserVoice-Forum navigiert.**
3. Sie haben 2 Optionen:
    1. Bildlauf nach unten zum Textfeld Wie können wir die Compliance verbessern oder Ihre Benutzer *besser in Office 365 schützen?* und in *Microsoft 365 Security Center einfügen.* Sie können die Ergebnisse nach einer Idee wie Ihrer suchen und diese abstimmen oder die Schaltfläche für **Neue Idee veröffentlichen verwenden.**
    1. Wenn Sie sich sicher sind, dass dieses Problem bereits gemeldet wurde und ihr  Profil mit einer Stimme (oder Abstimmungen) erhöhen möchten, verwenden Sie das Feld Feedback geben auf der rechten Seite von UserVoice. Suchen Sie *nach Microsoft 365 Security Center,* suchen Sie **das Problem,** und verwenden Sie die Abstimmungsschaltfläche, um den Status zu erhöhen.

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
- [Microsoft Defender for Endpoint im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)
