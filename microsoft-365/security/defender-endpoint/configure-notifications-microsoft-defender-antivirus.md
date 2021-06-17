---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und andere Microsoft Defender Antivirus-Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
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
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985408"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Konfigurieren Microsoft Defender Antivirus Benachrichtigungen, die auf Endpunkten angezeigt werden

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser. Microsoft Defender Antivirus Benachrichtigungen werden auf Endpunkten angezeigt, wenn Scans abgeschlossen sind und Bedrohungen erkannt werden. Benachrichtigungen folgen sowohl geplanten als auch manuell ausgelösten Scans. Diese Benachrichtigungen werden auch im **Info-Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitabständen angezeigt.

Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie konfigurieren, wie Benachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen, die zu einem Systemneustart auffordern oder darauf hinweisen, dass eine Bedrohung erkannt und behoben wurde.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Konfigurieren von Antivirusbenachrichtigungen mithilfe von Gruppenrichtlinien oder der Windows-Sicherheit-App

Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. aktuelle Zusammenfassungen zur Bedrohungserkennung, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mithilfe von Gruppenrichtlinien konfigurieren.

> [!NOTE]
> In Windows 10 Version 1607 wurde das Feature als **erweiterte Benachrichtigungen** bezeichnet und unter **Windows Einstellungen**  >  **Update & Security**  >  **Windows Defender** konfiguriert. In den Gruppenrichtlinieneinstellungen für alle Versionen von Windows 10 wird das Benachrichtigungsfeature als **erweiterte Benachrichtigungen** bezeichnet.

### <a name="use-group-policy-to-disable-additional-notifications"></a>Verwenden von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

4. Wählen Sie **Administrative Vorlagen** aus.

5. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus** > Reporting**.

6. Doppelklicken Sie auf **"Erweiterte Benachrichtigungen deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest. Wählen Sie dann **OK** aus. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

> [!IMPORTANT]
> Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Verwenden der Windows-Sicherheit-App zum Deaktivieren zusätzlicher Benachrichtigungen

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **"Virus & Bedrohungsschutzeinstellungen"** aus.

3. Scrollen Sie zum Abschnitt **"Benachrichtigungen",** und wählen Sie **"Benachrichtigungseinstellungen ändern" aus.**

4. Ziehen Sie den Schalter auf **"Aus"** oder **"Ein",** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.

> [!IMPORTANT]
> Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Konfigurieren von Standardbenachrichtigungen auf Endpunkten mithilfe von Gruppenrichtlinien

Mithilfe von Gruppenrichtlinien können Sie:

- Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss
- Ausblenden aller Benachrichtigungen auf Endpunkten
- Ausblenden von Neustartbenachrichtigungen auf Endpunkten

Das Ausblenden von Benachrichtigungen kann in Situationen nützlich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus Schnittstelle ausblenden können. Weitere Informationen finden Sie unter ["Verhindern, dass Benutzer die Microsoft Defender Antivirus-Benutzeroberfläche sehen oder damit interagieren."](prevent-end-user-interaction-microsoft-defender-antivirus.md) Das Ausblenden von Benachrichtigungen erfolgt nur auf Endpunkten, auf denen die Richtlinie bereitgestellt wurde. Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im [Microsoft Endpoint Manager Endpoint Protection Überwachungsdashboard und den Berichten](/configmgr/protect/deploy-use/monitor-endpoint-protection)angezeigt. 

Informationen zum Hinzufügen von benutzerdefinierten Kontaktinformationen zu Endpunktbenachrichtigungen finden Sie unter [Anpassen der Windows-Sicherheit-App für Ihre Organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie dann **administrative Vorlagen** aus.

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.** 

5. Doppelklicken Sie auf **"Alle Benachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest. 

6. Wählen Sie **OK** aus. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.**

5. Doppelklicken Sie auf **"Neustartbenachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest. 

5. Wählen Sie **OK** aus. Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.

