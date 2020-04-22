---
title: Schützen nicht verwalteter Windows 10-PCs und Macs
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Schützen Sie sich gegen Phishing und andere Angriffe mit Microsoft 365 für Kampagnen.
ms.openlocfilehash: 0cd96cb73ad3d0b38ab1e5ff31c913d97528c2d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632791"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Schützen nicht verwalteter Windows 10-PCs und Macs

Sie können Windows 10-PCs und Macs verwalten, indem Sie Sie in Microsoft InTune registrieren, sodass Sie vor dem Zugriff auf Daten in Ihrer Umgebung sicherstellen, dass Sie gesund und sicher sind. Viele Kampagnen und kleine Unternehmen umfassen jedoch Mitarbeiter, die ihre eigenen Geräte mitbringen (BYOD), die nicht von der Organisation verwaltet werden. Verwenden Sie diesen Artikel für diese nicht verwalteten PCs und Macs, um sicherzustellen, dass die minimalen Sicherheitsfunktionen konfiguriert sind. 

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

Die Geräteverschlüsselung steht für eine Vielzahl von Windows-Geräten zur Verfügung und schützt Ihre Daten durch Verschlüsselung. Wenn Sie die Geräteverschlüsselung aktivieren, können nur autorisierte Personen auf Ihr Gerät und Ihre Daten zugreifen. Anweisungen finden Sie unter [Aktivieren der Geräteverschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .

 Wenn die Geräteverschlüsselung auf Ihrem Gerät nicht verfügbar ist, können Sie stattdessen die standardmäßige [BitLocker-Verschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) aktivieren. (BitLocker ist unter Windows 10 Home Edition nicht verfügbar.) 


**Schützen Ihres Geräts mit Windows-Sicherheit**<p>
Wenn Sie über Windows 10 verfügen, erhalten Sie den neuesten Virenschutz mit Windows-Sicherheit. Wenn Sie Windows 10 zum ersten Mal starten, wird die Windows-Sicherheit aktiv und hilft Ihnen, Ihren PC zu schützen, indem Sie auf Schadsoftware (Schadsoftware), Viren und Sicherheitsbedrohungen überprüft. Windows-Sicherheit verwendet den Echtzeitschutz zum Überprüfen aller Inhalte, die Sie auf Ihrem PC herunterladen oder ausführen.

Windows Update lädt Updates für die Windows-Sicherheit automatisch herunter, um Ihren PC sicher zu halten und vor Bedrohungen zu schützen.

Wenn Sie über eine frühere Version von Windows verfügen und Microsoft Security Essentials verwenden, empfiehlt es sich, zu Windows-Sicherheit zu navigieren. Weitere Informationen finden Sie unter [Help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Aktivieren der Windows-Firewall**<p>
Sie sollten die Windows-Firewall immer ausführen, auch wenn Sie eine andere Firewall aktiviert haben. Durch das Deaktivieren der Windows-Firewall wird möglicherweise Ihr Gerät (und Ihr Netzwerk, falls vorhanden) anfälliger für nicht autorisierten Zugriff. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Windows-Firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) für Anweisungen

## <a name="mac"></a>[Mac](#tab/Mac)
**Verwenden von FileVault zum Verschlüsseln des Mac-Datenträgers**<p>
Durch die Datenträgerverschlüsselung werden Daten geschützt, wenn Geräte verloren gehen oder gestohlen werden. FileVault-Verschlüsselung mit vollständiger Festplatte verhindert nicht autorisierten Zugriff auf die Informationen auf dem Startdatenträger. Anweisungen dazu finden Sie unter [Verwenden von FileVault zum Verschlüsseln des Startdatenträgers auf dem Mac](https://support.apple.com/HT204837) .

**Schützen des Mac vor Schadsoftware**<p>
Microsoft empfiehlt die Installation und Verwendung zuverlässiger Antivirensoftware auf Ihrem Mac. Im folgenden Artikel finden Sie eine Liste der Optionen: [Best Mac Antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Sie können das Risiko von Schadsoftware auch reduzieren, indem Sie Software nur aus zuverlässigen Quellen verwenden. Mit den Einstellungen in Sicherheits & Datenschutzeinstellungen können Sie die auf Ihrem Mac installierten Softwarequellen angeben. Weitere Informationen finden Sie unter [Protect Your Mac from Schadsoftware](https://support.apple.com/kb/PH25087).

**Aktivieren des Firewall-Schutzes**<p>
Verwenden Sie Firewalleinstellungen, um Ihren Mac vor unerwünschten Kontakten zu schützen, die von anderen Computern initiiert wurden, wenn Sie mit dem Internet oder einem Netzwerk verbunden sind. Ohne diesen Schutz ist Ihr Mac möglicherweise anfälliger für unbefugten Zugriff. Anweisungen finden Sie unter [Informationen zur Anwendungs Firewall](https://support.apple.com/HT201642) .
