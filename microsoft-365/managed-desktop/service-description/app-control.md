---
title: App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170721"
---
# <a name="app-control"></a>App-Steuerelement

App-Steuerelement ist eine optionale Sicherheitspraxis in Microsoft Managed Desktop, die die Ausführung von Code auf Clientgeräten einschränkt. Durch dieses Steuerelement wird das Risiko von Schadsoftware oder böswilligen Skripts verringert, da nur Code ausgeführt werden kann, der von einer vom Kunden genehmigten Liste mit Herausgebern signiert wurde. Dieses Steuerelement bietet viele Sicherheitsvorteile, zielt jedoch in erster Linie darauf ab, Daten und Identität vor clientbasierten Exploits zu schützen.

Microsoft Managed Desktop vereinfacht die Verwaltung von App-Steuerelement Richtlinien, indem eine Basisrichtlinie erstellt wird, die Kern Produktivitätsszenarien ermöglicht. Sie können die Vertrauensstellung auf zusätzliche Signaturer erweitern, die für die apps und Skripts in Ihrer Umgebung spezifisch sind. 


Jede Sicherheitstechnologie erfordert ein Gleichgewichtzwischen Benutzerfreundlichkeit, Sicherheit und Kosten. Das App-Steuerelement reduziert die Bedrohung durch Schadsoftware in Ihrer Umgebung, es gibt jedoch Konsequenzen für den Endbenutzer und zusätzliche Aktionen für Ihren IT-Administrator.

**Zusätzliche Sicherheit:**

Für apps oder Skripts, denen die APP-Steuerelement Richtlinie nicht vertraut, wird die Ausführung auf Geräten blockiert.

**Ihre zusätzlichen Aufgaben:**

- Sie sind für das Testen Ihrer Apps verantwortlich, um zu ermitteln, ob Sie von der anwendungssteuerungsrichtlinie blockiert würden.
- Wenn eine APP blockiert ist (oder wäre), sind Sie dafür verantwortlich, die erforderlichen Signer-Details zu identifizieren und eine Änderung über das Verwaltungsportal anzufordern.

**Aufgaben von Microsoft Managed Desktop:**

- Microsoft Managed Desktop verwaltet die Basisrichtlinie, die Kernprodukte von Microsoft wie M365-apps, Windows, Teams, OneDrive usw. aktiviert.
- Microsoft Managed Desktop fügt Ihre vertrauenswürdigen unterzeichnenden ein und stellt die aktualisierte Richtlinie auf Ihren Geräten bereit.


## <a name="managing-trust-in-applications"></a>Verwalten der Vertrauensstellung in Anwendungen

Microsoft Managed Desktop kuratiert eine Basisrichtlinie, die den Kernkomponenten von Microsoft-Technologien vertraut. Sie fügen dann Vertrauenswürdigkeit für Ihre eigenen Anwendungen und Skripts *hinzu* , indem Sie Microsoft Managed Desktop informieren, dem Sie bereits Vertrauen.

### <a name="base-policy"></a>Basisrichtlinie

Microsoft Managed Desktop erstellt und verwaltet in Zusammenarbeit mit Microsoft Cyber-Experten eine Standardrichtlinie, die die meisten in Microsoft InTune bereitgestellten apps aktiviert, während gefährliche Aktivitäten wie die Codekompilierung oder die Ausführung nicht vertrauenswürdiger Dateien blockiert werden.

Die Basisrichtlinie verfolgt die folgende Vorgehensweise zum Einschränken der Softwareausführung:

- Von Administratoren ausgeführte Dateien können ausgeführt werden.
- Dateien an Speicherorten, die sich *nicht* in vom Benutzer beschreibbaren Verzeichnissen befinden, dürfen ausgeführt werden.
- Dateien werden von einem [vertrauenswürdigen Signaturer](#signer-requests)signiert.
- Die meisten von Microsoft signierten Dateien werden ausgeführt, einige werden jedoch blockiert, um Aktionen wie Codekompilierung mit hohem Risiko zu verhindern.


Wenn ein anderer Benutzer als ein Administrator eine APP oder ein Skript einem Gerät hinzugefügt haben könnte (das heißt, es befindet sich in einem Benutzer schreibfähigen Verzeichnis), lässt es sich nicht ausführen, es sei denn, es wurde bereits von einem Administrator ausdrücklich zugelassen. Wenn ein Benutzer versucht, Schadsoftware zu installieren, wenn eine Sicherheitsanfälligkeit in einer APP, die der Benutzer ausführt, versucht, Schadsoftware zu installieren, oder wenn ein Benutzer absichtlich versucht, eine nicht autorisierte APP oder ein unbefugtes Skript auszuführen, wird die Ausführung unserer Richtlinie angehalten.

### <a name="signer-requests"></a>Signer-Anforderungen

Sie informieren uns, welche apps von Softwareanbietern bereitgestellt werden, denen Sie Vertrauen, indem Sie eine *Signer-Anforderung*einreichen. Auf diese Weise fügen wir diese Vertrauensinformationen in die Baseline-anwendungssteuerungsrichtlinie ein und erlauben, dass alle mit dem Zertifikat des Herausgebers signierte Software auf Ihren Geräten ausgeführt wird.

## <a name="audit-and-enforced-policies"></a>Überwachen und Erzwingen von Richtlinien

Microsoft Managed Desktop verwendet zwei Microsoft InTune-Richtlinien, um die APP-Steuerung bereitzustellen:

### <a name="audit-policy"></a>Überwachungsrichtlinie
Mit dieser Richtlinie werden Protokolle erstellt, um festzuhalten, ob eine APP oder ein Skript durch die erzwungene Richtlinie blockiert würde. Überwachungsrichtlinien erzwingen keine app-Steuerelement Regeln und dienen zu Testzwecken, um zu ermitteln, ob für eine Anwendung eine Ausnahme Herausgeber erforderlich ist. Warnungen (8003-oder 8006-Ereignisse) werden in der Ereignisanzeige protokolliert, anstatt die Ausführung oder Installation bestimmter Apps oder Skripts zu blockieren.

### <a name="enforced-policy"></a>Erzwungene Richtlinie
Durch diese Richtlinie wird verhindert, dass nicht vertrauenswürdige apps und Skripts gestartet werden, und es werden Protokolle erstellt, wenn eine APP oder ein Skript blockiert wird. Erzwungene Richtlinien verhindern, dass Standardbenutzer Apps oder Skripts ausführen können, die in Benutzer schreibbaren Verzeichnissen gespeichert sind.

Für Geräte in der Test Gruppe wird eine Überwachungsrichtlinie angewendet, sodass Sie Sie verwenden können, um zu überprüfen, ob Anwendungen Probleme verursachen. Alle anderen Gruppen (zuerst, schnell und breit) verwenden eine erzwungene Richtlinie, sodass Endbenutzer in diesen Gruppen keine nicht vertrauenswürdigen Apps oder Skripts ausführen können.







