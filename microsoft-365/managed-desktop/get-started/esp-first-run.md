---
title: Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite
description: Vorgehensweise Bereitstellen der ESP-Umgebung, der verwendeten Einstellungen und der Konfigurationsänderungen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7337dd28f7940256d1753cd4c0b6309406fab2d1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305270"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite

Microsoft Managed Desktop verwendet sowohl [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) als auch Microsoft intunes [Registrierungs Status Seite (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) , um die bestmögliche Erstausführung für Ihre Benutzer bereitzustellen.

Die Seite Registrierungs Status befindet sich derzeit in der öffentlichen Vorschau.

## <a name="initial-deployment"></a>Erstbereitstellung

Um die ESP-Erfahrung bereitzustellen, müssen Sie Geräte im Microsoft Managed Desktop-Dienst registrieren. Weitere Informationen zur Registrierung finden Sie unter [Registrieren neuer Geräte selbst](../get-started/register-devices-self.md) oder [Schritte für Partner zum Registrieren von Geräten](../get-started/register-devices-partner.md).

Nachdem Ihre Geräte beim Dienst registriert wurden, können Sie ESP für Ihre von Microsoft verwalteten Desktop Geräte aktivieren, indem Sie ein Support Ticket über das [Verwaltungs Portal](https://portal.azure.com/)hinterlegen. Die ESP-Konfiguration wird zunächst in der Test Gruppe bereitgestellt, wenn Sie das Ticket archivieren. Sie wird für die anderen nachfolgenden Bereitstellungsgruppen (zuerst, schnell und breit) jeweils 24 Stunden bereitgestellt. Um die Bereitstellung anzuhalten, müssen Sie ein weiteres Ticket anfordern, in dem Vorgänge angehalten werden.

## <a name="autopilot-profile-settings"></a>Autopilot-Profileinstellungen

Microsoft Managed Desktop verwendet diese Einstellungen im Autopilot-Profil, das für die Geräte ihrer Benutzer verwendet wird:


|Einstellung  |Wert  |
|---------|---------|
|Bereitstellungsmodus |  Benutzer gesteuert       |
|Beitreten zu Azure AD als     |  Azure AD verbunden       |
|Sprache (Region)     | Betriebssystemstandard        |
|Automatisches Konfigurieren der Tastatur     | Nein        |
|Microsoft-Software-Lizenzbedingungen     |  Ausblenden       |
|Datenschutzeinstellungen     | Ausblenden        |
|Optionen für das Ausblenden von Änderungs Konten     | Anzeigen        |
|Typ des Benutzerkontos     |  Standard       |
|Weiße Hand Schuh-OOBE zulassen     |  Ja       |
|Gerätenamen Vorlage anwenden     | Ja        |
|Geben Sie einen Namen ein.     | MMD-% Rand: 11%        |

> [!NOTE]
> Während "White Glove"-Prothesen nur für Kunden mit aktivierter ESP aktiviert werden, wird Sie derzeit nicht in Microsoft Managed Desktop unterstützt.

## <a name="enrollment-status-page-settings"></a>Einstellungen für die Registrierungs Status Seite

Microsoft Managed Desktop verwendet diese Einstellungen für die Anmelde Status-Seiten Erfahrung:


|Einstellung  |Wert  |
|---------|---------|
|Anzeigen des Status von App-und Profilkonfiguration     | Ja        |
|Fehlermeldung anzeigen, wenn die Installation länger als die angegebene Anzahl von Minuten dauert     |  60       |
|Benutzerdefinierte Meldung anzeigen, wenn ein Zeit Begrenzungs Fehler auftritt     |  Ja       |
|Fehlermeldung     | Ja, es dauert etwas länger, bis Ihr Gerät eingerichtet ist als erwartet. Klicken Sie unten, um loszulegen und die Einrichtung im Hintergrund abzuschließen.        |
|Zulassen, dass Benutzer Protokolle zu Installationsfehlern sammeln     |  Ja       |
|Nur Seite auf Geräten anzeigen, die mit Out-of-Box-Erfahrung (OOBE) vorgestellt wurden     | Ja        |
|Geräteverwendung blockieren, bis alle apps und Profile installiert sind     |  Ja       |
|Benutzern das Zurücksetzen des Geräts gestatten, wenn ein Installationsfehler auftritt     |  Ja       |
|Benutzer dürfen Geräte verwenden, wenn ein Installationsfehler auftritt     |  Ja       |
|Geräteverwendung blockieren, bis diese erforderlichen apps installiert sind, wenn Sie dem Benutzer/Gerät zugewiesen sind     |  Moderne Arbeitsplatz-Zeitkorrektur       |



Die Anmelde Status-Seiten Erfahrung erfolgt in drei Phasen. Weitere Informationen finden Sie unter [Registrierung Status Page Tracking Information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

Die Erfahrung geht wie folgt vor:

1. Die Autopiloten-Erfahrung wird gestartet, und der Benutzer gibt seine Anmeldeinformationen ein.
2. Das Gerät öffnet die Seite Registrierungs Status und fährt über die Geräte Vorbereitung und die Geräte Setup Phasen fort. Der dritte Schritt (Kontoeinrichtung) wird *derzeit* in der Konfiguration von Microsoft Managed Desktop übersprungen, da der Benutzer ESP deaktiviert ist. Das Gerät wird neu gestartet.
3. Nach dem Neustart öffnet das Gerät die Windows-Anmeldeseite für **andere Benutzer**.
4. Die Benutzer geben Ihre Anmeldeinformationen erneut ein, und der Desktop wird geöffnet.

> [!NOTE]
> Win32-apps werden nur bei ESP bereitgestellt, wenn die Windows 10-Version 1903 oder höher ist.

![Start Seite des Autopilot-Setups mit den Phasen "Geräte Vorbereitung" und "Geräte Setup".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Weiße Hand Schuh Prothesen

Microsoft Managed Desktop unterstützt derzeit nicht die Funktion "weißer Handschuh" von Windows Autopilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Ändern der Einstellungen für "Autopilot" und "Registrierungs Status"

Wenn das von Microsoft Managed Desktop verwendete Setup nicht genau Ihren Anforderungen entspricht, können Sie ein Support Ticket über das [Verwaltungs Portal](https://portal.azure.com/)einreichen. Im folgenden finden Sie einige Beispiele für die Konfigurationstypen, die Sie möglicherweise benötigen:

### <a name="autopilot-settings-change"></a>Änderung von Autopilot-Einstellungen

Möglicherweise möchten Sie eine andere Gerätenamen Vorlage anfordern. Sie können den Bereitstellungsmodus jedoch nicht ändern, mit Azure as, Datenschutzeinstellungen oder Benutzerkontotyp beitreten.

### <a name="enrollment-status-page-settings-change"></a>Änderung der Registrierungs Status-Seiteneinstellungen

- Eine längere Anzahl von Minuten für die Einstellung "Fehler anzeigen, wenn die Installation länger dauert als die angegebene Anzahl von Minuten".
- Die angezeigte Fehlermeldung
- Hinzufügen oder Entfernen von Anwendungen in der "Geräteverwendung blockieren, bis diese erforderlichen apps installiert sind, wenn Sie der Benutzer/Gerät"-Einstellung zugewiesen sind.

## <a name="required-applications"></a>Erforderliche Anwendungen

- Sie müssen auf Anwendungen in den modernen Arbeitsplatz- *Gerätegruppen* Test, First, fast und Broad abzielen. Anwendungen müssen im Kontext "System" installiert werden. Stellen Sie sicher, dass Sie die Tests mit ESP in der Test Gruppe abschließen, bevor Sie Sie allen Gruppen zuweisen.
- Für keine Anwendungen sollte ein Neustart des Geräts erforderlich sein. Es wird empfohlen, dass Anwendungen auf "nichts tun" festgelegt werden, wenn Sie das Anwendungspaket erstellen, wenn Sie einen Neustart erfordern.
- Beschränken Sie erforderliche Anwendungen auf die Kernanwendungen, die ein Benutzer sofort benötigt, wenn er sich beim Gerät anmeldet.
- Halten Sie die Gesamtgröße aller Anwendungen zusammen unter 1 GB, um Timeouts während der Anwendungs Installationsphase zu vermeiden.
- Idealerweise sollten apps keine Abhängigkeiten aufweisen. Wenn Sie über apps verfügen, die Abhängigkeiten aufweisen *müssen* , stellen Sie sicher, dass Sie Sie im Rahmen ihrer ESP-Evaluierung konfigurieren, testen und validieren.
- Keine Anwendungen, die den "Benutzerkontext" (beispielsweise "Teams") benötigen, können in die öffentliche Vorschau von ESP aufgenommen werden.
