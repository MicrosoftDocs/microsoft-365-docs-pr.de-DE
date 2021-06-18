---
title: Ausblenden der Microsoft Defender Antivirus-Schnittstelle
description: Sie können die Kachel für Viren- und Bedrohungsschutz in der Windows-Sicherheit-App ausblenden.
keywords: Ui-Sperrmodus, Headless-Modus, App ausblenden, Einstellungen ausblenden, Benutzeroberfläche ausblenden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007668"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Benutzer am Anzeigen oder Interagieren mit der Microsoft Defender Antivirus Benutzeroberfläche hindern

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Mithilfe von Gruppenrichtlinien können Sie verhindern, dass Benutzern auf Endpunkten die Microsoft Defender Antivirus-Schnittstelle angezeigt wird. Sie können auch verhindern, dass sie Scans anhalten.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ausblenden der Microsoft Defender Antivirus-Schnittstelle

In Windows 10, Version 1703, blendet das Ausblenden der Schnittstelle Microsoft Defender Antivirus Benachrichtigungen aus und verhindert, dass die Kachel zum Viren- & Bedrohungsschutz in der Windows-Sicherheit App angezeigt wird.

Mit aktivierter **Einstellung:**

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows-Sicherheit ohne das Schildsymbol und den Abschnitt &quot;Viren- und Bedrohungsschutz&quot;":::

Wenn die Einstellung auf **"Deaktiviert"** festgelegt oder nicht konfiguriert ist:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Screenshot der Windows-Sicherheit mit Schutzsymbolen und Bedrohungsschutzabschnitten":::

>[!NOTE]
>Durch das Ausblenden der Schnittstelle wird auch verhindert, dass Microsoft Defender Antivirus Benachrichtigungen auf dem Endpunkt angezeigt werden. Microsoft Defender für Endpunkt-Benachrichtigungen werden weiterhin angezeigt. Sie können auch [die Benachrichtigungen, die auf Endpunkten angezeigt werden,](configure-notifications-microsoft-defender-antivirus.md) einzeln konfigurieren.

In früheren Versionen von Windows 10 blendet die Einstellung die Windows Defender Clientschnittstelle aus. Wenn der Benutzer versucht, sie zu öffnen, wird eine Warnung mit der Meldung "Ihr Systemadministrator hat den Zugriff auf diese App eingeschränkt" angezeigt.

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Warnmeldung, wenn der Headless-Modus in früheren Versionen als 1703 in Windows 10 aktiviert ist":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Verwenden von Gruppenrichtlinien zum Ausblenden der Microsoft Defender AV-Benutzeroberfläche vor Benutzern

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.**

5. Doppelklicken Sie auf die Einstellung **"Headless UI-Modus aktivieren",** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie auf **OK**. 

Weitere Optionen zum Verhindern, dass Benutzer den Schutz auf ihren PCs ändern, finden Sie unter ["Verhindern,](configure-local-policy-overrides-microsoft-defender-antivirus.md) dass Benutzer richtlinieneinstellungen lokal ändern".

## <a name="prevent-users-from-pausing-a-scan"></a>Verhindern, dass Benutzer eine Überprüfung anhalten

Sie können verhindern, dass Benutzer Scans anhalten. Dies kann hilfreich sein, um sicherzustellen, dass geplante oder bedarfsgesteuerte Scans nicht von Benutzern unterbrochen werden.

> [!NOTE]
> Diese Einstellung wird für Windows 10 nicht unterstützt.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Verwenden von Gruppenrichtlinien, um zu verhindern, dass Benutzer einen Scan anhalten

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur, um **komponenten Microsoft Defender Antivirus**  >  Scan **Windows.**  >  

5. Doppelklicken Sie auf die Einstellung "Benutzern das Anhalten der **Scaneinstellung erlauben",** und legen Sie die Option auf **"Deaktiviert"** fest. Klicken Sie auf **OK**. 

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md)

- [Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)