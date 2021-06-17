---
title: Konfigurieren der Funktionen zur Verringerung der Angriffsfläche
description: Verwenden Sie Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und Gruppenrichtlinien, um die Verringerung der Angriffsfläche zu konfigurieren.
keywords: asr, Attack Surface Reduction, Windows Defender, Microsoft Defender, Antivirus, AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984448"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Konfigurieren der Funktionen zur Verringerung der Angriffsfläche

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender für Endpunkt umfasst mehrere Funktionen zur Verringerung der Angriffsfläche. Weitere Informationen finden Sie unter ["Übersicht über die Funktionen zur Verringerung der Angriffsfläche".](overview-attack-surface-reduction.md) Führen Sie die folgenden Schritte aus, um die Verringerung der Angriffsfläche in Ihrer Umgebung zu konfigurieren:

1. [Aktivieren Sie die hardwarebasierte Isolation für Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)

2. Aktivieren Sie die Anwendungssteuerung.

   1. Überprüfen Sie die Basisrichtlinien in Windows. Siehe [Beispiel für Basisrichtlinien.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)
   2. Weitere Informationen finden Sie im [Entwurfshandbuch für Windows Defender Anwendungssteuerung.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. Weitere Informationen finden Sie unter [Deploying Windows Defender Application Control (WDAC)-Richtlinien.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [Aktivieren Sie den kontrollierten Ordnerzugriff.](enable-controlled-folders.md)

4. [Aktivieren Sie den Netzwerkschutz.](enable-network-protection.md)

5. [Aktivieren Des Exploit-Schutzes.](enable-exploit-protection.md)

6. [Konfigurieren Sie Regeln zur Verringerung der Angriffsfläche.](enable-attack-surface-reduction.md)

7. Richten Sie Ihre Netzwerkfirewall ein.

   1. Hier erhalten Sie eine Übersicht über [Windows Defender Firewall mit erweiterter Sicherheit.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Verwenden Sie die [Windows Defender Firewall-Entwurfshandbuchs,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) um zu entscheiden, wie Sie Ihre Firewallrichtlinien entwerfen möchten.
   3. Verwenden Sie das [Windows Defender Firewall-Bereitstellungshandbuch,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) um die Firewall Ihrer Organisation mit erweiterter Sicherheit einzurichten.

> [!TIP]
> In den meisten Fällen können Sie beim Konfigurieren von Attack Surface Reduction-Funktionen zwischen verschiedenen Methoden wählen:

> - Microsoft Endpoint Manager (die jetzt Microsoft Intune und Microsoft Endpoint Configuration Manager umfasst)
> - Gruppenrichtlinien
> - PowerShell-Cmdlets
