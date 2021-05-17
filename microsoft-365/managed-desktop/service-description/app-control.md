---
title: App-Steuerung
description: Verwenden von App-Steuerelementen und -Vertrauensstellungen mit Anwendungen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841303"
---
# <a name="app-control"></a>App-Steuerung

Die App-Steuerung ist eine optionale Sicherheitspraxis in Microsoft Managed Desktop, die die Ausführung von Code auf Clientgeräten einschränkt. Dieses Steuerelement verringert das Risiko von Schadsoftware oder bösartigen Skripts, indem nur Code ausgeführt werden darf, der von einer vom Kunden genehmigten Liste von Herausgebern signiert wurde. Dieses Steuerelement bietet zahlreiche Sicherheitsvorteile, zielt jedoch in erster Linie auf den Schutz von Daten und Identität vor clientbasierten Exploits ab.

Microsoft Managed Desktop vereinfacht die Verwaltung von App-Steuerelementrichtlinien, indem eine Basisrichtlinie erstellt wird, die zentrale Produktivitätsszenarien ermöglicht. Sie können die Vertrauensstellung auf andere Signierer erweitern, die für die Apps und Skripts in Ihrer Umgebung spezifisch sind. 


Jede Sicherheitstechnologie erfordert ein Gleichgewicht zwischen Benutzererfahrung, Sicherheit und Kosten. Die App-Steuerung reduziert die Bedrohung durch schadsoftware in Ihrer Umgebung, es gibt jedoch Folgen für den Benutzer und weitere Aktionen für Ihren IT-Administrator.

**Zusätzliche Sicherheit:**

Apps oder Skripts, denen die App-Steuerelementrichtlinie nicht vertraut, können nicht auf Geräten ausgeführt werden.

**Ihre zusätzlichen Verantwortlichkeiten:**

- Sie sind für das Testen Ihrer Apps verantwortlich, um zu ermitteln, ob sie von der Anwendungssteuerungsrichtlinie blockiert würden.
- Wenn eine App blockiert ist (oder wäre), sind Sie dafür verantwortlich, die erforderlichen Signierdetails zu identifizieren und eine Änderung über das Administratorportal anfordern.

**Microsoft Managed Desktop Verantwortlichkeiten:**

- Microsoft Managed Desktop verwaltet die Basisrichtlinie, die wichtige Microsoft-Produkte wie M365 Apps, Windows, Teams, OneDrive und so weiter ermöglicht.
- Microsoft Managed Desktop werden Ihre vertrauenswürdigen Signierer eingefügt und die aktualisierte Richtlinie auf Ihren Geräten bereitgestellt.


## <a name="managing-trust-in-applications"></a>Verwalten von Vertrauensstellungen in Anwendungen

Microsoft Managed Desktop eine Basisrichtlinie, die den Kernkomponenten von Microsoft-Technologien vertraut. Anschließend fügen Sie *Vertrauen* für Ihre eigenen Anwendungen und Skripts hinzu, indem Sie Microsoft Managed Desktop denen Sie bereits vertrauen.

### <a name="base-policy"></a>Basisrichtlinie

Microsoft Managed Desktop erstellt und verwaltet in Zusammenarbeit mit Microsoft Cybersecurity-Experten eine Standardrichtlinie, die die meisten über Microsoft Intune bereitgestellten Apps ermöglicht und gleichzeitig gefährliche Aktivitäten wie die Codekompilierung oder Ausführung nicht vertrauenswürdiger Dateien blockiert.

Die Basisrichtlinie verfolgt den folgenden Ansatz zum Einschränken der Softwareausführung:

- Von Administratoren ausgeführte Dateien können ausgeführt werden.
- Dateien an Speicherorten, *die* sich nicht in beschreibbaren Verzeichnissen befinden, können ausgeführt werden.
- Dateien werden von einem vertrauenswürdigen [Signier signiert.](#signer-requests)
- Die meisten von Microsoft signierten Dateien werden ausgeführt, einige werden jedoch blockiert, um aktionen mit hohem Risiko wie die Codekompilierung zu verhindern.


Wenn ein anderer Benutzer als ein Administrator einem Gerät eine App oder ein Skript hinzugefügt haben könnte (d. h. es befindet sich in einem benutzerschreibbaren Verzeichnis), wird die Ausführung nicht zugelassen, es sei denn, es wurde bereits ausdrücklich von einem Administrator zugelassen. Wenn ein Benutzer versucht, Schadsoftware zu installieren, wenn eine Sicherheitslücke in einer App, die der Benutzer ausgeführt hat, versucht, Schadsoftware zu installieren, oder wenn ein Benutzer absichtlich versucht, eine nicht autorisierte App oder ein nicht autorisiertes Skript auszuführen, wird die Ausführung durch unsere Richtlinie beendet.

### <a name="signer-requests"></a>Signeranforderungen

Sie informieren uns darüber, welche Apps von Softwareherausgebern bereitgestellt werden, denen Sie vertrauen, indem Sie eine *Signieranforderung einreichen.* Auf diese Weise fügen wir diese Vertrauensinformationen der Basisanwendungssteuerungsrichtlinie hinzu und ermöglichen die Ausführung von Software, die mit dem Zertifikat dieses Herausgebers signiert ist, auf Ihren Geräten.

## <a name="audit-and-enforced-policies"></a>Überwachungs- und Erzwungene Richtlinien

Microsoft Managed Desktop verwendet zwei Microsoft Intune, um die App-Steuerung zu ermöglichen:

### <a name="audit-policy"></a>Überwachungsrichtlinie
Diese Richtlinie erstellt Protokolle, um zu erfassen, ob eine App oder ein Skript von der Richtlinie Erzwungen blockiert wird. Überwachungsrichtlinien erzwingen keine Regeln für die App-Kontrolle und dienen zu Testzwecken, um zu ermitteln, ob für eine Anwendung eine Herausgeberfreistellung erforderlich ist. Es protokolliert Warnungen (8003- oder 8006-Ereignisse) in der Ereignisanzeige, anstatt die Ausführung oder Installation von angegebenen Apps oder Skripts zu blockieren.

### <a name="enforced-policy"></a>Erzwungene Richtlinie
Diese Richtlinie blockiert die Ausführung nicht vertrauenswürdiger Apps und Skripts und erstellt Protokolle, sobald eine App oder ein Skript blockiert wird. Erzwungene Richtlinien verhindern, dass Standardbenutzer Apps oder Skripts ausführen, die in beschreibbaren Verzeichnissen gespeichert sind.

Auf Geräten in der Testgruppe wird eine Überwachungsrichtlinie angewendet, damit Sie überprüfen können, ob Anwendungen Probleme verursachen. Alle anderen Gruppen (First, Fast und Broad) verwenden eine Erzwungene Richtlinie, sodass Benutzer in diesen Gruppen nicht vertrauenswürdige Apps oder Skripts nicht ausführen können.







