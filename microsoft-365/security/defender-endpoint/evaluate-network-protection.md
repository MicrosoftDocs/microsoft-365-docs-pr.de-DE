---
title: Auswerten des Netzwerkschutzes
description: Erfahren Sie, wie der Netzwerkschutz funktioniert, indem Sie gängige Szenarien testen, vor denen er schützt.
keywords: Netzwerkschutz, Exploits, schädliche Website, IP, Domäne, Domänen, Evaluieren, Testen, Demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ade50e85dbfcf5f59921a65d5b97bb47d21e5b12
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570924"
---
# <a name="evaluate-network-protection"></a>Auswerten des Netzwerkschutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können.

Dieser Artikel hilft Ihnen bei der Bewertung des Netzwerkschutzes, indem Sie das Feature aktivieren und Sie zu einer Testwebsite führen. Die Websites in diesem Evaluierungsartikel sind nicht bösartig. Es sind speziell erstellte Websites, die vorgeben, bösartig zu sein. Die Website repliziert das Verhalten, das auftreten würde, wenn ein Benutzer eine schädliche Website oder Domäne besuchte.

> [!TIP]
> Sie können auch die Microsoft Defender Testground-Website unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu sehen, wie andere Schutzfunktionen funktionieren.

## <a name="enable-network-protection-in-audit-mode"></a>Aktivieren des Netzwerkschutzes im Überwachungsmodus

Aktivieren Sie den Netzwerkschutz im Überwachungsmodus, um zu sehen, welche IP-Adressen und Domänen blockiert worden wären. Sie können sicherstellen, dass sich dies nicht auf Business-Apps aus wirkt, oder Sie können sich eine Vorstellung davon machen, wie oft Blöcke auftreten.

1. Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **maustaste Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Besuchen einer (gefälschten) bösartigen Domäne

1. Öffnen Sie Internet Explorer, Google Chrome oder einen anderen Browser Ihrer Wahl.

1. Wechseln Sie zu [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Die Netzwerkverbindung ist zulässig, und es wird eine Testnachricht angezeigt.

![Beispielbenachrichtigung mit der Meldung "Verbindung blockiert": Ihr IT-Administrator hat windows Security dazu verangert, diese Netzwerkverbindung zu blockieren. Wenden Sie sich an Ihren IT-Helpdesk.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Überprüfen von Netzwerkschutzereignissen in der Windows-Ereignisanzeige

Um Apps zu überprüfen, die blockiert wurden, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows-Defender/Operational-Protokoll nach Ereignis-ID 1125. In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.

| Ereignis-ID | Bereitstellen/Quelle | Beschreibung |
|-|-|-|
|5007 | Windows Defender (Betriebsbereit) | Ereignis, wenn Einstellungen geändert werden |
|1125 | Windows Defender (Betriebsbereit) | Ereignis, wenn eine Netzwerkverbindung überwacht wird |
|1126 | Windows Defender (Betriebsbereit) | Ereignis, wenn eine Netzwerkverbindung blockiert wird |

## <a name="see-also"></a>Siehe auch

* [Netzwerkschutz](network-protection.md)
* [Aktivieren des Netzwerkschutzes](enable-network-protection.md)
* [Problembehandlung beim Netzwerkschutz](troubleshoot-np.md)
