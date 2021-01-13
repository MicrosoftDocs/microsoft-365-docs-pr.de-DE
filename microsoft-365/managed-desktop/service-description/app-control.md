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

Die App-Steuerung ist eine optionale Sicherheitspraxis in Microsoft Managed Desktop, die die Ausführung von Code auf Clientgeräten einschränkt. Dieses Steuerelement verringert das Risiko von Schadsoftware oder bösartigen Skripts, indem nur Code ausgeführt werden darf, der von einer vom Kunden genehmigten Liste von Herausgebern signiert wurde. Dieses Steuerelement bietet zahlreiche Sicherheitsvorteile, aber es dient in erster Linie dem Schutz von Daten und Identitäten vor clientbasierten Exploits.

Microsoft Managed Desktop vereinfacht die Verwaltung von App-Steuerungsrichtlinien, indem eine Basisrichtlinie erstellt wird, die zentrale Produktivitätsszenarien ermöglicht. Sie können die Vertrauensstellung auf andere Signierer erweitern, die für die Apps und Skripts in Ihrer Umgebung spezifisch sind. 


Jede Sicherheitstechnologie erfordert ein Gleichgewicht zwischen Benutzererfahrung, Sicherheit und Kosten. Die App-Kontrolle verringert die Bedrohung durch Schadsoftware in Ihrer Umgebung, aber es gibt Konsequenzen für den Benutzer und weitere Aktionen für Ihren IT-Administrator.

**Zusätzliche Sicherheit:**

Apps oder Skripts, denen die Richtlinie für die App-Steuerung nicht vertraut, werden für die Ausführung auf Geräten gesperrt.

**Ihre zusätzlichen Zuständigkeiten:**

- Sie sind für das Testen Ihrer Apps verantwortlich, um festzustellen, ob sie durch die Anwendungssteuerungsrichtlinie blockiert werden.
- Wenn eine App blockiert ist (oder wäre), sind Sie dafür verantwortlich, die erforderlichen Signierdetails zu identifizieren und eine Änderung über das Verwaltungsportal anfordert.

**Verantwortlichkeiten von Microsoft Managed Desktop:**

- Microsoft Managed Desktop verwaltet die Basisrichtlinie, die #A0 wie M365-Apps, Windows, Teams, OneDrive und vieles mehr ermöglicht.
- Microsoft Managed Desktop fügt Ihre vertrauenswürdigen Signierer ein und stellt die aktualisierte Richtlinie auf Ihren Geräten zur Verfügung.


## <a name="managing-trust-in-applications"></a>Verwalten der Vertrauensstellung in Anwendungen

Microsoft Managed Desktop stellt eine Basisrichtlinie zusammen, die den Kernkomponenten von Microsoft-Technologien vertraut. Anschließend fügen Sie *eine Vertrauensstellung* für Ihre eigenen Anwendungen und Skripts hinzu, indem Sie Microsoft Managed Desktop darüber informieren, welchen Anwendungen Sie bereits vertrauen.

### <a name="base-policy"></a>Basisrichtlinie

Microsoft Managed Desktop erstellt und verwaltet in Zusammenarbeit mit Microsoft Cybersicherheitsexperten eine Standardrichtlinie, die die meisten über Microsoft Intune bereitgestellten Apps ermöglicht und gleichzeitig gefährliche Aktivitäten wie die Codekompilierung oder die Ausführung nicht vertrauenswürdiger Dateien blockiert.

Die Basisrichtlinie verfolgt den folgenden Ansatz zum Einschränken der Softwareausführung:

- Von Administratoren ausgeführte Dateien dürfen ausgeführt werden.
- Dateien an Speicherorten, *die sich* nicht in beschreibbaren Verzeichnissen befinden, dürfen ausgeführt werden.
- Dateien werden von einem [vertrauenswürdigen Signer signiert.](#signer-requests)
- Die meisten von Microsoft signierten Dateien werden ausgeführt, einige werden jedoch blockiert, um Aktionen mit hohem Risiko wie die Codekompilierung zu verhindern.


Wenn ein anderer Benutzer als ein Administrator einem Gerät eine App oder ein Skript hinzugefügt haben könnte (d. h. es befindet sich in einem benutzerschreibbaren Verzeichnis), lassen wir die Ausführung nicht zu, es sei denn, der Administrator hat dies ausdrücklich zugelassen. Wenn ein Benutzer versucht, Schadsoftware zu installieren, wenn ein Sicherheitsrisiko in einer App versucht, Schadsoftware zu installieren, oder wenn ein Benutzer absichtlich versucht, eine nicht autorisierte App oder ein nicht autorisiertes Skript auszuführen, stoppt unsere Richtlinie die Ausführung.

### <a name="signer-requests"></a>Signieranforderungen

Sie teilen uns mit, welche Apps von Softwareherausgebern bereitgestellt werden, denen Sie vertrauen, indem Sie eine *Signieranforderung einreichen.* Auf diese Weise fügen wir diese Vertrauensinformationen der grundlegenden Anwendungssteuerungsrichtlinie hinzu und lassen zu, dass mit dem Zertifikat dieses Herausgebers signierte Software auf Ihren Geräten ausgeführt wird.

## <a name="audit-and-enforced-policies"></a>Überwachen und Erzwingen von Richtlinien

Microsoft Managed Desktop verwendet zwei Microsoft Intune-Richtlinien, um die App-Steuerung bereitzustellen:

### <a name="audit-policy"></a>Überwachungsrichtlinie
Diese Richtlinie erstellt Protokolle, um zu erfassen, ob eine App oder ein Skript durch die Richtlinie "Enforced" blockiert würde. Überwachungsrichtlinien erzwingen keine Regeln für die App-Steuerung und dienen zu Testzwecken, um festzustellen, ob für eine Anwendung eine Herausgeberbefreiung erforderlich ist. Warnungen (8003- oder 8006-Ereignisse) werden in der Ereignisanzeige protokolliert, anstatt die Ausführung oder Installation angegebener Apps oder Skripts zu blockieren.

### <a name="enforced-policy"></a>Erzwungene Richtlinie
Diese Richtlinie blockiert die Ausführung nicht vertrauenswürdiger Apps und Skripts und erstellt Protokolle, sobald eine App oder ein Skript blockiert wird. Erzwungene Richtlinien verhindern, dass Standardbenutzer Apps oder Skripts ausführen, die in beschreibbaren Verzeichnissen gespeichert sind.

Auf Geräte in der Testgruppe wird eine Überwachungsrichtlinie angewendet, mit der Sie überprüfen können, ob Anwendungen Probleme verursachen. Alle anderen Gruppen (zuerst, schnell und breit) verwenden eine erzwungene Richtlinie, sodass Benutzer in diesen Gruppen keine nicht vertrauenswürdigen Apps oder Skripts ausführen können.







