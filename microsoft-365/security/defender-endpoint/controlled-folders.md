---
title: Schützen wichtiger Ordner vor Ransomware vor dem Verschlüsseln Ihrer Dateien mit kontrollierten Ordnerzugriff
description: Dateien in Standardordnern können davor geschützt werden, von schädlichen Apps geändert zu werden. Verhindern, dass Ransomware Ihre Dateien verschlüsselt.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, schützen, Dateien, Ordner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7c471dc99a5deafcc60177812f60f1f884b10ee1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845570"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Was ist kontrollierter Ordnerzugriff?

Der kontrollierte Ordnerzugriff schützt Ihre wertvollen Daten vor schädlichen Apps und Bedrohungen wie Ransomware. Der kontrollierte Ordnerzugriff schützt Ihre Daten, indem Apps anhand einer Liste bekannter, vertrauenswürdiger Apps überprüft werden. Auf Windows Server 2019- und Windows 10-Clients unterstützt, kann der kontrollierte Ordnerzugriff mithilfe der Windows-Sicherheit App, Microsoft Endpoint Configuration Manager oder Intune (für verwaltete Geräte) aktiviert werden. 

> [!NOTE]
> Skriptmodule sind nicht vertrauenswürdig, und Sie können ihnen keinen Zugriff auf kontrollierte geschützte Ordner gewähren.  Beispielsweise wird PowerShell nicht durch kontrollierten Ordnerzugriff vertrauenswürdig, auch wenn Sie dies mit [Zertifikat- und Dateiindikatoren](/microsoft-365/security/defender-endpoint/indicator-certificates)zulassen. 

Der kontrollierte Ordnerzugriff funktioniert am besten mit [Microsoft Defender für Endpunkt.](microsoft-defender-endpoint.md)Dadurch erhalten Sie detaillierte Berichte zu Ereignissen und Blockierungen des kontrollierten Ordnerzugriffs im Rahmen der üblichen Szenarien zur Untersuchung von [Warnungen.](investigate-alerts.md)

> [!TIP]
> Kontrollierte Ordnerzugriffsblöcke generieren keine Warnungen in der [Warnungswarteschlange.](alerts-queue.md) Sie können jedoch Informationen zu kontrollierten Ordnerzugriffsblöcken in der [Zeitachsenansicht](investigate-machines.md)des Geräts anzeigen, während Sie [die erweiterte Suche](advanced-hunting-overview.md)verwenden oder [benutzerdefinierte Erkennungsregeln verwenden.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Wie funktioniert der kontrollierte Ordnerzugriff?

Der kontrollierte Ordnerzugriff funktioniert nur, indem vertrauenswürdigen Apps der Zugriff auf geschützte Ordner gestattet wird. Geschützte Ordner werden angegeben, wenn der kontrollierte Ordnerzugriff konfiguriert wird. In der Regel sind häufig verwendete Ordner, z. B. für Dokumente, Bilder, Downloads usw., in der Liste der gesteuerten Ordner enthalten. 

Der kontrollierte Ordnerzugriff funktioniert mit einer Liste vertrauenswürdiger Apps. Apps, die in der Liste der vertrauenswürdigen Software enthalten sind, funktionieren erwartungsgemäß. Apps, die nicht in der Liste enthalten sind, werden daran gehindert, Änderungen an Dateien in geschützten Ordnern vorzunehmen. 

Apps werden der Liste basierend auf ihrer Verbreitung und Ihrem Ruf hinzugefügt. Apps, die in Ihrer Gesamten Organisation sehr weit verbreitet sind und nie als bösartig eingestuftes Verhalten angezeigt haben, gelten als vertrauenswürdig. Diese Apps werden automatisch zur Liste hinzugefügt.

Apps können der vertrauenswürdigen Liste auch manuell mithilfe von Configuration Manager oder Intune hinzugefügt werden. Zusätzliche Aktionen, z. [B. das Hinzufügen eines Dateiindikators](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) für eine App, können über die Security Center-Konsole ausgeführt werden.

## <a name="why-controlled-folder-access-is-important"></a>Warum der kontrollierte Ordnerzugriff wichtig ist

Der kontrollierte Ordnerzugriff ist besonders nützlich, um Ihre Dokumente und Informationen vor [Ransomware](https://www.microsoft.com/wdsi/threats/ransomware)zu schützen. Bei einem Ransomware-Angriff können Ihre Dateien verschlüsselt und als Host gehalten werden. Wenn der kontrollierte Ordnerzugriff aktiviert ist, wird eine Benachrichtigung auf dem Computer angezeigt, auf dem eine App versucht hat, Änderungen an einer Datei in einem geschützten Ordner vorzunehmen. Sie können [die Benachrichtigung](customize-attack-surface-reduction.md#customize-the-notification) mit Ihren Unternehmensdetails und Kontaktinformationen anpassen. Sie können die Regeln auch einzeln aktivieren, um anzupassen, welche Techniken vom Feature überwacht werden.

Zu den [geschützten Ordnern](#review-controlled-folder-access-events-in-windows-event-viewer) gehören allgemeine Systemordner (einschließlich Startbereichen), und Sie können [weitere Ordner hinzufügen.](customize-controlled-folders.md#protect-additional-folders) Sie können Apps auch den Zugriff auf die geschützten Ordner [gestatten.](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders)

Sie können den [Überwachungsmodus](audit-windows-defender.md) verwenden, um zu bewerten, wie sich der kontrollierte Ordnerzugriff auf Ihre Organisation auswirken würde, wenn er aktiviert wäre. Sie können auch die Website Windows Defender Test-Boden unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

Der kontrollierte Ordnerzugriff wird in den folgenden Versionen von Windows unterstützt:
- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) und höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows Systemordner sind standardmäßig geschützt

Windows Systemordner sind standardmäßig zusammen mit mehreren anderen Ordnern geschützt: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> Sie können zusätzliche Ordner als geschützt konfigurieren, aber Sie können die Windows Systemordner nicht entfernen, die standardmäßig geschützt sind.

## <a name="requirements-for-controlled-folder-access"></a>Anforderungen für den kontrollierten Ordnerzugriff

Für den kontrollierten Ordnerzugriff muss [Microsoft Defender Antivirus Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)aktiviert werden.

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Überprüfen der Ereignisse des kontrollierten Ordnerzugriffs in der Microsoft Defender Security Center

Defender für Endpunkt bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)

Sie können Microsoft Defender für Endpunktdaten mithilfe der [erweiterten Suche](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)abfragen. Wenn Sie den [Überwachungsmodus](audit-windows-defender.md)verwenden, können Sie die [erweiterte Suche](advanced-hunting-overview.md) verwenden, um zu sehen, wie sich die Einstellungen für den kontrollierten Ordnerzugriff auf Ihre Umgebung auswirken würden, wenn sie aktiviert würden.

Beispielabfrage:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Überprüfen der Ereignisse des kontrollierten Ordnerzugriffs in Windows Ereignisanzeige

Sie können das Windows Ereignisprotokoll überprüfen, um Ereignisse anzuzeigen, die erstellt werden, wenn der kontrollierte Ordnerzugriff eine App blockiert (oder überwacht):

1. Laden Sie das [Evaluierungspaket herunter,](https://aka.ms/mp7z2w) und extrahieren Sie die Datei *cfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.
2. Geben Sie die **Ereignisanzeige** im Startmenü ein, um die Windows Ereignisanzeige zu öffnen.
3. Wählen Sie im linken Bereich unter **"Aktionen"** die Option **"Benutzerdefinierte Ansicht importieren" aus...**.
4. Navigieren Sie zu der Extrahierten *cfa-events.xml,* und wählen Sie sie aus. Alternativ können [Sie den XML-Code direkt kopieren.](event-views.md)
5. Wählen Sie **OK** aus.

In der folgenden Tabelle sind Ereignisse im Zusammenhang mit dem kontrollierten Ordnerzugriff aufgeführt:

|Ereignis-ID | Beschreibung |
|:---|:---|
|5007 | Ereignis, wenn Einstellungen geändert werden |
|1124 | Überwachtes Ereignis für den kontrollierten Ordnerzugriff | 
|1123 | Blockiertes Ereignis für den kontrollierten Ordnerzugriff |

## <a name="view-or-change-the-list-of-protected-folders"></a>Anzeigen oder Ändern der Liste der geschützten Ordner

Mit der Windows-Sicherheit-App können Sie die Liste der Ordner anzeigen, die durch den kontrollierten Ordnerzugriff geschützt sind. 

1. Öffnen Sie auf Ihrem Windows 10 Gerät die Windows-Sicherheit-App.
2. Wählen Sie **Viren- und Bedrohungsschutz** aus.
3. Wählen Sie unter **Ransomware-Schutz** Den **Ransomware-Schutz verwalten** aus.
4. Wenn der kontrollierte Ordnerzugriff deaktiviert ist, müssen Sie ihn aktivieren. Wählen Sie **geschützte Ordner aus.**
5. Führen Sie einen der folgenden Schritte aus:
   - Um einen Ordner hinzuzufügen, wählen Sie **+ Geschützten Ordner hinzufügen** aus.
   - Um einen Ordner zu entfernen, wählen Sie ihn aus, und wählen Sie dann **Entfernen** aus. 

> [!NOTE]
> [Windows Systemordner](#windows-system-folders-are-protected-by-default) sind standardmäßig geschützt, und Sie können sie nicht aus der Liste entfernen.

## <a name="see-also"></a>Siehe auch

- [Auswerten des kontrollierten Ordnerzugriffs](evaluate-controlled-folder-access.md)
- [Kontrollierte Ordnerzugriff anpassen](customize-controlled-folders.md)
- [Schützen weiterer Ordner](customize-controlled-folders.md#protect-additional-folders)
