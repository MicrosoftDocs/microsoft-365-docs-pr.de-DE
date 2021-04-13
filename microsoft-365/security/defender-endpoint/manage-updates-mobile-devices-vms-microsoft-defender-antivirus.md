---
title: Definieren, wie mobile Geräte von Microsoft Defender Antivirus aktualisiert werden
description: Verwalten, wie mobile Geräte, z. B. Laptops, mit Microsoft Defender Antivirus Protection-Updates aktualisiert werden sollen.
keywords: updates, protection, schedule updates, battery, mobile device, laptop, notebook, opt-in, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690395"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Mobile Geräte und virtuelle Computer erfordern möglicherweise mehr Konfiguration, um sicherzustellen, dass die Leistung nicht von Updates betroffen ist.

Es gibt zwei Einstellungen, die für diese Geräte nützlich sind:

- Opt in to Microsoft Update on mobile computers without a WSUS connection
- Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb

Die folgenden Artikel können auch in diesen Situationen hilfreich sein:
- [Konfigurieren geplanter Und Nachholscans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Bereitstellungshandbuch für Microsoft Defender Antivirus in einer Virtuellen Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI)-Umgebung](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Opt in to Microsoft Update on mobile computers without a WSUS connection

Sie können Microsoft Update verwenden, um die Sicherheitsintelligenz auf mobilen Geräten mit Microsoft Defender Antivirus auf dem neuesten Stand zu halten, wenn sie nicht mit dem Unternehmensnetzwerk verbunden sind oder anderweitig keine WSUS-Verbindung haben. 

Dies bedeutet, dass Schutzupdates auf Geräten (über Microsoft Update) zugestellt werden können, auch wenn Sie WSUS so festgelegt haben, dass Microsoft Update außer Kraft gesetzt wird.

Sie können sich auf dem mobilen Gerät auf einer der folgenden Arten für Microsoft Update entscheiden:

- Ändern Sie die Einstellung mit Gruppenrichtlinie.
- Verwenden Sie ein VBScript, um ein Skript zu erstellen, und führen Sie es dann auf jedem Computer im Netzwerk aus.
- Wählen Sie jeden Computer im Netzwerk manuell über das Menü **Einstellungen** aus.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Verwenden von Gruppenrichtlinien zum Opt-in für Microsoft Update

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Wählen **Sie Richtlinien** und dann Administrative Vorlagen **aus.**

4. Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.

5. Legen **Sie Sicherheitsintelligenzupdates von Microsoft Update** zulassen auf **Aktiviert,** und wählen Sie dann **OK aus.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Verwenden eines VBScripts zum Opt-in für Microsoft Update

1. Verwenden Sie die Anweisungen im [MSDN-Artikel Opt-In to Microsoft Update,](/windows/win32/wua_sdk/opt-in-to-microsoft-update) um das VBScript zu erstellen.

2. Führen Sie das vbScript aus, das Sie auf jedem Computer in Ihrem Netzwerk erstellt haben.

### <a name="manually-opt-in-to-microsoft-update"></a>Manuelles Aktivieren von Microsoft Update

1. Öffnen **Sie Windows Update** in Update **&** Sicherheitseinstellungen auf dem Computer, für den Sie sich entscheiden möchten.

2. Wählen Sie **Erweiterte** Optionen aus.

3. Aktivieren Sie das Kontrollkästchen Updates für andere **Microsoft-Produkte geben, wenn ich Windows update.**

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb

Sie können Microsoft Defender Antivirus so konfigurieren, dass nur Schutzupdates heruntergeladen werden, wenn der PC mit einer verkabelten Stromquelle verbunden ist. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Verwenden von Gruppenrichtlinien zum Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb

1.  Öffnen Sie auf dem Computer [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))für die Gruppenrichtlinienverwaltung die Gruppenrichtlinienverwaltungskonsole, wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und öffnen Sie es zur Bearbeitung.

2.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3.  Wählen **Sie Richtlinien** und dann Administrative Vorlagen **aus.**

4.  Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature  >  **Updates,** und legen Sie dann **Allow security intelligence updates when running on battery power** auf Disabled . Wählen Sie dann **OK** aus. 

Mit dieser Aktion wird verhindert, dass Schutzupdates heruntergeladen werden, wenn der PC mit Strom verbunden ist.

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Aktualisieren und Verwalten von Microsoft Defender Antivirus in Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)