---
title: Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist
description: Beschreibt Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, erläutert die Berechnung von Details und was Sicherheitsadministratoren erwarten dürfen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545934"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist

Um [Microsoft-Sicherheitsbewertung](microsoft-secure-score-new.md) zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor. Ihre Bewertung und die maximale Punktzahl werden geändert. Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.

Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score-new.md#whats-new).

## <a name="june-2020"></a>Juni 2020

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Entfernen von Verbesserungs Aktionen für Microsoft Defender Advanced Threat Protection

* Aktivieren von Regeln für Angriffsflächen Reduzierung

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Hinzufügen von Verbesserungs Aktionen für Microsoft Defender Advanced Threat Protection

* Blockieren des Erstellens von untergeordneten Prozessen durch Adobe Reader
* Verwenden von erweitertem Schutz gegen Ransomware
* Verhindern, dass alle Office-Anwendungen untergeordnete Prozesse erstellen
* Verhindern der Erstellung von ausführbaren Inhalten durch Office-Anwendungen
* Blockieren von JavaScript oder VBScript beim Starten heruntergeladener ausführbarer Inhalte
* Blockieren der Ausführung von potenziell verborgenen Skripts
* Blockieren von ausführbaren Inhalten aus dem e-Mail-Client und Webmail
* Blockieren der Office-Kommunikationsanwendung beim Erstellen von untergeordneten Prozessen
* Blockieren von nicht vertrauenswürdigen und nicht signierten Prozessen, die von USB ausgeführt werden
* Block Persistenz durch WMI-Ereignisabonnement
* Verhindern, dass Office-Anwendungen Code in andere Prozesse einfügen
* Verhindern der Ausführung von ausführbaren Dateien, es sei denn, Sie entsprechen einer Prävalenz, einem Alter oder einem vertrauenswürdigen Listen Kriterium
* Blockieren von Prozess Kreationen, die von PSExec-und WMI-Befehlen stammen
* Blockieren des Diebstahls von Anmeldeinformationen vom Windows Local Security Authority Subsystem (Lsass. exe)
* Blockieren von Win32-API-Aufrufen aus Office-Makros
