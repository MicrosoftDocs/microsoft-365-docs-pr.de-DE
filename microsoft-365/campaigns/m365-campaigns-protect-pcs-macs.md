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
description: Schützen Sie nicht verwaltete oder bring-your-own-Geräte (BYOD) mit Microsoft 365.
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227499"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Schützen nicht verwalteter Windows 10-PCs und Macs

Sie können Windows 10 PCs und Macs verwalten, indem Sie sie in Microsoft Intune registrieren, wodurch Sie sicherstellen können, dass sie fehlerfrei und sicher sind, bevor Sie auf Daten in Ihrer Umgebung zugreifen. Viele Kampagnen und kleine Unternehmen umfassen jedoch Mitarbeiter, die ihre eigenen Geräte (BYOD) bringen, die nicht von der Organisation verwaltet werden. Verwenden Sie für diese nicht verwalteten PCs und Macs diesen Artikel, um sicherzustellen, dass die Mindestsicherheitsfunktionen konfiguriert sind.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Schützen eines Computers, auf dem Windows 10 oder mac ausgeführt wird

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Wenn Ihr Windows 10 PC oder Mac nicht von Ihrer Organisation verwaltet wird, müssen Sie diese Sicherheitsfunktionen konfigurieren.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Aktivieren der Geräteverschlüsselung**<p>

Die Geräteverschlüsselung ist auf einer Vielzahl von Windows Geräten verfügbar und trägt zum Schutz Ihrer Daten bei, indem sie verschlüsselt werden. Wenn Sie die Geräteverschlüsselung aktivieren, können nur autorisierte Personen auf Ihr Gerät und Ihre Daten zugreifen. Anweisungen finden Sie unter Aktivieren der [Geräteverschlüsselung.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)

 Wenn die Geräteverschlüsselung auf Ihrem Gerät nicht verfügbar ist, können Sie stattdessen die [Standardmäßige BitLocker-Verschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) aktivieren. (BitLocker ist in Windows 10 Home Edition nicht verfügbar.) 

**Schützen Ihres Geräts mit Windows-Sicherheit**<p>
Wenn Sie über Windows 10 verfügen, erhalten Sie den neuesten Antivirenschutz mit Windows-Sicherheit. Wenn Sie Windows 10 zum ersten Mal starten, ist Windows-Sicherheit aktiviert und trägt aktiv zum Schutz Ihres PCs bei, indem sie nach Schadsoftware (Schadsoftware), Viren und Sicherheitsbedrohungen sucht. Windows-Sicherheit verwendet Echtzeitschutz, um alles zu überprüfen, was Sie auf Ihrem PC herunterladen oder ausführen.

Updates für Windows-Sicherheit werden von Windows Update automatisch heruntergeladen, um Ihren PC vor Angriffen zu schützen.

Wenn Sie über eine frühere Version von Windows verfügen und Microsoft Security Essentials verwenden, empfiehlt es sich, zu Windows-Sicherheit zu wechseln. Weitere Informationen finden Sie unter ["Schützen meines Geräts mit Windows-Sicherheit."](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Aktivieren Windows Firewall**<p>
Sie sollten immer Windows Firewall ausführen, auch wenn Sie eine andere Firewall aktiviert haben. Wenn Sie Windows Firewall deaktivieren, kann dies dazu führen, dass Ihr Gerät (und Ihr Netzwerk, falls Sie über eines verfügen) anfälliger für nicht autorisierten Zugriff sind. Anweisungen finden Sie unter [Aktivieren oder Deaktivieren Windows Firewall.](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)

**Verwenden von FileVault zum Verschlüsseln des Mac-Datenträgers**<p>
Die Datenträgerverschlüsselung schützt Daten, wenn Geräte verloren gehen oder gestohlen werden. Die FileVault-Volldatenträgerverschlüsselung trägt dazu bei, nicht autorisierten Zugriff auf die Informationen auf dem Startdatenträger zu verhindern. Anweisungen finden Sie unter [Verwenden von FileVault zum Verschlüsseln des Startdatenträgers auf Ihrem Mac.](https://support.apple.com/HT204837)

**Schützen Des Macs vor Schadsoftware**<p>
Microsoft empfiehlt, zuverlässige Antivirensoftware auf Ihrem Mac zu installieren und zu verwenden. Eine Liste der Optionen finden Sie im folgenden Artikel: [Best Mac Antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Sie können auch das Risiko von Schadsoftware reduzieren, indem Sie Software nur aus zuverlässigen Quellen verwenden. Mit den Einstellungen unter "Sicherheit & Datenschutzeinstellungen" können Sie die Quellen der auf Ihrem Mac installierten Software angeben. Weitere Informationen finden Sie unter ["Schützen Ihres Macs vor Schadsoftware".](https://support.apple.com/kb/PH25087)

**Aktivieren des Firewallschutzes**<p>
Verwenden Sie Firewalleinstellungen, um Ihren Mac vor unerwünschten Kontakten zu schützen, die von anderen Computern initiiert werden, wenn Sie mit dem Internet oder einem Netzwerk verbunden sind. Ohne diesen Schutz ist Ihr Mac möglicherweise anfälliger für nicht autorisierten Zugriff. Anweisungen finden Sie [in der Anwendungsfirewall.](https://support.apple.com/HT201642)
