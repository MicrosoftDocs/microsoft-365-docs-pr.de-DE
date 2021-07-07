---
title: Auswerten des Netzwerkschutzes
description: Erfahren Sie, wie der Netzwerkschutz funktioniert, indem Sie allgemeine Szenarien testen, vor denen er schützt.
keywords: Netzwerkschutz, Exploits, schädliche Website, IP, Domäne, Domänen, auswerten, testen, Demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98e4c80c2e0262712885f1e7a2da82886b2ebe80
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309364"
---
# <a name="evaluate-network-protection"></a>Auswerten des Netzwerkschutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter eine beliebige Anwendung verwenden, um auf gefährliche Domänen zuzugreifen, die Phishing-Angriffe, Exploits und andere schädliche Inhalte im Internet hosten können.

Dieser Artikel hilft Ihnen bei der Bewertung des Netzwerkschutzes, indem er das Feature aktiviert und Sie zu einer Testwebsite führt. Die Websites in diesem Evaluierungsartikel sind nicht bösartig. Es handelt sich um speziell erstellte Websites, die vorgeben, bösartig zu sein. Die Website repliziert das Verhalten, das auftreten würde, wenn ein Benutzer eine schädliche Website oder Domäne besucht.

> [!TIP]
> Sie können auch die Microsoft Defender Testground-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu sehen, wie andere Schutzfeatures funktionieren.

## <a name="enable-network-protection-in-audit-mode"></a>Aktivieren des Netzwerkschutzes im Überwachungsmodus

Aktivieren Sie den Netzwerkschutz im Überwachungsmodus, um festzustellen, welche IP-Adressen und Domänen blockiert worden wären. Sie können sicherstellen, dass dies keine Auswirkungen auf Branchen-Apps hat, oder eine Vorstellung davon erhalten, wie oft Blöcke auftreten.

1. Geben Sie **PowerShell** in die Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **"Als Administrator ausführen"** aus.
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Besuchen einer (gefälschten) schädlichen Domäne

1. Öffnen Sie Internet Explorer, Google Chrome oder einen anderen Browser Ihrer Wahl.

1. Wechseln Sie zu [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Die Netzwerkverbindung ist zulässig, und es wird eine Testmeldung angezeigt.

![Beispielbenachrichtigung, die besagt, dass die Verbindung blockiert ist: Ihr IT-Administrator hat bewirkt, dass Windows-Sicherheit diese Netzwerkverbindung blockiert hat. Wenden Sie sich an Ihren IT-Helpdesk.](images/np-notif.png)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Überprüfen von Netzwerkschutzereignissen in Windows Ereignisanzeige

Um Apps zu überprüfen, die blockiert worden wären, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows-Defender/Operational-Protokoll nach Ereignis-ID 1125. In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.

| Ereignis-ID | Bereitstellen/Quelle | Beschreibung |
|-|-|-|
|5007 | Windows Defender (Betriebsbereit) | Ereignis, wenn Einstellungen geändert werden |
|1125 | Windows Defender (Betriebsbereit) | Ereignis, wenn eine Netzwerkverbindung überwacht wird |
|1126 | Windows Defender (Betriebsbereit) | Ereignis, wenn eine Netzwerkverbindung blockiert wird |

## <a name="see-also"></a>Siehe auch

* [Netzwerkschutz](network-protection.md)
* [Netzwerkschutz aktivieren](enable-network-protection.md)
* [Problembehandlung beim Netzwerkschutz](troubleshoot-np.md)
