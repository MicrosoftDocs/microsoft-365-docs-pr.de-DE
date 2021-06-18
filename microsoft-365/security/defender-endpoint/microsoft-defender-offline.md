---
title: Microsoft Defender Offline in Windows 10
description: Sie können Microsoft Defender Offline direkt aus der Windows Defender Antivirus-App verwenden. Sie können auch verwalten, wie es in Ihrem Netzwerk bereitgestellt wird.
keywords: Scannen, Defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2a6ee7c3f3ea2fb31b31d2f1db178bfd9847fbc
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007475"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Ausführen und Überprüfen der Ergebnisse eines Microsoft Defender Offline-Scans

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline ist ein Antischadsoftware-Scantool, mit dem Sie eine Überprüfung aus einer vertrauenswürdigen Umgebung starten und ausführen können. Die Überprüfung wird von außerhalb des normalen Windows Kernels ausgeführt, sodass sie auf Schadsoftware abzielen kann, die versucht, die Windows Shell zu umgehen, z. B. Viren und Rootkits, die den Master Boot Record (MBR) infizieren oder überschreiben.

Sie können Microsoft Defender Offline verwenden, wenn Sie eine Schadsoftware-Infektion vermuten oder eine gründliche Bereinigung des Endpunkts nach einem Schadsoftwareausbruch bestätigen möchten.

In Windows 10 können Microsoft Defender Offline mit einem Klick direkt aus der [Windows-Sicherheit App](microsoft-defender-security-center-antivirus.md)ausgeführt werden. In früheren Versionen von Windows musste ein Benutzer Microsoft Defender Offline für startbare Medien installieren, den Endpunkt neu starten und das startbare Medium laden.

## <a name="prerequisites-and-requirements"></a>Voraussetzungen und Anforderungen

Microsoft Defender Offline in Windows 10 hat die gleichen Hardwareanforderungen wie Windows 10. 

Weitere Informationen zu Windows 10 Anforderungen finden Sie in den folgenden Themen:

- [Hardware-Mindestanforderungen](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Hardwarekomponenten-Anleitungen](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline wird auf Computern mit ARM-Prozessoren oder auf Windows Server Stock Keeping Units nicht unterstützt.

Um Microsoft Defender Offline vom Endpunkt aus auszuführen, muss der Benutzer mit Administratorrechten angemeldet sein.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline Updates

Microsoft Defender Offline verwendet die neuesten Schutzupdates, die auf dem Endpunkt verfügbar sind; es wird immer aktualisiert, wenn Windows Defender Antivirus aktualisiert wird. 

> [!NOTE]
> Vor dem Ausführen eines Offlinescans sollten Sie versuchen, den Microsoft Defender AV-Schutz zu aktualisieren. Sie können entweder ein Update mit einer Gruppenrichtlinie erzwingen oder updates normalerweise auf Endpunkten bereitstellen, oder Sie können die neuesten Schutzupdates aus dem [Microsoft-Center für den Schutz vor schädlicher Software](https://www.microsoft.com/security/portal/definitions/adl.aspx)manuell herunterladen und installieren.

Weitere Informationen finden Sie im Thema ["Verwalten Microsoft Defender Antivirus Sicherheitsupdates](manage-protection-updates-microsoft-defender-antivirus.md) für Sicherheitsinformationen".

## <a name="usage-scenarios"></a>Verwendungsszenarien

In Windows 10 Version 1607 können Sie einen Offlinescan manuell erzwingen. Wenn Windows Defender bestimmt, dass Microsoft Defender Offline ausgeführt werden muss, fordert es den Benutzer auf dem Endpunkt auf. 

Die Notwendigkeit, einen Offlinescan durchzuführen, wird auch in Microsoft Endpoint Manager angezeigt, wenn Sie ihn zum Verwalten Ihrer Endpunkte verwenden.

Die Eingabeaufforderung kann über eine Benachrichtigung erfolgen, ähnlich wie die folgende:

:::image type="content" source="../../media/notification.png" alt-text="Benachrichtigung zum Ausführen Microsoft Defender Offline":::

Der Benutzer wird auch innerhalb des Windows Defender-Clients benachrichtigt.

In Configuration Manager können Sie den Status von Endpunkten ermitteln, indem Sie zu **"Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status"** navigieren. 

Microsoft Defender Offline Scans werden unter dem Status zur **Schadsoftwarebehebung** als **Offlinescan angegeben.**

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender Offline Überprüfung erforderlich ist":::

## <a name="configure-notifications"></a>Konfigurieren von Benachrichtigungen

Microsoft Defender Offline Benachrichtigungen werden in derselben Richtlinieneinstellung wie andere Microsoft Defender AV-Benachrichtigungen konfiguriert.

Weitere Informationen zu Benachrichtigungen in Windows Defender finden Sie im Thema ["Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden".](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Ausführen eines Scanvorgangs 

> [!IMPORTANT]
> Bevor Sie Microsoft Defender Offline verwenden, stellen Sie sicher, dass Sie alle Dateien speichern und ausgeführte Programme herunterfahren. Der Microsoft Defender Offline Scan dauert ca. 15 Minuten. Der Endpunkt wird neu gestartet, wenn der Scan abgeschlossen ist. Die Überprüfung erfolgt außerhalb der üblichen Windows Betriebsumgebung. Die Benutzeroberfläche unterscheidet sich von einer normalen Überprüfung, die von Windows Defender ausgeführt wird. Nach Abschluss der Überprüfung wird der Endpunkt neu gestartet, und Windows wird normal geladen.

Sie können einen Microsoft Defender Offline-Scan mit folgendem Code ausführen:

- PowerShell
- Windows-Verwaltungsinstrumentation (WMI)
- Die Windows-Sicherheit-App



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Verwenden von PowerShell-Cmdlets zum Ausführen eines Offlinescans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Start-MpWDOScan
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Verwenden Windows Management Instruction (WMI) zum Ausführen eines Offlinescans

Verwenden Sie die [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Klasse, um einen Offlinescan auszuführen.

Der folgende WMI-Skriptausschnitt führt sofort eine Microsoft Defender Offline Überprüfung aus, wodurch der Endpunkt neu gestartet wird, der Offlinescan ausgeführt und dann neu gestartet und in Windows gestartet wird.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Weitere Informationen finden Sie in den folgenden Themen:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Verwenden der Windows Defender Security-App zum Ausführen eines Offlinescans

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder das Startmenü nach **Defender** durchsuchen.

2. Klicken Sie auf die Kachel **"Viren- & Bedrohungsschutz"** (oder auf das Schildsymbol auf der linken Menüleiste) und dann auf die Bezeichnung **"Erweiterter Scan":**
    
3. Wählen Sie **Microsoft Defender Offline scannen** aus, und klicken Sie auf **"Jetzt scannen".**

    > [!NOTE]
    > In Windows 10, Version 1607, kann der Offlinescan unter **Windows Einstellungen**  >  **Update & Security**  >  **Windows Defender** oder vom Windows Defender-Client ausgeführt werden.


## <a name="review-scan-results"></a>Überprüfen der Scanergebnisse

Microsoft Defender Offline Scanergebnisse werden im Abschnitt ["Scanverlauf" der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)aufgeführt. 


## <a name="related-articles"></a>Verwandte Artikel

- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Scans und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)