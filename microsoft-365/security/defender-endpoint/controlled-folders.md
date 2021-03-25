---
title: Schützen wichtiger Ordner vor Ransomware vor der Verschlüsselung Ihrer Dateien mit kontrolliertem Ordnerzugriff
description: Dateien in Standardordnern können vor der Änderung durch schädliche Apps geschützt werden. Verhindern, dass Ransomware Ihre Dateien verschlüsselt.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner
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
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200281"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Was ist kontrollierter Ordnerzugriff?

Der kontrollierte Ordnerzugriff schützt Ihre wertvollen Daten vor schädlichen Apps und Bedrohungen, z. B. Ransomware. Der kontrollierte Ordnerzugriff schützt Ihre Daten, indem Apps mit einer Liste bekannter, vertrauenswürdiger Apps überprüft werden. Unterstützt auf Windows Server 2019- und Windows 10-Clients kann der kontrollierte Ordnerzugriff mit der Windows Security App, Microsoft Endpoint Configuration Manager oder Intune (für verwaltete Geräte) aktiviert werden. 

> [!NOTE]
> Skriptmodule sind nicht vertrauenswürdig, und Sie können ihnen keinen Zugriff auf kontrollierte geschützte Ordner erlauben.  Beispielsweise wird PowerShell nicht durch kontrollierten Ordnerzugriff vertrauenswürdig, auch wenn Sie dies mit Zertifikat- und [Dateiindikatoren zulassen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates) 

Der kontrollierte Ordnerzugriff funktioniert am besten mit [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), mit dem Sie detaillierte Berichte zu Ereignissen und Blöcken für den kontrollierten Ordnerzugriff im Rahmen der üblichen Warnungsuntersuchungsszenarien erstellen [können.](investigate-alerts.md)

> [!TIP]
> Kontrollierte Ordnerzugriffsblöcke generieren keine Warnungen in der [Warnungswarteschlange.](alerts-queue.md) Sie können jedoch Informationen zu zugriffsgesteuerten Ordnerblöcken in [](advanced-hunting-overview.md)der Gerätezeitachsenansicht [anzeigen,](investigate-machines.md)während Sie erweiterte Suche oder benutzerdefinierte [Erkennungsregeln verwenden.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Wie funktioniert der kontrollierte Ordnerzugriff?

Der kontrollierte Ordnerzugriff funktioniert, indem nur vertrauenswürdige Apps auf geschützte Ordner zugreifen können. Geschützte Ordner werden angegeben, wenn der kontrollierte Ordnerzugriff konfiguriert ist. In der Regel werden häufig verwendete Ordner, z. B. für Dokumente, Bilder, Downloads und so weiter, in die Liste der kontrollierten Ordner aufgenommen. 

Der kontrollierte Ordnerzugriff funktioniert mit einer Liste vertrauenswürdiger Apps. Apps, die in der Liste der vertrauenswürdigen Software enthalten sind, funktionieren wie erwartet. Apps, die nicht in der Liste enthalten sind, können keine Änderungen an Dateien in geschützten Ordnern vornehmen. 

Apps werden der Liste basierend auf ihrer Verbreitung und Reputation hinzugefügt. Apps, die in Ihrer gesamten Organisation stark verbreitet sind und niemals ein als schädlich eingestuftes Verhalten angezeigt haben, gelten als vertrauenswürdig. Diese Apps werden der Liste automatisch hinzugefügt.

Apps können auch manuell mithilfe von Configuration Manager oder Intune zur vertrauenswürdigen Liste hinzugefügt werden. Zusätzliche Aktionen, z. [B. das Hinzufügen eines Dateiindikators](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) für eine App, können über die Security Center Console ausgeführt werden.

## <a name="why-controlled-folder-access-is-important"></a>Warum der kontrollierte Ordnerzugriff wichtig ist

Der kontrollierte Ordnerzugriff ist besonders hilfreich, um Ihre Dokumente und Informationen vor Ransomware [zu schützen.](https://www.microsoft.com/wdsi/threats/ransomware) Bei einem Ransomware-Angriff können Ihre Dateien verschlüsselt und als Host gehalten werden. Bei kontrolliertem Ordnerzugriff wird eine Benachrichtigung auf dem Computer angezeigt, auf dem eine App versucht hat, Änderungen an einer Datei in einem geschützten Ordner vorzunehmen. Sie können [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) Ihren Unternehmensdetails und Kontaktinformationen anpassen. Sie können die Regeln auch einzeln aktivieren, um anzupassen, welche Techniken das Feature überwacht.

Die [geschützten Ordner](#review-controlled-folder-access-events-in-windows-event-viewer) enthalten allgemeine Systemordner (einschließlich Startsektoren), und Sie können [weitere Ordner hinzufügen.](customize-controlled-folders.md#protect-additional-folders) Sie können Apps [auch den](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) Zugriff auf die geschützten Ordner ermöglichen.

Sie können den [Überwachungsmodus verwenden,](audit-windows-defender.md) um zu bewerten, wie sich der kontrollierte Ordnerzugriff auf Ihre Organisation auswirken würde, wenn er aktiviert wäre. Sie können auch die Windows Defender test ground website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

Der kontrollierte Ordnerzugriff wird unter den folgenden Versionen von Windows unterstützt:
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) und höher
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows-Systemordner sind standardmäßig geschützt

Windows-Systemordner sind zusammen mit mehreren anderen Ordnern standardmäßig geschützt: 

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
> Sie können zusätzliche Ordner als geschützt konfigurieren, aber sie können die standardmäßig geschützten Windows-Systemordner nicht entfernen.

## <a name="requirements-for-controlled-folder-access"></a>Anforderungen für den kontrollierten Ordnerzugriff

Der kontrollierte Ordnerzugriff erfordert die [Aktivierung des Microsoft Defender Antivirus-Echtzeitschutzes.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff im Microsoft Defender Security Center

Defender for Endpoint bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)

Sie können Microsoft Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Wenn Sie den Überwachungsmodus [verwenden,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu sehen, wie sich die Einstellungen für den kontrollierten Ordnerzugriff auf Ihre Umgebung auswirken würden, wenn sie aktiviert wären. [](advanced-hunting-overview.md)

Beispielabfrage:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff in der Windows-Ereignisanzeige

Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die erstellt werden, wenn kontrollierte Ordnerzugriffsblöcke (oder Überwachungen) einer App ausgeführt werden:

1. Laden Sie [das Evaluierungspaket](https://aka.ms/mp7z2w) herunter, und *extrahierencfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.
2. Geben **Sie die Ereignisanzeige** im Menü Start ein, um die Windows-Ereignisanzeige zu öffnen.
3. Wählen Sie im linken Bereich unter **Aktionen** die Option **Benutzerdefinierte Ansicht importieren... aus.**
4. Navigieren Sie zu dem Ort, an *demcfa-events.xml* extrahiert haben, und wählen Sie ihn aus. Alternativ können [Sie die XML direkt kopieren.](event-views.md)
5. Wählen Sie **OK** aus.

In der folgenden Tabelle sind Ereignisse im Zusammenhang mit dem kontrollierten Ordnerzugriff aufgeführt:

|Ereignis-ID | Beschreibung |
|:---|:---|
|5007 | Ereignis, wenn Einstellungen geändert werden |
|1124 | Überwachtes kontrolliertes Ordnerzugriffsereignis | 
|1123 | Blockiertes Ereignis für den kontrollierten Ordnerzugriff |

## <a name="view-or-change-the-list-of-protected-folders"></a>Anzeigen oder Ändern der Liste geschützter Ordner

Mit der Windows Security-App können Sie die Liste der Ordner anzeigen, die durch den kontrollierten Ordnerzugriff geschützt sind. 

1. Öffnen Sie auf Ihrem Windows 10-Gerät die Windows Security-App.
2. Wählen **Sie Virenschutz & Bedrohungsschutz aus.**
3. Wählen **Sie unter Ransomware-Schutz** die Option **Ransomware-Schutz verwalten aus.**
4. Wenn der kontrollierte Ordnerzugriff deaktiviert ist, müssen Sie ihn aktivieren. Wählen **Sie geschützte Ordner aus.**
5. Führen Sie einen der folgenden Schritte aus:
   - Wählen Sie + Einen geschützten Ordner hinzufügen aus, **um einen Ordner hinzuzufügen.**
   - Um einen Ordner zu entfernen, wählen Sie ihn aus, und wählen Sie dann **Entfernen aus.** 

> [!NOTE]
> [Windows-Systemordner](#windows-system-folders-are-protected-by-default) sind standardmäßig geschützt, und Sie können sie nicht aus der Liste entfernen.

## <a name="see-also"></a>Siehe auch

- [Bewerten des kontrollierten Ordnerzugriffs](evaluate-controlled-folder-access.md)
- [Anpassen des kontrollierten Ordnerzugriffs](customize-controlled-folders.md)
- [Weitere Ordner schützen](customize-controlled-folders.md#protect-additional-folders)
