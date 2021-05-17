---
title: Behandeln von Problemen mit Microsoft Defender Antivirus bei der Migration von einer Drittanbieterlösung
description: Behandeln von häufigen Fehlern bei der Migration zu Microsoft Defender Antivirus
keywords: Ereignis, Fehlercode, Protokollierung, Problembehandlung, Microsoft Defender Antivirus, Windows Defender Antivirus, Migration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764591"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Behandeln von Problemen mit Microsoft Defender Antivirus bei der Migration von einer Drittanbieterlösung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


Hilfe finden Sie hier, wenn beim Migrieren von einer Sicherheitslösung eines Drittanbieters zu einer Microsoft Defender Antivirus.

## <a name="review-event-logs"></a>Überprüfen von Ereignisprotokollen

Öffnen Sie die Ereignisanzeige-App, indem Sie in der Taskleiste das Symbol Suchen auswählen und nach *der Ereignisanzeige suchen.* 

Informationen zu Microsoft Defender Antivirus finden Sie unter **Anwendungen und Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**. 

Wählen Sie dort unterhalb **von Operational** **die Option Öffnen aus.**

Wenn Sie ein Ereignis aus dem Detailbereich auswählen, werden weitere Informationen zu einem Ereignis im unteren Bereich unter den Registerkarten **Allgemein** und **Details** angezeigt.

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus wird nicht gestartet

Dieses Problem kann sich in Form mehrerer verschiedener Ereignis-IDs manifestieren, die alle die gleiche zugrunde liegende Ursache haben.

### <a name="associated-event-ids"></a>Zugeordnete Ereignis-IDs

 Ereignis-ID | Protokollname | Beschreibung | Quelle
-|-|-|-
15  | Anwendung | Der Windows Defender status wurde erfolgreich auf SECURITY_PRODUCT_STATE_OFF. | Security Center
5007 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus Die Konfiguration hat sich geändert.  Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.<br /><br />**Alter Wert:** Default\IsServiceRunning = 0x0<br />**Neuer Wert:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus überprüfung auf Spyware und andere potenziell unerwünschte Software ist deaktiviert. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>So erfahren Sie, ob Microsoft Defender Antivirus nicht gestartet wird, da ein Antivirenprogramm eines Drittanbieters installiert ist

Wenn Sie Windows 10 Microsoft Defender for Endpoint nicht verwenden und ein Antivirenprogramm eines Drittanbieters installiert ist, wird Microsoft Defender Antivirus automatisch deaktiviert. Wenn Sie Microsoft Defender for Endpoint mit einem Antivirenprogramm eines Drittanbieters verwenden, wird Microsoft Defender Antivirus mit eingeschränkter Funktionalität im passiven Modus gestartet.

> [!TIP]
> Das beschriebene Szenario gilt nur für Windows 10. Andere Versionen von Windows haben unterschiedliche [Antworten](microsoft-defender-antivirus-compatibility.md) auf Microsoft Defender Antivirus, die zusammen mit Sicherheitssoftware von Drittanbietern ausgeführt werden.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Verwenden der Dienst-App, um zu überprüfen, ob Microsoft Defender Antivirus deaktiviert ist

Wählen Sie zum Öffnen  der Dienst-App in der Taskleiste das Symbol Suchen aus, und suchen Sie nach *Diensten.* Sie können die App auch über die Befehlszeile öffnen, indem Sie *services.msc eingeben.*

Informationen zu Microsoft Defender Antivirus werden in der Services-App unter **Windows Defender**  >  **Operational aufgeführt.** Der Name des Antivirusdiensts *ist Windows Defender Antivirus Dienst*.

Beim Überprüfen der App wird möglicherweise angezeigt, dass *Windows Defender Antivirus Service* auf manuell festgelegt ist. Wenn Sie jedoch versuchen, diesen Dienst manuell zu starten, wird eine Warnung mit dem Hinweis angezeigt, dass der Windows Defender Antivirus-Dienst auf dem lokalen Computer gestartet und dann beendet *wurde. Einige Dienste werden automatisch beendet, wenn sie nicht von anderen Diensten oder Programmen verwendet werden.*

Dies bedeutet, Microsoft Defender Antivirus automatisch deaktiviert wurde, um die Kompatibilität mit einem Antivirenprogramm eines Drittanbieters zu gewährleisten.

#### <a name="generate-a-detailed-report"></a>Generieren eines detaillierten Berichts

Sie können einen detaillierten Bericht über derzeit aktive Gruppenrichtlinien generieren, indem Sie eine Eingabeaufforderung im **Modus Als** Administrator ausführen öffnen und dann den folgenden Befehl eingeben:

```powershell
GPresult.exe /h gpresult.html
```

Dadurch wird ein Bericht generiert, der sich unter *./gpresult.html befindet.* Öffnen Sie diese Datei, und möglicherweise werden die folgenden Ergebnisse angezeigt, je nachdem, Microsoft Defender Antivirus deaktiviert wurde.

##### <a name="group-policy-results"></a>Gruppenrichtlinienergebnisse

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Wenn Sicherheitseinstellungen über Gruppenrichtlinien (GPO) auf Domänen- oder lokaler Ebene implementiert werden oder wenn System Center Configuration Manager (SCCM)

Im GPResults-Bericht wird unter der Überschrift *Windows Komponenten/Windows Defender Antivirus* möglicherweise ein Eintrag wie der folgende angezeigt, der angibt, dass Microsoft Defender Antivirus deaktiviert ist.

Richtlinie | Setting | Gruppenrichtlinienobjekt gewinnen
-|-|-
Deaktivieren Windows Defender Antivirus | Aktiviert | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Wenn Sicherheitseinstellungen über gruppenrichtlinieneinstellungen (Group Policy Preference, GPP) implementiert werden

Unter der Überschrift Registrierungselement *(Schlüsselpfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Wertname: DisableAntiSpyware)* wird möglicherweise etwas wie der folgende Eintrag angezeigt, der angibt, dass Microsoft Defender Antivirus deaktiviert ist.

DisableAntiSpyware | -
-|-
Gruppenrichtlinienobjekt gewinnen | Win10-Workstations
Ergebnis: Erfolg | 
**Allgemein** | 
Aktion | Aktualisieren
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

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Wenn Sicherheitseinstellungen in Windows oder ihrem Windows Serverimage festgelegt sind

Ihr imaginärer Administrator hat möglicherweise die Sicherheitsrichtlinie **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, lokal über *GPEdit.exe*, *LGPO.exe* oder durch Ändern der Registrierung in ihrer Tasksequenz festgelegt. Sie können [einen vertrauenswürdigen Bildbezeichner](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) für Microsoft Defender Antivirus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Aktivieren Microsoft Defender Antivirus Wieder aktivieren

Microsoft Defender Antivirus wird automatisch aktiviert, wenn derzeit kein anderer Antivirus aktiv ist. Sie müssen den Antivirenprogramm eines Drittanbieters vollständig deaktivieren, um sicherzustellen, dass Microsoft Defender Antivirus funktionen voll ausgeführt werden kann.

> [!WARNING]
> Lösungen, die vorschlagen,  dass Sie die Windows Defender-Startwerte für *wdboot,* *wdfilter*, *wdnisdrv,* *wdnissvc* und *windefend* in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services bearbeiten, werden nicht unterstützt und können ein erneutes Image Ihres Systems erzwingen.

Der passive Modus ist verfügbar, wenn Sie mit der Verwendung von Microsoft Defender for Endpoint und einem Antivirenprogramm eines Drittanbieters zusammen mit Microsoft Defender Antivirus. Der passive Modus ermöglicht Es Microsoft Defender, Dateien zu überprüfen und sich selbst zu aktualisieren, es werden jedoch keine Bedrohungen behoben. Darüber hinaus ist die Verhaltensüberwachung über [Den Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md) im passiven Modus nicht verfügbar, es sei denn, die Verhinderung von Datenverlust [durch Endpunkte (Endpoint Data Loss Prevention, DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) wird bereitgestellt.

Ein weiteres Feature, das als [eingeschränkte](limited-periodic-scanning-microsoft-defender-antivirus.md)regelmäßige Überprüfung bezeichnet wird, steht Endbenutzern zur Verfügung, wenn Microsoft Defender Antivirus automatisch deaktiviert ist. Dieses Feature ermöglicht Microsoft Defender Antivirus, Dateien regelmäßig zusammen mit einem Antivirenprogramm eines Drittanbieters mithilfe einer begrenzten Anzahl von Erkennungen zu überprüfen.

> [!IMPORTANT]
> Begrenzte regelmäßige Überprüfungen werden in Unternehmensumgebungen nicht empfohlen. Die Erkennungs-, Verwaltungs- und Berichtsfunktionen, die beim Ausführen Microsoft Defender Antivirus in diesem Modus verfügbar sind, sind im Vergleich zum aktiven Modus reduziert.

### <a name="see-also"></a>Siehe auch

* [Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivirus in der Windows-Sicherheit App](microsoft-defender-security-center-antivirus.md)