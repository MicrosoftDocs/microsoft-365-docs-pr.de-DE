---
title: Definieren, wie mobile Geräte von Microsoft Defender Antivirus aktualisiert werden
description: Verwalten Sie, wie mobile Geräte, z. B. Laptops, mit Microsoft Defender Antivirus Schutzupdates aktualisiert werden sollen.
keywords: Updates, Schutz, Updates planen, Akku, mobiles Gerät, Laptop, Notizbuch, Anmelden, Microsoft Update, wsus, außer Kraft setzen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926007"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Mobile Geräte und VMs erfordern möglicherweise mehr Konfiguration, um sicherzustellen, dass die Leistung nicht durch Updates beeinträchtigt wird.

Es gibt zwei Einstellungen, die für diese Geräte nützlich sind:

- Aktivieren von Microsoft Update auf mobilen Computern ohne WSUS-Verbindung
- Verhindern von Security Intelligence-Updates bei Akkubetrieb

Die folgenden Artikel können auch in diesen Situationen hilfreich sein:
- [Konfigurieren von geplanten Scans und Nachholscans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Bereitstellungshandbuch für Microsoft Defender Antivirus in einer VDI-Umgebung (Virtual Desktop Infrastructure)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Aktivieren von Microsoft Update auf mobilen Computern ohne WSUS-Verbindung

Sie können Microsoft Update verwenden, um die Security Intelligence auf mobilen Geräten, die Microsoft Defender Antivirus ausgeführt werden, auf dem neuesten Stand zu halten, wenn sie nicht mit dem Unternehmensnetzwerk verbunden sind oder andernfalls keine WSUS-Verbindung haben. 

Dies bedeutet, dass Schutzupdates an Geräte (über Microsoft Update) übermittelt werden können, auch wenn Sie WSUS so festgelegt haben, dass Microsoft Update überschrieben wird.

Sie können Microsoft Update auf dem mobilen Gerät auf eine der folgenden Arten aktivieren:

- Ändern Sie die Einstellung mithilfe von Gruppenrichtlinien.
- Verwenden Sie ein VBScript, um ein Skript zu erstellen, und führen Sie es dann auf jedem Computer in Ihrem Netzwerk aus.
- Melden Sie sich manuell über das **Menü Einstellungen** auf jedem Computer in Ihrem Netzwerk an.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Verwenden von Gruppenrichtlinien zum Aktivieren von Microsoft Update

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Wählen Sie **"Richtlinien"** und dann **"Administrative Vorlagen" aus.**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signaturupdates.**

5. Legen Sie **"Sicherheitsintelligenz-Updates von Microsoft Update zulassen"** auf **"Aktiviert"** fest, und wählen Sie dann  **"OK"** aus.


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Verwenden von VBScript zum Anmelden an Microsoft Update

1. Verwenden Sie die Anweisungen im [MSDN-Artikel "Anmelden bei Microsoft Update",](/windows/win32/wua_sdk/opt-in-to-microsoft-update) um VBScript zu erstellen.

2. Führen Sie das VBScript aus, das Sie auf jedem Computer in Ihrem Netzwerk erstellt haben.

### <a name="manually-opt-in-to-microsoft-update"></a>Manuelles Anmelden bei Microsoft Update

1. Öffnen Sie **Windows Update** in Update **& Sicherheitseinstellungen** auf dem Computer, den Sie sich anmelden möchten.

2. Wählen Sie **"Erweiterte** Optionen" aus.

3. Aktivieren Sie das Kontrollkästchen für **"Updates für andere Microsoft-Produkte bereitstellen", wenn ich Windows aktuaktuiere.**

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Verhindern von Security Intelligence-Updates bei Akkubetrieb

Sie können Microsoft Defender Antivirus so konfigurieren, dass nur Schutzupdates heruntergeladen werden, wenn der PC mit einer kabelgebundenen Stromquelle verbunden ist. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Verwenden von Gruppenrichtlinien, um Sicherheitsupdates bei Akkubetrieb zu verhindern

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und öffnen Sie es zur Bearbeitung.

2.  Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3.  Wählen Sie **"Richtlinien"** und dann **"Administrative Vorlagen" aus.**

4.  Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signaturupdates,** und legen Sie dann **"Allow security intelligence updates when running on battery power" auf** **"Disabled"** fest. Wählen Sie dann **OK** aus. 

Diese Aktion verhindert, dass Schutzupdates heruntergeladen werden, wenn der PC mit Akkubetrieb betrieben wird.

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Aktualisieren und Verwalten von Microsoft Defender Antivirus in Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)