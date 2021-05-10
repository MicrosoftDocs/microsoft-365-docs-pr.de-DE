---
title: 'Schritt 2: Behebung Des ersten Vorfalls'
description: Erste Schritte bei der Behebung Ihres ersten Vorfalls in Microsoft 365 Defender.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297344"
---
# <a name="step-2-remediate-your-first-incident"></a>Schritt 2. Behebung Des ersten Vorfalls

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft 365 Defender bietet nicht nur Erkennungs- und Analysefunktionen, sondern bietet auch Eindämmung und Beseitigung von Schadsoftware. Containment umfasst Schritte, um die Auswirkungen des Angriffs zu reduzieren, während die Auslöschung sicherstellt, dass alle Spuren von Angreiferaktivitäten aus dem Netzwerk entfernt werden.  Microsoft 365 Defender bietet verschiedene Korrekturaktionen, die je [](m365d-autoir.md) nach Betriebssystem und Angriffstyp für die automatische Behebung konfiguriert werden können.

Microsoft 365 Defender bietet mehrere Korrekturaktionen, die Analysten manuell initiieren können. Aktionen sind in zwei Kategorien unterteilt: Aktionen auf Geräten und Aktionen für Dateien. Einige Aktionen können verwendet werden, um die Bedrohung sofort zu beenden, während andere Aktionen bei der weiteren forensischen Analyse helfen.

## <a name="actions-on-devices"></a>Aktionen auf Geräten

- **Gerät** isolieren – Diese Aktivität blockiert sofort den ganzen Netzwerkdatenverkehr (Internet und intern), um die Verbreitung von Schadsoftware zu minimieren und Analysten die Fortsetzung der Analyse zu ermöglichen, ohne dass ein böswilliger Akteur einen Angriff fortsetzen kann. Die einzige zulässige Verbindung ist die Microsoft Defender for Identity -Dienst-Cloud, damit Microsoft Defender for Identity das Gerät weiterhin überwachen kann. 
- **Einschränken der** App-Ausführung: Um die Ausführung einer Anwendung einzuschränken, wird eine Codeintegritätsrichtlinie angewendet, die nur die Ausführung von Dateien zulässt, wenn sie von einem von Microsoft ausgestellten Zertifikat signiert sind. Diese Einschränkungsmethode kann verhindern, dass ein Angreifer gefährdete Geräte steuert und weitere schädliche Aktivitäten ausführen kann.
- **Antivirusscan ausführen** – Eine Microsoft Defender Antivirus kann zusammen mit anderen Antivirenlösungen ausgeführt werden, unabhängig davon, ob Defender Antivirus die aktive Antivirenlösung ist oder nicht. Wenn ein anderes Antivirenprodukt die primäre Endpunktschutzlösung ist, können Sie Defender Antivirus im passiven Modus ausführen.
- **Initiieren einer automatisierten** Untersuchung – Sie können eine neue allgemeine automatisierte Untersuchung auf dem Gerät starten. Während eine Untersuchung ausgeführt wird, werden alle anderen vom Gerät generierten Warnungen einer fortlaufenden automatisierten Untersuchung hinzugefügt, bis diese Untersuchung abgeschlossen ist. Wenn die gleiche Bedrohung auch auf anderen Geräten angezeigt wird, werden diese Geräte der Untersuchung hinzugefügt.
- **Liveantwort initiieren** – Liveantwort ist eine Funktion, mit der Sie über eine Remoteshellverbindung sofort auf ein Gerät zugreifen können. Dadurch können Sie eingehende Ermittlungen durchführen und sofort Maßnahmen ergreifen, um identifizierte Bedrohungen zeitnah in Echtzeit zu enthalten. Die Liveantwort dient der Verbesserung der Untersuchungen, indem Sie forensische Daten sammeln, Skripts ausführen, verdächtige Entitäten zur Analyse senden, Bedrohungen behebt und proaktiv nach neuen Bedrohungen fahnen kann.
- **Untersuchungspaket sammeln** – Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen. Durch das Sammeln des Untersuchungspakets können Sie den aktuellen Zustand des Geräts identifizieren und die vom Angreifer verwendeten Tools und Techniken besser verstehen. 
- **Konsultieren Sie einen** Bedrohungsexperten (verfügbar in Aktionen auf Geräten und Dateien) – Sie können einen Microsoft-Bedrohungsexperten konsultieren, um weitere Informationen zu potenziell gefährdeten Geräten oder Geräten zu erhalten, die bereits gefährdet sind. Microsoft-Bedrohungsexperten können direkt innerhalb des Microsoft Defender Security Center eine zeitnahe und genaue Antwort erhalten. 

## <a name="actions-on-files"></a>Aktionen für Dateien

- **Datei beenden und isolieren** – Diese Aktion umfasst das Beenden von ausgeführten Prozessen, das Quarantinieren von Dateien und das Löschen persistenter Daten, z. B. aller Registrierungsschlüssel. Diese Aktion wird auf Geräten mit Windows 10 Version 1703 oder höher wirksam, auf denen die Datei in den letzten 30 Tagen beobachtet wurde. 
- **Hinzufügen von Indikatoren zum Blockieren** oder Zulassen von Dateien – Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten. Dieser Vorgang verhindert, dass die Datei auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.
- **Datei herunterladen** oder sammeln – Mit dieser Aktion können Analysten eine Datei in einer kennwortgeschützten .zip Archivdatei für die weitere Analyse durch die Organisation herunterladen.
- **Tiefe Analyse** – Mit dieser Aktion wird eine Datei in einer sicheren, vollständig instrumentierten Cloudumgebung ausgeführt. Tiefe Analyseergebnisse zeigen die Aktivitäten der Datei, beobachtete Verhaltensweisen und zugehörige Artefakte, z. B. gelöschte Dateien, Registrierungsänderungen und die Kommunikation mit IP-Adressen. 

Wenn Sie das Beispiel in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident)fortsetzen, kann ein Analytiker diesen Vorfall mit folgenden Aktionen beklagen:

1. Sofortiges Zurücksetzen des Benutzerkontokennworts
2. Isolieren des Geräts in Microsoft 365 Defender, bis die umfassende Analyse abgeschlossen ist
3. Stellen Sie sicher, dass die schädliche Datei in Quarantäne SharePoint
4. Überprüfen, welche Endpunkte von Schadsoftware betroffen waren
5. Neuerstellen von Systemen
6. Überprüfen auf ähnliche Microsoft Cloud App Security für andere Benutzer
7. Erstellen eines benutzerdefinierten Indikators in Microsoft Defender for Endpoint zum Blockieren einer Tor-IP-Adresse
8. Erstellen Sie eine Steuerungsaktion in Microsoft Cloud App Security für diese Art von Warnung, z. B. die in der folgenden Abbildung dargestellten:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Beispiel für Steuerungsaktionen im Microsoft Cloud App Security Portal"::: 
 
Die meisten Korrekturaktionen können in Defender angewendet und nachverfolgt Microsoft 365 werden. 

## <a name="using-playbooks"></a>Verwenden von Playbooks

Darüber hinaus kann eine automatisierte Korrektur mithilfe von Playbooks erstellt werden. Derzeit verfügt Microsoft [über Playbook-Vorlagen auf GitHub,](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) die Playbooks für die folgenden Szenarien bereitstellen:

- Entfernen der freigabe vertraulichen Dateien nach dem Anfordern der Benutzerüberprüfung
- Automatisches Austriagen seltener Länderwarnungen
- Anfordern einer Manageraktion vor dem Deaktivieren eines Kontos
- Deaktivieren bösartiger Posteingangsregeln

Playbooks verwenden Power Automate, um benutzerdefinierte Automatisierungsabläufe für Robotikprozesse zu erstellen, um bestimmte Aktivitäten zu automatisieren, sobald bestimmte Kriterien ausgelöst wurden. Organisationen können Playbooks entweder aus vorhandenen Vorlagen oder von Grund auf neu erstellen. 

Im Folgenden sehen Sie ein Beispiel.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Beispiel für einen Power Automate benutzerdefinierten Automatisierungsfluss für Robotikprozesse"::: 
 
Playbooks können auch [](first-incident-post.md) während der Überprüfung nach dem Vorfall erstellt werden, um Korrekturaktionen aus Vorfällen für schnellere Korrekturaktionen zu erstellen. 

## <a name="next-step"></a>Nächster Schritt

[![Schritt 3: Erfahren Sie, wie Sie eine Überprüfung eines Vorfalls nach einem Vorfall durchführen](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

Erfahren Sie, [wie Sie eine Überprüfung eines Vorfalls nach einem Vorfall durchführen.](first-incident-post.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
