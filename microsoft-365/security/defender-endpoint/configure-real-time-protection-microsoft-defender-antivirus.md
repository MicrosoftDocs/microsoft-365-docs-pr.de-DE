---
title: Aktivieren und Konfigurieren Microsoft Defender Antivirus Schutzfunktionen
description: Aktivieren und Konfigurieren Microsoft Defender Antivirus Echtzeitschutzfeatures wie Verhaltensüberwachung, Heuristik und Machine Learning
keywords: Antivirus, Echtzeitschutz, RTP, Machine Learning, Verhaltensüberwachung, Heuristiken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.date: 12/16/2019
manager: dansimp
ms.custom: nextgen
ms.openlocfilehash: 313646c69417082583b27bcfbab540131043ce76
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926667"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Aktivieren und Konfigurieren des immer aktivierten Schutzes von Microsoft Defender Antivirus in einer Gruppenrichtlinie


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Der Always-On-Schutz besteht aus Echtzeitschutz, Verhaltensüberwachung und Heuristiken, um Schadsoftware basierend auf bekannten verdächtigen und bösartigen Aktivitäten zu identifizieren.

Zu diesen Aktivitäten gehören Ereignisse, z. B. Prozesse, die ungewöhnliche Änderungen an vorhandenen Dateien vornehmen, das Ändern oder Erstellen automatischer Startregistrierungsschlüssel und Startspeicherorte (auch bekannt als Erweiterungspunkte für den automatischen Start oder ASEPs) und andere Änderungen am Dateisystem oder an der Dateistruktur.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Aktivieren und Konfigurieren des Always-On-Schutzes in gruppenrichtlinien

Sie können den Editor für **lokale Gruppenrichtlinien** verwenden, um Microsoft Defender Antivirus Always-On-Schutzeinstellungen zu aktivieren und zu konfigurieren.

So aktivieren und konfigurieren Sie den alwayson-Schutz:

1. Öffnen **Sie den Editor für lokale Gruppenrichtlinien.** Gehen Sie hierfür folgendermaßen vor:  

    1. Geben Sie in das Suchfeld der Windows 10 Taskleiste **gpedit ein.**
    
    1. Klicken Sie unter **"Beste Übereinstimmung"** auf **"Gruppenrichtlinie bearbeiten",** um den Editor für **lokale Gruppenrichtlinien** zu starten.
    
       ![GPEdit-Taskleistensuchergebnis](images/gpedit-search.png)

2. Erweitern Sie im linken Bereich des Editors für **lokale Gruppenrichtlinien** die Struktur auf administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus.** 

3. Konfigurieren Sie die Richtlinieneinstellungen für den Microsoft Defender Antivirus Antischadsoftwaredienst. Gehen Sie hierfür folgendermaßen vor:  

    1. Doppelklicken Sie im **Microsoft Defender Antivirus** Detailbereich auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:

       | Einstellung | Beschreibung | Standardeinstellung |
       |-----------------------------|------------------------|-------------------------------|
       | Starten des Antischadsoftwarediensts mit normaler Priorität zulassen | Sie können die Priorität des Microsoft Defender Antivirus Moduls verringern, was in einfachen Bereitstellungen nützlich sein kann, in denen Sie einen möglichst schlanken Startprozess wünschen. Dies kann sich auf den Schutz des Endpunkts auswirken. | Enabled
       | Zulassen, dass der Antischadsoftwaredienst immer ausgeführt wird | Wenn Schutzupdates deaktiviert wurden, können Sie festlegen, dass Microsoft Defender Antivirus weiterhin ausgeführt wird. Dadurch wird der Schutz auf dem Endpunkt verringert. | Deaktiviert |
    
    1. Konfigurieren Sie die Einstellung nach Bedarf, und klicken Sie auf **"OK".**
    
    1. Wiederholen Sie die vorherigen Schritte für jede Einstellung in der Tabelle.

4. Konfigurieren Sie die Microsoft Defender Antivirus Richtlinieneinstellungen für den Echtzeitschutz. Gehen Sie hierfür folgendermaßen vor:

    1. Doppelklicken Sie im **Detailbereich Microsoft Defender Antivirus** auf **Echtzeitschutz.** Oder klicken Sie in der **Microsoft Defender Antivirus** Struktur im linken Bereich auf **Echtzeitschutz.**
    
    1. Doppelklicken Sie im Detailbereich **"Echtzeitschutz"** auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:  

       | Einstellung | Beschreibung | Standardeinstellung |
       |-----------------------------|------------------------|-------------------------------|
       | Aktivieren der Verhaltensüberwachung | Das AV-Modul überwacht Dateiprozesse, Datei- und Registrierungsänderungen sowie andere Ereignisse auf Ihren Endpunkten auf verdächtige und bekannte böswillige Aktivitäten. | Enabled |
       | Scannen aller heruntergeladenen Dateien und Anlagen | Heruntergeladene Dateien und Anlagen werden automatisch gescannt. Dies funktioniert zusätzlich zum Windows Defender SmartScreen-Filter, der Dateien vor und während des Downloads überprüft. | Enabled |
       | Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer | Das Microsoft Defender Antivirus Modul notiert alle Dateiänderungen (Datei schreibt, z. B. Verschiebungen, Kopien oder Änderungen) und allgemeine Programmaktivitäten (Programme, die geöffnet oder ausgeführt werden und andere Programme ausführen). | Enabled |
       | Aktivieren von unformatierten Benachrichtigungen zum Schreiben von Volumes | Informationen zu unformatierten Volume-Schreibvorgängen werden von der Verhaltensüberwachung analysiert. | Enabled |
       | Aktivieren der Prozessüberprüfung, sobald der Echtzeitschutz aktiviert ist | Sie können das Microsoft Defender Antivirus Modul unabhängig aktivieren, um ausgeführte Prozesse auf verdächtige Änderungen oder Verhaltensweisen zu überprüfen. Dies ist nützlich, wenn Sie den Echtzeitschutz vorübergehend deaktiviert haben und Prozesse, die während der Deaktivierung gestartet wurden, automatisch überprüfen möchten. | Enabled |
       | Definieren der maximalen Größe der heruntergeladenen Dateien und Anlagen, die gescannt werden sollen | Sie können die Größe in KB definieren. | Enabled |
       | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Aktivierung der Verhaltensüberwachung | Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Verhaltensüberwachung. Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden. Wenn Sie diese Einstellung aktivieren, hat die Einstellung für lokale Einstellungen Vorrang vor gruppenrichtlinien. Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat die Gruppenrichtlinie Vorrang vor der lokalen Einstellung.| Enabled |
       | Konfigurieren der Außerkraftsetzung der lokalen Einstellung zum Überprüfen aller heruntergeladenen Dateien und Anlagen | Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überprüfung für alle heruntergeladenen Dateien und Anlagen. Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden. Wenn Sie diese Einstellung aktivieren, hat die Einstellung für lokale Einstellungen Vorrang vor gruppenrichtlinien. Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat die Gruppenrichtlinie Vorrang vor der lokalen Einstellung.| Enabled |
       | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung von Datei- und Programmaktivitäten auf Ihrem Computer | Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überwachung für Datei- und Programmaktivitäten auf Ihrem Computer. Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden. Wenn Sie diese Einstellung aktivieren, hat die Einstellung für lokale Einstellungen Vorrang vor gruppenrichtlinien. Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat die Gruppenrichtlinie Vorrang vor der lokalen Einstellung.| Enabled |
       | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren des Echtzeitschutzes | Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration, um den Echtzeitschutz zu aktivieren. Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden. Wenn Sie diese Einstellung aktivieren, hat die Einstellung für lokale Einstellungen Vorrang vor gruppenrichtlinien. Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat die Gruppenrichtlinie Vorrang vor der lokalen Einstellung.| Enabled |
       | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung eingehender und ausgehender Dateiaktivitäten | Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überwachung für eingehende und ausgehende Dateiaktivitäten. Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden. Wenn Sie diese Einstellung aktivieren, hat die Einstellung für lokale Einstellungen Vorrang vor gruppenrichtlinien. Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat die Gruppenrichtlinie Vorrang vor der lokalen Einstellung. | Enabled |
       | Konfigurieren der Überwachung für eingehende und ausgehende Datei- und Programmaktivitäten | Gibt an, ob die Überwachung für eingehende, ausgehende, beide oder keine Richtung erfolgen soll. Dies ist für Windows Serverinstallationen relevant, bei denen Sie bestimmte Server oder Serverrollen definiert haben, bei denen große Mengen von Dateiänderungen in nur einer Richtung angezeigt werden, und Sie die Netzwerkleistung verbessern möchten. Vollständig aktualisierte Endpunkte (und Server) in einem Netzwerk werden nur geringe Auswirkungen auf die Leistung haben, unabhängig von der Anzahl oder Richtung von Dateiänderungen. | Aktiviert (beide Richtungen) |

    1. Konfigurieren Sie die Einstellung nach Bedarf, und klicken Sie auf **"OK".**
    
    1. Wiederholen Sie die vorherigen Schritte für jede Einstellung in der Tabelle.

5. Konfigurieren Sie die Einstellung für die Microsoft Defender Antivirus Überprüfungsrichtlinie. Gehen Sie hierfür folgendermaßen vor:  

    1. Klicken Sie in der **Microsoft Defender Antivirus** Struktur im linken Bereich auf **"Scannen".**
    
       ![Microsoft Defender Antivirus Scanoptionen](images/gpedit-windows-defender-antivirus-scan.png)

    1. Doppelklicken Sie im Bereich **"Scandetails"** auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:

       | Einstellung | Beschreibung | Standardeinstellung |
       |-----------------------------|------------------------|-------------------------------|    
       | Aktivieren von Heuristiken | Der heuristische Schutz deaktiviert oder blockiert verdächtige Aktivitäten unmittelbar, bevor das Microsoft Defender Antivirus Modul aufgefordert wird, die Aktivität zu erkennen. | Enabled |

    1. Konfigurieren Sie die Einstellung nach Bedarf, und klicken Sie auf **"OK".**
    
6. Schließen Sie **den Editor für lokale Gruppenrichtlinien.**


## <a name="disable-real-time-protection-in-group-policy"></a>Deaktivieren des Echtzeitschutzes in gruppenrichtlinien

> [!WARNING]
> Das Deaktivieren des Echtzeitschutzes reduziert den Schutz auf Ihren Endpunkten erheblich und wird nicht empfohlen.

Die Hauptfunktion zum Echtzeitschutz ist standardmäßig aktiviert, Sie können sie jedoch mithilfe des Editors für **lokale Gruppenrichtlinien** deaktivieren.

So deaktivieren Sie den Echtzeitschutz in der Gruppenrichtlinie:

1. Öffnen **Sie den Editor für lokale Gruppenrichtlinien.**

   1. Geben Sie in das Suchfeld der Windows 10 Taskleiste **gpedit ein.**
   
   1. Klicken Sie unter **"Beste Übereinstimmung"** auf **"Gruppenrichtlinie bearbeiten",** um den Editor für **lokale Gruppenrichtlinien** zu starten.

2.  Erweitern Sie im linken Bereich des Editors für **lokale Gruppenrichtlinien** die Struktur zu **administrativen Vorlagen** für die Computerkonfiguration  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Echtzeitschutz.**

3. Doppelklicken Sie im Detailbereich **"Echtzeitschutz"** auf der rechten Seite auf **"Echtzeitschutz deaktivieren".**

   ![Deaktivieren des Echtzeitschutzes](images/gpedit-turn-off-real-time-protection.png)

4. Legen Sie im Einstellungsfenster zum Deaktivieren des **Echtzeitschutzes** die Option auf **"Aktiviert"** fest.

   ![Deaktivieren des Echtzeitschutzes aktiviert](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Klicken Sie auf **OK**.

6. Schließen Sie **den Editor für lokale Gruppenrichtlinien.**

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
