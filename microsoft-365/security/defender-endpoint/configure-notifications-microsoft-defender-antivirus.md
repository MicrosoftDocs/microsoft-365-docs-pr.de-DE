---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und zusätzliche Microsoft Defender Antivirus-Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
keywords: Benachrichtigungen, Defender, Antivirus, Endpunkt, Verwaltung, Administrator
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926238"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser.

Benachrichtigungen werden auf Endpunkten angezeigt, wenn manuell ausgelöste und geplante Scans abgeschlossen und Bedrohungen erkannt werden. Diese Benachrichtigungen werden auch im **Info-Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitabständen angezeigt.

Sie können auch konfigurieren, wie Standardbenachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen zum Neustart oder wenn eine Bedrohung erkannt und behoben wurde.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Konfigurieren der zusätzlichen Benachrichtigungen, die auf Endpunkten angezeigt werden

Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. aktuelle Zusammenfassungen zur Bedrohungserkennung, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mithilfe von Gruppenrichtlinien konfigurieren.

> [!NOTE]
> In Windows 10 Version 1607 wurde das Feature als **erweiterte Benachrichtigungen** bezeichnet und konnte unter **Windows Einstellungen** Update & Security Windows Defender konfiguriert  >    >  werden. In den Gruppenrichtlinieneinstellungen in allen Versionen von Windows 10 wird sie als **erweiterte Benachrichtigungen** bezeichnet.

> [!IMPORTANT]
> Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.

**Verwenden Sie die Windows-Sicherheit-App, um zusätzliche Benachrichtigungen zu deaktivieren:**

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **"Virus & Bedrohungsschutzeinstellungen"** aus.

3. Scrollen Sie zum Abschnitt **"Benachrichtigungen",** und klicken Sie auf **"Benachrichtigungseinstellungen ändern".**

4. Ziehen Sie den Schalter auf **"Aus"** oder **"Ein",** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.

**Verwenden Von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen:**

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Berichterstellung.**

5. Doppelklicken Sie auf **"Erweiterte Benachrichtigungen deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

## <a name="configure-standard-notifications-on-endpoints"></a>Konfigurieren von Standardbenachrichtigungen auf Endpunkten

Mithilfe von Gruppenrichtlinien können Sie:

- Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss
- Ausblenden aller Benachrichtigungen auf Endpunkten
- Ausblenden von Neustartbenachrichtigungen auf Endpunkten

Das Ausblenden von Benachrichtigungen kann in Situationen nützlich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus Schnittstelle ausblenden können. Weitere Informationen finden Sie unter ["Verhindern, dass Benutzer die Microsoft Defender Antivirus-Benutzeroberfläche sehen oder damit interagieren."](prevent-end-user-interaction-microsoft-defender-antivirus.md) 

> [!NOTE]
> Das Ausblenden von Benachrichtigungen erfolgt nur auf Endpunkten, auf denen die Richtlinie bereitgestellt wurde. Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im [Microsoft Endpoint Manager Endpoint Protection Überwachungsdashboard und den Berichten](/configmgr/protect/deploy-use/monitor-endpoint-protection)angezeigt. 

Anweisungen zum Hinzufügen von benutzerdefinierten Kontaktinformationen zu den Benachrichtigungen, die Benutzern auf ihren Computern angezeigt werden, finden Sie unter Anpassen der [Windows-Sicherheit-App für Ihre Organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

**Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen:**

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten.**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.** 

4. Doppelklicken Sie auf **"Alle Benachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

**Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen:**

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.**

5. Doppelklicken Sie auf **"Neustartbenachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
