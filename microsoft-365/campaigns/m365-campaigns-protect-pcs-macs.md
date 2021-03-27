---
title: Schützen nicht verwalteter Windows 10-PCs und Macs
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Schützen sie nicht verwaltete oder selbst mitbringende Geräte (BYOD) mit Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398253"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Schützen nicht verwalteter Windows 10-PCs und Macs

Sie können Windows 10-PCs und Macs verwalten, indem Sie sie in Microsoft Intune registrieren, wodurch Sie sicherstellen können, dass sie fehlerfrei und sicher sind, bevor Sie auf Daten in Ihrer Umgebung zugreifen. Viele Kampagnen und kleine Unternehmen umfassen jedoch Mitarbeiter, die ihre eigenen Geräte (BYOD) mitbringen, die nicht von der Organisation verwaltet werden. Verwenden Sie diesen Artikel für diese nicht verwalteten PCs und Macs, um sicherzustellen, dass minimale Sicherheitsfunktionen konfiguriert sind.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Schützen eines Computers mit Windows 10 oder einem Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Wenn Ihr Windows 10-PC oder Mac nicht von Ihrer Organisation verwaltet wird, müssen Sie diese Sicherheitsfunktionen konfigurieren.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Aktivieren der Geräteverschlüsselung**<p>

Die Geräteverschlüsselung ist auf einer Vielzahl von Windows-Geräten verfügbar und schützt Ihre Daten durch Verschlüsselung. Wenn Sie die Geräteverschlüsselung aktivieren, können nur autorisierte Personen auf Ihr Gerät und Ihre Daten zugreifen. Anweisungen [finden Sie unter Aktivieren der Geräteverschlüsselung.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)

 Wenn die Geräteverschlüsselung auf Ihrem Gerät nicht verfügbar ist, können Sie stattdessen die standardmäßige [BitLocker-Verschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) aktivieren. (BitLocker ist unter Windows 10 Home Edition nicht verfügbar.) 

**Schützen Ihres Geräts mit Windows Security**<p>
Wenn Sie über Windows 10 verfügen, erhalten Sie den neuesten Antivirenschutz mit Windows Security. Wenn Sie Windows 10 zum ersten Mal starten, ist Windows Security aktiv und hilft aktiv, Ihren PC zu schützen, indem Sie nach Schadsoftware (Schadsoftware), Viren und Sicherheitsbedrohungen suchen. Windows Security verwendet Echtzeitschutz, um alles zu überprüfen, was Sie auf Ihrem PC herunterladen oder ausführen.

Updates für Windows-Sicherheit werden von Windows Update automatisch heruntergeladen, um Ihren PC vor Angriffen zu schützen.

Wenn Sie über eine frühere Version von Windows verfügen und Microsoft Security Essentials verwenden, sollten Sie zu Windows Security wechseln. Weitere Informationen finden Sie unter [Hilfe zum Schutz meines Geräts mit Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Aktivieren der Windows-Firewall**<p>
Sie sollten die Windows-Firewall immer ausführen, auch wenn eine andere Firewall aktiviert ist. Wenn Sie die Windows-Firewall deaktivieren, ist Ihr Gerät (und Ihr Netzwerk, falls Sie über eins verfügen) möglicherweise anfälliger für nicht autorisierten Zugriff. Anweisungen [finden Sie unter Aktivieren oder Deaktivieren der Windows-Firewall.](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)

**Verschlüsseln Ihres Mac-Datenträgers mithilfe von FileVault**<p>
Die Datenträgerverschlüsselung schützt Daten, wenn Geräte verloren gehen oder gestohlen werden. Die FileVault-Volldatenträgerverschlüsselung verhindert nicht autorisierten Zugriff auf die Informationen auf dem Startdatenträger. Anweisungen [finden Sie unter Verwenden von FileVault zum](https://support.apple.com/HT204837) Verschlüsseln des Startdatenträgers auf Ihrem Mac.

**Schützen Ihres Mac vor Schadsoftware**<p>
Microsoft empfiehlt, zuverlässige Antivirensoftware auf Ihrem Mac zu installieren und zu verwenden. Eine Liste der Auswahlmöglichkeiten finden Sie im folgenden Artikel: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Sie können auch das Risiko von Schadsoftware verringern, indem Sie Software nur aus zuverlässigen Quellen verwenden. Mit den Einstellungen unter & Datenschutzeinstellungen können Sie die auf Ihrem Mac installierten Softwarequellen angeben. Weitere Informationen finden Sie unter [Schützen Ihres Mac vor Schadsoftware](https://support.apple.com/kb/PH25087).

**Aktivieren des Firewallschutzes**<p>
Verwenden Sie Firewalleinstellungen, um Ihren Mac vor unerwünschten Kontakten zu schützen, die von anderen Computern initiiert werden, wenn Sie mit dem Internet oder einem Netzwerk verbunden sind. Ohne diesen Schutz ist Ihr Mac möglicherweise anfälliger für nicht autorisierten Zugriff. Anweisungen [zur Anwendungsfirewall](https://support.apple.com/HT201642) finden Sie unter.
