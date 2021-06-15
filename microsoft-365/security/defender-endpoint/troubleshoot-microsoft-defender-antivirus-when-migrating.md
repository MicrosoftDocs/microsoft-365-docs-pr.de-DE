---
title: Behandeln von Problemen mit Microsoft Defender Antivirus bei der Migration von einer Drittanbieterlösung
description: Behandeln häufiger Fehler bei der Migration zu Microsoft Defender Antivirus
keywords: Ereignis, Fehlercode, Protokollierung, Problembehandlung, Microsoft Defender Antivirus, Windows Defender Antivirus, Migration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924383"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Behandeln von Problemen mit Microsoft Defender Antivirus bei der Migration von einer Drittanbieterlösung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


Hier finden Sie Hilfe, wenn beim Migrieren von einer Drittanbieter-Sicherheitslösung zu Microsoft Defender Antivirus Probleme auftreten.

## <a name="review-event-logs"></a>Überprüfen von Ereignisprotokollen

Öffnen Sie die Ereignisanzeige-App, indem Sie das **Suchsymbol** in der Taskleiste auswählen und nach *der Ereignisanzeige* suchen.

Informationen zu Microsoft Defender Antivirus finden Sie unter **Anwendungen und Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**. 

Wählen Sie dort unter **"Betriebsbereit"** die Option **"Öffnen"** aus.

Wenn Sie ein Ereignis im Detailbereich auswählen, werden weitere Informationen zu einem Ereignis im unteren Bereich unter den Registerkarten **"Allgemein"** und **"Details"** angezeigt.

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus wird nicht gestartet

Dieses Problem kann sich in Form verschiedener Ereignis-IDs manifestieren, die alle die gleiche zugrunde liegende Ursache haben.

### <a name="associated-event-ids"></a>Zugeordnete Ereignis-IDs

 Ereignis-ID | Protokollname | Beschreibung | Source
-|-|-|-
15 | App | Der Status Windows Defender wurde erfolgreich auf SECURITY_PRODUCT_STATE_OFF aktualisiert. | Sicherheitscenter
5007 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus Die Konfiguration hat sich geändert.  Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.<br /><br />**Alter Wert:** Default\IsServiceRunning = 0x0<br />**Neuer Wert:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus Überprüfung auf Spyware und andere potenziell unerwünschte Software ist deaktiviert. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Erfahren Sie, ob Microsoft Defender Antivirus nicht gestartet wird, da ein Antivirenprogramm eines Drittanbieters installiert ist.

Wenn Sie auf einem Windows 10 Gerät Microsoft Defender für Endpunkt nicht verwenden und ein Antivirenprogramm eines Drittanbieters installiert ist, wird Microsoft Defender Antivirus automatisch deaktiviert. Wenn Sie Microsoft Defender für Endpunkt verwenden und ein Antivirenprogramm eines Drittanbieters installiert ist, wird Microsoft Defender Antivirus im passiven Modus mit eingeschränkter Funktionalität gestartet.

> [!TIP]
> Das soeben beschriebene Szenario gilt nur für Windows 10. Andere Versionen von Windows haben [unterschiedliche Antworten auf](microsoft-defender-antivirus-compatibility.md) Microsoft Defender Antivirus zusammen mit Sicherheitssoftware von Drittanbietern ausgeführt werden.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Verwenden der Dienste-App, um zu überprüfen, ob Microsoft Defender Antivirus deaktiviert ist

Um die Dienste-App zu öffnen, wählen Sie das **Suchsymbol** in der Taskleiste aus, und suchen Sie nach *Diensten.* Sie können die App auch über die Befehlszeile öffnen, indem Sie *"services.msc"* eingeben.

Informationen zu Microsoft Defender Antivirus werden in der Dienste-App unter **Windows Defender**  >  **Operational** aufgeführt. Der Name des Antivirendiensts lautet *Windows Defender Antivirus Dienst.*

Beim Überprüfen der App sehen Sie möglicherweise, dass *Windows Defender Antivirus Dienst* auf manuell festgelegt ist. Wenn Sie jedoch versuchen, diesen Dienst manuell zu starten, wird eine Warnung angezeigt, die besagt, dass der *Windows Defender Antivirus Dienstdienst auf dem lokalen Computer gestartet und dann beendet wurde. Einige Dienste werden automatisch beendet, wenn sie nicht von anderen Diensten oder Programmen verwendet werden.*

Dies weist darauf hin, dass Microsoft Defender Antivirus automatisch deaktiviert wurde, um die Kompatibilität mit einem Antivirenprogramm eines Drittanbieters zu erhalten.

#### <a name="generate-a-detailed-report"></a>Generieren eines detaillierten Berichts

Sie können einen detaillierten Bericht über derzeit aktive Gruppenrichtlinien generieren, indem Sie eine Eingabeaufforderung im **Modus "Als Administrator ausführen"** öffnen und dann den folgenden Befehl eingeben:

```powershell
GPresult.exe /h gpresult.html
```

Dadurch wird ein Bericht generiert, der sich unter *./gpresult.html* befindet. Öffnen Sie diese Datei, und je nachdem, wie Microsoft Defender Antivirus deaktiviert wurde, werden möglicherweise die folgenden Ergebnisse angezeigt.

##### <a name="group-policy-results"></a>Gruppenrichtlinienergebnisse

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Wenn Sicherheitseinstellungen über gruppenrichtlinien (GPO) auf domänen- oder lokaler Ebene oder über System Center Configuration Manager (SCCM) implementiert werden

Im GPResults-Bericht wird unter der Überschrift *Windows Komponenten/Windows Defender Antivirus* möglicherweise etwa der folgende Eintrag angezeigt, der angibt, dass Microsoft Defender Antivirus deaktiviert ist.

Richtlinie | Setting | Gewinnen eines Gruppenrichtlinienobjekts
-|-|-
Deaktivieren Windows Defender Antivirus | Enabled | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Wenn Sicherheitseinstellungen über die Gruppenrichtlinieneinstellung (Group Policy Preference, GPP) implementiert werden

Unter der Überschrift *"Registrierungselement" (Schlüsselpfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Wertname: DisableAntiSpyware)* wird möglicherweise etwa der folgende Eintrag angezeigt, der angibt, dass Microsoft Defender Antivirus deaktiviert ist.

DisableAntiSpyware | -
-|-
Gewinnen eines Gruppenrichtlinienobjekts | Win10-Workstations
Ergebnis: Erfolgreich | 
**Allgemein** | 
Aktion | Update
**Eigenschaften** | 
Hive | HKEY_LOCAL_MACHINE
Schlüsselpfad | SOFTWARE\Policies\Microsoft\Windows Defender
Wertname | DisableAntiSpyware
Werttyp | REG_DWORD
Wertdaten | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Wenn Sicherheitseinstellungen über den Registrierungsschlüssel implementiert werden

Der Bericht kann den folgenden Text enthalten, der angibt, dass Microsoft Defender Antivirus deaktiviert ist:
 
> Registrierung (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Wenn Sicherheitseinstellungen in Windows oder ihrem Windows Server-Image festgelegt sind

Ihr imaginierender Administrator hat die Sicherheitsrichtlinie **["DisableAntiSpyware"](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** möglicherweise lokal über *GPEdit.exe,* *LGPO.exe* oder durch Ändern der Registrierung in der Tasksequenz festgelegt. Sie können [einen vertrauenswürdigen Bildbezeichner](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) für Microsoft Defender Antivirus konfigurieren.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Microsoft Defender Antivirus wieder aktivieren

Microsoft Defender Antivirus wird automatisch aktiviert, wenn kein anderer Antivirus derzeit aktiv ist. Sie müssen das Antivirenprogramm des Drittanbieters vollständig deaktivieren, um sicherzustellen, dass Microsoft Defender Antivirus mit voller Funktionalität ausgeführt werden können.

> [!WARNING]
> Lösungen, die vorschlagen, dass Sie die *Windows Defender* Startwerte für *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* und *windefend* in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services nicht unterstützt werden, und sie können das erneute Image Ihres Systems erzwingen.

Der passive Modus ist verfügbar, wenn Sie Microsoft Defender für Endpunkt und ein Antivirenprogramm eines Drittanbieters zusammen mit Microsoft Defender Antivirus verwenden. Der passive Modus ermöglicht Es Microsoft Defender, Dateien zu scannen und sich selbst zu aktualisieren, bedrohungen werden jedoch nicht behoben. Darüber hinaus ist die Verhaltensüberwachung über [Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md) im passiven Modus nicht verfügbar, es sei denn, [die Verhinderung von Datenverlust am Endpunkt (Endpoint Data Loss Prevention, DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) wird bereitgestellt.

Ein weiteres Feature, das als [eingeschränkte regelmäßige Überprüfung](limited-periodic-scanning-microsoft-defender-antivirus.md)bezeichnet wird, steht Endbenutzern zur Verfügung, wenn Microsoft Defender Antivirus so eingestellt ist, dass es automatisch deaktiviert wird. Dieses Feature ermöglicht es Microsoft Defender Antivirus, Dateien regelmäßig zusammen mit einem Antivirenprogramm eines Drittanbieters mithilfe einer begrenzten Anzahl von Erkennungen zu scannen.

> [!IMPORTANT]
> Eine eingeschränkte regelmäßige Überprüfung wird in Unternehmensumgebungen nicht empfohlen. Die verfügbaren Funktionen für Erkennung, Verwaltung und Berichterstellung, wenn Microsoft Defender Antivirus in diesem Modus ausgeführt werden, werden im Vergleich zum aktiven Modus reduziert.

### <a name="see-also"></a>Siehe auch

* [Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivirus in der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)