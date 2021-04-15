---
title: Microsoft Defender Offline in Windows 10
description: Sie können Microsoft Defender Offline direkt über die Windows Defender Antivirus-App verwenden. Sie können auch verwalten, wie sie in Ihrem Netzwerk bereitgestellt wird.
keywords: scan, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765335"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Ausführen und Überprüfen der Ergebnisse einer Microsoft Defender Offline-Überprüfung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline ist ein Antischadsoftwarescantool, mit dem Sie eine Überprüfung aus einer vertrauenswürdigen Umgebung starten und ausführen können. Der Scan wird außerhalb des normalen Windows-Kernels ausgeführt, sodass er auf Schadsoftware zielen kann, die versucht, die Windows-Shell zu umgehen, z. B. Viren und Rootkits, die den Hauptstartdatensatz (Master Boot Record, MBR) infizieren oder überschreiben.

Sie können Microsoft Defender Offline verwenden, wenn Sie eine Schadsoftwareinfektion vermuten oder eine sorgfältige Bereinigung des Endpunkts nach einem Schadsoftwareausbruch bestätigen möchten.

In Windows 10 kann Microsoft Defender Offline mit einem Klick direkt über die [Windows Security App ausgeführt werden.](microsoft-defender-security-center-antivirus.md) In früheren Versionen von Windows musste ein Benutzer Microsoft Defender Offline zum Starten von Medien installieren, den Endpunkt neu starten und die startbaren Medien laden.

## <a name="prerequisites-and-requirements"></a>Voraussetzungen und Anforderungen

Microsoft Defender Offline in Windows 10 hat die gleichen Hardwareanforderungen wie Windows 10. 

Weitere Informationen zu Windows 10-Anforderungen finden Sie in den folgenden Themen:

- [Mindesthardwareanforderungen](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Richtlinien für Hardwarekomponenten](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline wird nicht auf Computern mit ARM Oder auf Windows Server Stock Keeping Units unterstützt.

Um Microsoft Defender Offline vom Endpunkt aus ausführen zu können, muss der Benutzer mit Administratorrechten angemeldet sein.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline-Updates

Microsoft Defender Offline verwendet die neuesten auf dem Endpunkt verfügbaren Schutzupdates. es wird immer dann aktualisiert, Windows Defender Antivirus aktualisiert wird. 

> [!NOTE]
> Bevor Sie einen Offlinescan ausführen, sollten Sie versuchen, den Microsoft Defender AV-Schutz zu aktualisieren. Sie können entweder ein Update mit Gruppenrichtlinien erzwingen oder aber normalerweise Updates auf Endpunkten [bereitstellen,](https://www.microsoft.com/security/portal/definitions/adl.aspx)oder Sie können die neuesten Schutzupdates manuell aus dem Microsoft Center zum Schutz vor Malware.

Weitere Informationen finden Sie im Thema Verwalten von [Microsoft Defender Antivirus Security Intelligence-Updates.](manage-protection-updates-microsoft-defender-antivirus.md)

## <a name="usage-scenarios"></a>Verwendungsszenarien

In Windows 10, Version 1607, können Sie einen Offlinescan manuell erzwingen. Wenn sie Windows Defender, dass Microsoft Defender Offline ausgeführt werden muss, wird der Benutzer auf dem Endpunkt aufgefordert. 

Die Notwendigkeit, eine Offlinescan durchzuführen, wird auch im Microsoft Endpoint Manager angezeigt, wenn Sie ihn zum Verwalten Ihrer Endpunkte verwenden.

Die Eingabeaufforderung kann über eine Benachrichtigung erfolgen, ähnlich der folgenden:

![Windows-Benachrichtigung mit der Anforderung zum Ausführen von Microsoft Defender Offline](images/defender/notification.png)

Der Benutzer wird auch innerhalb des Windows Defender benachrichtigt.

In Configuration Manager können Sie den Status von Endpunkten identifizieren, indem Sie zu **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status navigieren.** 

Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.

![Microsoft Endpoint Manager gibt an, dass eine Microsoft Defender Offline-Überprüfung erforderlich ist](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Konfigurieren von Benachrichtigungen

Microsoft Defender Offline-Benachrichtigungen werden in derselben Richtlinieneinstellung wie andere Microsoft Defender AV-Benachrichtigungen konfiguriert.

Weitere Informationen zu Benachrichtigungen in Windows Defender finden Sie im Thema Konfigurieren der Benachrichtigungen, [die auf Endpunkten angezeigt](configure-notifications-microsoft-defender-antivirus.md) werden.

## <a name="run-a-scan"></a>Ausführen eines Scanvorgangs 

> [!IMPORTANT]
> Bevor Sie Microsoft Defender Offline verwenden, stellen Sie sicher, dass Sie alle Dateien speichern und ausgeführte Programme herunterfahren. Die Ausführung der Microsoft Defender Offline-Überprüfung dauert ca. 15 Minuten. Der Endpunkt wird neu gestartet, wenn die Überprüfung abgeschlossen ist. Die Überprüfung wird außerhalb der üblichen Windows-Betriebsumgebung durchgeführt. Die Benutzeroberfläche wird von einer normalen Überprüfung durch den Benutzer Windows Defender. Nach Abschluss der Überprüfung wird der Endpunkt neu gestartet, und Windows wird normal geladen.

Sie können eine Microsoft Defender Offline-Überprüfung wie folgt ausführen:

- PowerShell
- Windows-Verwaltungsinstrumentation (WMI)
- Die Windows Security-App



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Verwenden von PowerShell-Cmdlets zum Ausführen einer Offlinescan

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Start-MpWDOScan
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Ausführen eines Offlinescans mithilfe der Windows-Verwaltungsanweisung (WMI)

Verwenden [](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Sie die MSFT_MpWDOScan-Klasse, um eine Offlinescan ausführen.

Im folgenden WMI-Skriptausschnitt wird sofort eine Microsoft Defender Offline-Überprüfung ausgeführt, die dazu führen wird, dass der Endpunkt neu gestartet wird, der Offlinescan ausgeführt wird und dann neu gestartet und in Windows gestartet wird.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Weitere Informationen finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Verwenden der Windows Defender-Sicherheits-App zum Ausführen einer Offlinescan

1. Öffnen Sie die Windows Security-App, indem Sie auf das Schildsymbol in der Aufgabenleiste klicken oder im Startmenü nach **Defender suchen.**

2. Klicken Sie **auf &** Kachel "Virenschutz" (oder auf das Schildsymbol auf der linken Menüleiste) und dann auf die **Bezeichnung Erweiterte** Überprüfung:
    
3. Wählen **Sie Microsoft Defender Offlinescan aus,** und klicken Sie auf Jetzt **überprüfen.**

    > [!NOTE]
    > In Windows 10, Version 1607, kann der Offlinescan unter **Windows Settings** Update & security Windows Defender oder vom Windows Defender  >    >   ausgeführt werden.


## <a name="review-scan-results"></a>Überprüfen der Scanergebnisse

Microsoft Defender Offline-Scanergebnisse werden im Abschnitt [Scanverlauf der Windows Security App aufgeführt.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Verwandte Artikel

- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Scans und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)