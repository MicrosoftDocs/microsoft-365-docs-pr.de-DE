---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie Standard- und zusätzliche Microsoft Defender Antivirus Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
keywords: Benachrichtigungen, Verteidiger, Antivirus, Endpunkt, Verwaltung, Admin
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572345"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In Windows 10 sind Anwendungsbenachrichtigungen über Malwareerkennung und -behebung robuster, konsistenter und präziser.

Benachrichtigungen werden auf Endpunkten angezeigt, wenn manuell ausgelöste und geplante Scans abgeschlossen und Bedrohungen erkannt werden. Diese Benachrichtigungen werden auch im **Benachrichtigungscenter** und in regelmäßigen Zeitabständen eine Zusammenfassung der Scans und Bedrohungserkennungen angezeigt.

Sie können auch konfigurieren, wie Standardbenachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen für einen Neustart oder wenn eine Bedrohung erkannt und behoben wurde.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Konfigurieren der zusätzlichen Benachrichtigungen, die auf Endpunkten angezeigt werden

Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. aktuelle Zusammenfassungen zur Bedrohungserkennung, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mit Gruppenrichtlinien konfigurieren.

> [!NOTE]
> In Windows 10, Version 1607, wurde die Funktion **Erweiterte Benachrichtigungen** genannt und konnte unter **Windows Einstellungen** Update & Security Windows Defender konfiguriert  >    >  werden. In den Gruppenrichtlinieneinstellungen in allen Versionen von Windows 10 wird dies als **erweiterte Benachrichtigungen** bezeichnet.

> [!IMPORTANT]
> Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Bedrohungserkennungs- und Behebungswarnungen, nicht deaktiviert.

**Verwenden Sie die Windows-Sicherheit-App, um zusätzliche Benachrichtigungen zu deaktivieren:**

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.

2. Wählen Sie **Virus & Bedrohungsschutzkachel** (oder das Schildsymbol in der linken Menüleiste) und wählen Sie dann **Virus & Bedrohungsschutzeinstellungen** aus.

3. Scrollen Sie zum Abschnitt **Benachrichtigungen,** und klicken Sie auf **Benachrichtigungseinstellungen ändern**.

4. Schieben Sie den Schalter auf **Aus** oder **Ein,** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.

**Verwenden Sie Gruppenrichtlinien, um zusätzliche Benachrichtigungen zu deaktivieren:**

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungscomputer die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken Sie auf **Verwaltungsvorlagen**.

4. Erweitern Sie die Struktur auf **Windows Komponenten > Microsoft Defender Antivirus > Reporting**.

5. Doppelklicken Sie auf **Erweiterte Benachrichtigungen deaktivieren,** und legen Sie die Option auf **Aktiviert** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

## <a name="configure-standard-notifications-on-endpoints"></a>Konfigurieren von Standardbenachrichtigungen auf Endpunkten

Sie können Gruppenrichtlinien verwenden, um:

- Anzeigen von zusätzlichem, benutzerdefiniertem Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss
- Alle Benachrichtigungen auf Endpunkten ausblenden
- Ausblenden von Neustartbenachrichtigungen auf Endpunkten

Das Ausblenden von Benachrichtigungen kann in Situationen nützlich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus-Schnittstelle ausblenden können. Weitere Informationen finden Sie unter Verhindern von [Benutzern, die die Microsoft Defender Antivirus Benutzeroberfläche anzeigen oder mit ihr interagieren.](prevent-end-user-interaction-microsoft-defender-antivirus.md) 

> [!NOTE]
> Das Ausblenden von Benachrichtigungen erfolgt nur an Endpunkten, für die die Richtlinie bereitgestellt wurde. Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin auf dem [Microsoft Endpoint Manager Endpoint Protection Überwachungsdashboard und in Berichten](/configmgr/protect/deploy-use/monitor-endpoint-protection)angezeigt. 

Unter [Anpassen der Windows-Sicherheit-App für Ihre Organisation](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) finden Sie Anweisungen zum Hinzufügen benutzerdefinierter Kontaktinformationen zu den Benachrichtigungen, die Benutzern auf ihren Computern angezeigt werden.

**Verwenden Sie Gruppenrichtlinien, um Benachrichtigungen auszublenden:**

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungscomputer die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die Struktur, um **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle Windows.** 

4. Doppelklicken Sie auf **Alle Benachrichtigungen unterdrücken,** und legen Sie die Option auf **Aktiviert** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

**Verwenden Sie Gruppenrichtlinien, um Neustartbenachrichtigungen auszublenden:**

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungscomputer die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken Sie auf **Verwaltungsvorlagen**.

4. Erweitern Sie die Struktur, um **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle Windows.**

5. Doppelklicken **Unterdrückt Neustartbenachrichtigungen** und legen Sie die Option auf **Aktiviert** fest. Klicken Sie auf **OK**. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
