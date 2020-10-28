---
title: Was kommt mit Microsoft Secure Score
description: Beschreibt, welche neuen Änderungen an Microsoft Secure Score im Microsoft 365 Security Center vorgenommen werden.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Improvement Actions
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779248"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Was kommt mit Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Wir nehmen in naher Zukunft einige Änderungen vor, um [Microsoft Secure Score](microsoft-secure-score.md) zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern. Ihre Punktzahl und die maximal mögliche Punktzahl können sich ändern.

## <a name="proposed-changes"></a>Vorgeschlagene Änderungen

### <a name="november-2020"></a>November 2020

Das Entfernen der Möglichkeit, ServiceNow-Tickets über Secure Score zu erstellen, erhalten Sie, indem Sie **> ServiceNow freigeben** .

- Der Vorschauzeitraum für den ServiceNow-Konnektor wird enden. Diese Funktion ist Ende 2020 nicht mehr verfügbar. Vielen Dank für Ihr Feedback und den weiteren Support, während wir die nächsten Schritte bestimmen.

Hinzufügen von 18 Verbesserungs Aktionen im Zusammenhang mit Microsoft Defender für Endpoint (zuvor Microsoft Defender ATP):

Empfehlungen zur Angriffsflächen Reduzierung (ASR):
- Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren
- Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern
- Office-Anwendungen am Erstellen ausführbarer Inhalte hindern
- Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern
- JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern
- Ausführung potenziell verborgener Skripts blockieren
- Win32-API-Aufrufe von Office-Makros blockieren
- Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium
- Erweiterten Schutz vor Ransomware verwenden
- Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren
- Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren
- Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren
- Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern
- Adobe Reader am Erstellen von untergeordneten Prozessen hindern
- Persistenz durch WMI-Ereignisabonnement blockieren

Empfehlungen zu Diensten:
- Unzitierten Dienstpfad für Windows-Dienste reparieren
- Ändern des ausführbaren Pfads des Diensts in einen allgemeinen geschützten Speicherort
- Ändern des Dienstkontos, um das zwischengespeicherte Kennwort in der Windows-Registrierung zu vermeiden

## <a name="related-resources"></a>Verwandte Ressourcen

- [Microsoft Secure Score (Übersicht)](microsoft-secure-score.md)
- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Neuigkeiten](microsoft-secure-score-whats-new.md)
