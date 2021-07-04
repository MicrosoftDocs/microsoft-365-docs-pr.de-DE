---
title: Erstellen eines benutzerdefinierten schrittweisen Rollouts für Microsoft Defender-Updates
description: Erfahren Sie, wie Sie unterstützte Tools verwenden, um einen benutzerdefinierten graduellen Rolloutprozess für Updates zu erstellen.
keywords: Updatetools, GPO, Intune, MDM, Microsoft Endpoint Manager, Richtlinie, PowerShell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a7a560cb33190105f8df5922e04aeada4d75f398
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290039"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Erstellen eines benutzerdefinierten schrittweisen Rollouts für Microsoft Defender-Updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Diese Funktionalität erfordert Microsoft Defender Antivirus Version 4.18.2106.X oder höher.

Um Einen eigenen benutzerdefinierten graduellen Rolloutprozess für Defender-Updates zu erstellen, können Sie Gruppenrichtlinien, Microsoft Endpoint Manager und PowerShell verwenden.

In der folgenden Tabelle sind die verfügbaren Gruppenrichtlinieneinstellungen zum Konfigurieren von Updatekanälen aufgeführt:

| Festlegen des Titels  | Beschreibung  | Speicherort  |
|:---|:---|:---|
| Auswählen des Rolloutkanals für graduelle monatliche Microsoft Defender-Plattformupdates  | Aktivieren Sie diese Richtlinie, um anzugeben, wann Geräte Während des monatlichen graduellen Rollouts Microsoft Defender-Plattformupdates erhalten. Betakanal: Geräte, die auf diesen Kanal festgelegt sind, erhalten als Erste neue Updates. Wählen Sie "Betakanal" aus, um an der Identifizierung und Meldung von Problemen an Microsoft teilzunehmen. Geräte im Windows-Insider-Programm sind standardmäßig für diesen Kanal abonniert. Nur zur Verwendung in (manuellen) Testumgebungen und einer begrenzten Anzahl von Geräten.  <br><br>  Aktueller Kanal (Vorschau): Geräte, die auf diesen Kanal festgelegt sind, werden frühestens während des monatlichen schrittweisen Veröffentlichungszyklus Updates angeboten. Wird für Vorproduktions-/Validierungsumgebungen vorgeschlagen.  <br><br>  Aktueller Kanal (bereitgestellt): Geräten werden Updates nach dem monatlichen schrittweisen Releasezyklus angeboten. Es wird empfohlen, einen kleinen, repräsentativen Teil Ihrer Produktionsgesamtheit (ca. 10 %) anzuwenden.  <br><br>  Aktueller Kanal (allgemein): Geräte werden Updates erst nach Abschluss des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, eine breite Palette von Geräten in Ihrer Produktionsgesamtheit anzuwenden (ca. 10-100 %).  <br><br>   Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, bleibt das Gerät während des schrittweisen Releasezyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte.  | Windows Components\Microsoft Defender Antivirus  |
| Auswählen des Rolloutkanals für schrittweise Updates des Microsoft Defender-Moduls  | Aktivieren Sie diese Richtlinie, um anzugeben, wann Geräte während des monatlichen graduellen Rollouts Updates des Microsoft Defender-Moduls erhalten.  <br><br>  Betakanal: Geräte, die auf diesen Kanal festgelegt sind, erhalten als Erste neue Updates. Wählen Sie "Betakanal" aus, um an der Identifizierung und Meldung von Problemen an Microsoft teilzunehmen. Geräte im Windows-Insider-Programm sind standardmäßig für diesen Kanal abonniert. Nur zur Verwendung in (manuellen) Testumgebungen und einer begrenzten Anzahl von Geräten.  <br><br>  Aktueller Kanal (Vorschau): Geräte, die auf diesen Kanal festgelegt sind, werden frühestens während des monatlichen schrittweisen Veröffentlichungszyklus Updates angeboten. Wird für Vorproduktions-/Validierungsumgebungen vorgeschlagen.  <br><br>  Aktueller Kanal (bereitgestellt): Geräten werden Updates nach dem monatlichen schrittweisen Releasezyklus angeboten. Es wird empfohlen, einen kleinen, repräsentativen Teil Ihrer Produktionsgesamtheit (ca. 10 %) anzuwenden.  <br><br>  Aktueller Kanal (allgemein): Geräte werden Updates erst nach Abschluss des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, eine breite Palette von Geräten in Ihrer Produktionsgesamtheit anzuwenden (ca. 10-100 %).  <br><br>  Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, bleibt das Gerät während des schrittweisen Releasezyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte.  | Windows Components\Microsoft Defender Antivirus  |
| Auswählen des Rolloutkanals für schrittweise tägliche Microsoft Defender-Definitionsupdates  | Aktivieren Sie diese Richtlinie, um anzugeben, wann Geräte während des täglichen graduellen Rollouts Microsoft Defender-Definitionsupdates erhalten. <br><br> Aktueller Kanal (bereitgestellt): Geräten werden nach dem Veröffentlichungszyklus Updates angeboten. Es wird empfohlen, einen kleinen, repräsentativen Teil der Produktionsgesamtheit (~10 %) anzuwenden. <br><br>   Aktueller Kanal (allgemein): Geräte werden Updates erst nach Abschluss des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, eine breite Palette von Geräten in Ihrer Produktionsgesamtheit anzuwenden (ca. 10-100 %). <br><br>   Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, bleibt das Gerät während des täglichen Veröffentlichungszyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte.  | Windows Components\Microsoft Defender Antivirus  |
| Deaktivieren des graduellen Rollouts von Microsoft Defender-Updates  | Aktivieren Sie diese Richtlinie, um den graduellen Rollout von Defender-Updates zu deaktivieren. <br><br> Aktueller Kanal (allgemein): Geräten, die auf diesen Kanal festgelegt sind, werden während des schrittweisen Veröffentlichungszyklus zuletzt Updates angeboten. Am besten geeignet für Rechenzentrumscomputer, die nur eingeschränkte Updates erhalten. <br><br> Hinweis: Diese Einstellung gilt sowohl für monatliche als auch für tägliche Defender-Updates und setzt alle zuvor konfigurierten Kanalauswahlen für Plattform- und Modulupdates außer Kraft. <br><br> Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, verbleibt das Gerät im aktuellen Kanal (Standard), sofern in bestimmten Kanälen für Plattform- und Modulupdates nichts anderes angegeben ist. Bleiben Sie während des schrittweisen Freigabezyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte.  | Windows Components\Microsoft Defender Antivirus  |

## <a name="group-policy"></a>Gruppenrichtlinien

> [!NOTE]
> Eine aktualisierte Defender ADMX-Vorlage wird zusammen mit der 21H2-Version von Windows 10 veröffentlicht. Eine nicht lokalisierte Version kann unter heruntergeladen https://github.com/microsoft/defender-updatecontrols werden.

Sie können [gruppenrichtlinien](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)   verwenden, um Microsoft Defender Antivirus auf Ihren Endpunkten zu konfigurieren und zu verwalten.

Im Allgemeinen können Sie das folgende Verfahren verwenden, um Microsoft Defender Antivirus Gruppenrichtlinieneinstellungen zu konfigurieren oder zu ändern:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die  **Gruppenrichtlinien-Verwaltungskonsole,** klicken Sie mit der rechten Maustaste auf das **Gruppenrichtlinienobjekt** , das Sie konfigurieren möchten, und klicken Sie auf  **"Bearbeiten".**

2. Navigieren Sie mithilfe des Gruppenrichtlinienverwaltungs-Editors zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur, um **komponenten > Microsoft Defender Antivirus Windows.**

5. Erweitern Sie den Abschnitt (in der Tabelle in diesem Thema als **Speicherort**   bezeichnet), der die zu konfigurierende Einstellung enthält, doppelklicken Sie auf die Einstellung, um sie zu öffnen, und nehmen Sie Konfigurationsänderungen vor.

6. [Stellen Sie das aktualisierte Gruppenrichtlinienobjekt wie gewohnt](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)bereit.

## <a name="intune"></a>Intune

Folgen Sie den Anweisungen im folgenden Link, um eine benutzerdefinierte Richtlinie in Intune zu erstellen:

[Hinzufügen von benutzerdefinierten Einstellungen für Windows 10 Geräte in Microsoft Intune – Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

Weitere Informationen zu den Defender-CSPs, die für den graduellen Rollout-Prozess verwendet werden, finden Sie unter [Defender CSP.](/windows/client-management/mdm/defender-csp)

## <a name="powershell"></a>PowerShell

Verwenden Sie das `Set-MpPreference` Cmdlet, um das Rollout der graduellen Updates zu konfigurieren.

Verwenden Sie die folgenden Parameter:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Beispiel:

Dient zum Konfigurieren von `Set-MpPreference -PlatformUpdatesChannel Beta` Plattformupdates für die Eintreffen aus dem Betakanal.

Weitere Informationen zu den Parametern und deren Konfiguration finden Sie unter [Set-MpPreference (Defender) | Microsoft Docs](/powershell/module/defender/set-mppreference).
