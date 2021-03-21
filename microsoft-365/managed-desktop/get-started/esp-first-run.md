---
title: Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite
description: Bereitstellen der ESP-Erfahrung, der verwendeten Einstellungen und Konfigurationsänderungen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ec3758a2c452b5b20deab3b3776d631ebd48eaef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921942"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite

Microsoft Managed Desktop verwendet [sowohl Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) als auch die Registrierungsstatusseite [(Enrollment Status Page, ESP)](/windows/deployment/windows-autopilot/enrollment-status) von Microsoft Intune, um Ihren Benutzern die bestmögliche Erstlauferfahrung zu bieten.

Die Registrierungsstatusseite befindet sich derzeit in der öffentlichen Vorschau.

## <a name="initial-deployment"></a>Erstbereitstellung

Um die ESP-Erfahrung zur Verfügung zu stellen, müssen Sie Geräte im Microsoft Managed Desktop-Dienst registrieren. Weitere Informationen zur Registrierung finden Sie unter [Registrieren neuer Geräte selbst](../get-started/register-devices-self.md) oder Schritte für Partner zum Registrieren von [Geräten.](../get-started/register-devices-partner.md)

Sobald Ihre Geräte beim Dienst registriert sind, können Sie ESP für Ihre Microsoft Managed Desktop-Geräte aktivieren, indem Sie ein Supportticket über das [Admin Portal einreichen.](https://portal.azure.com/) Wir stellen die ESP-Konfiguration bei der Ticketdatei zunächst in der Testgruppe zur Bereitstellung. Es wird alle 24 Stunden für die anderen nachfolgenden Bereitstellungsgruppen (First, Fast und Broad) bereitgestellt. Um die Bereitstellung anzuhalten, führen Sie ein weiteres Ticket aus, in dem Operations zum Anhalten aufgefordert wird.

## <a name="autopilot-profile-settings"></a>Autopilot-Profileinstellungen

Microsoft Managed Desktop verwendet diese Einstellungen im Autopilot-Profil, das für die Geräte Ihrer Benutzer verwendet wird:


|Setting  |Wert  |
|---------|---------|
|Bereitstellungsmodus |  Benutzergesteuert       |
|Beitreten zu Azure AD als     |  Azure AD beigetreten       |
|Sprache (Region)     | Benutzerauswahl        |
|Automatisches Konfigurieren der Tastatur     | Nein        |
|Microsoft Software Lizenzbedingungen     |  Ausblenden       |
|Datenschutzeinstellungen     | Ausblenden        |
|Ausblenden von Änderungskontooptionen     | Anzeigen        |
|Benutzerkontotyp     |  Standard       |
|Zulassen von White Glove OOBE     |  Ja       |
|Anwenden der Gerätenamenvorlage     | Ja        |
|Geben Sie einen Namen ein     | MMD-%RAND:11%        |

## <a name="enrollment-status-page-settings"></a>Einstellungen der Registrierungsstatusseite

Microsoft Managed Desktop verwendet diese Einstellungen für die Registrierungsstatusseite:


|Setting  |Wert  |
|---------|---------|
|Anzeigen des Fortschritts der App- und Profilkonfiguration     | Ja        |
|Anzeigen eines Fehlers, wenn die Installation länger als die angegebene Anzahl von Minuten dauert     |  60       |
|Anzeigen einer benutzerdefinierten Nachricht beim Auftreten eines Zeitlimitfehlers     |  Ja       |
|Fehlermeldung     | Ja, Es dauert etwas länger, bis Ihr Gerät eingerichtet ist als erwartet. Klicken Sie unten, um zu beginnen, und wir beenden die Einrichtung im Hintergrund.        |
|Zulassen, dass Benutzer Protokolle zu Installationsfehlern sammeln     |  Ja       |
|Nur Seite auf Geräten anzeigen, die von der out-of-Box-Besens (Out-of-Box Experience, OOBE) bereitgestellt werden     | Ja        |
|Gerätenutzung blockieren, bis alle Apps und Profile installiert sind     |  Ja       |
|Zulassen, dass Benutzer das Gerät zurücksetzen, wenn ein Installationsfehler auftritt     |  Ja       |
|Zulassen der Verwendung des Geräts durch Benutzer bei Auftreten eines Installationsfehlers     |  Ja       |
|Gerätenutzung blockieren, bis diese erforderlichen Apps installiert sind, wenn sie dem Benutzer/Gerät zugewiesen sind     |  Moderner Arbeitsplatz – Zeitkorrektur       |



Die Registrierungsstatusseite erfolgt in drei Phasen. Weitere Informationen finden Sie unter [Registrierungsstatusseite Nachverfolgungsinformationen](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

Die Erfahrung läuft wie folgt ab:

1. Die Autopilot-Erfahrung wird gestartet, und der Benutzer gibt seine Anmeldeinformationen ein.
2. Das Gerät öffnet die Registrierungsstatusseite und durchschreitet die Phasen Gerätevorbereitung und Geräteeinrichtung. Der dritte Schritt (Kontoeinrichtung) wird *derzeit* in der Microsoft Managed Desktop-Konfiguration übersprungen, da Benutzer-ESP deaktiviert ist. Das Gerät wird neu gestartet.
3. Nach dem Neustart öffnet das Gerät die Windows-Anmeldeseite mit **"Anderer Benutzer".**
4. Die Benutzer geben ihre Anmeldeinformationen erneut ein, und der Desktop wird geöffnet.

> [!NOTE]
> Win32-Apps werden nur bei ESP bereitgestellt, wenn die Windows 10-Version 1903 oder höher ist.

![Startseite des Autopilot-Setups mit den Phasen "Gerätevorbereitung" und "Geräteeinrichtung".](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>Autopilot für die vorab bereitgestellte Bereitstellung
> [!NOTE]
> Autopilot für die vorab bereitgestellte Bereitstellung in Microsoft Managed Desktop befindet sich derzeit in der öffentlichen Vorschau.

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Zusätzliche Voraussetzungen für Autopilot für die vorab bereitgestellte Bereitstellung
- Sie müssen die Registrierungsstatusseite (Enrollment Status Page, ESP) aktiviert haben. Weitere Informationen finden Sie unter [Initial deployment](#initial-deployment).
- Das Gerät muss über eine verkabelte Netzwerkverbindung verfügen.
- Wenn Sie über Geräte verfügen, die vor August 2020 über das Microsoft Managed Desktop-Portal registriert wurden, de-register and register them again.
- Geräte müssen über ein Factoryimage verfügen, das das kumulative Update [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) oder [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) vom November 2020 enthält, wenn es installiert ist, oder muss mit dem neuesten Microsoft Managed Desktop-Image aktualisiert werden.
- Physische Geräte müssen TPM 2.0 und Gerätebescheinigungen unterstützen. Virtuelle Computer werden nicht unterstützt. Der Vorabbereitstellungsprozess verwendet Selbstbereitstellungsfunktionen von Windows Autopilot, sodass TPM 2.0 erforderlich ist. Der TPM-Nachweisprozess erfordert auch Zugriff auf eine Reihe von HTTPS-URLs, die für jeden TPM-Anbieter eindeutig sind. Weitere Informationen finden Sie im Eintrag für autopilot self-deploying mode und Autopilot pre-provisioned deployment in [Windows Autopilot networking requirements](https://docs.microsoft.com/mem/autopilot/networking-requirements#tpm).

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Abfolge von Ereignissen in Autopilot für die vorab bereitgestellte Bereitstellung
1. It Admin reimages or resets the device if needed.
2. DER IT-Administrator startet das Gerät, erreicht die out-of-box-Erfahrung und drückt die Windows-TASTE fünf mal.
3. DER IT-Administrator wählt die Windows Autopilot-Bereitstellung und dann **Weiter aus.** Auf dem Windows Autopilot-Konfigurationsbildschirm werden Informationen zum Gerät angezeigt.
5. DER IT-Administrator wählt **Provision aus,** um den Bereitstellungsprozess zu starten.
6. Das Gerät startet ESP und durch führt Die Gerätevorbereitungs- und Einrichtungsphasen durch. Während der Geräteeinrichtungsphase wird die **App-Installation x von x** angezeigt (abhängig von der genauen Konfiguration des ESP-Profils).
7. Der Kontoeinrichtungsschritt wird derzeit in der Microsoft Managed Desktop-Konfiguration übersprungen, da benutzer-ESP deaktiviert wird.
8. Das Gerät wird neu gestartet.

Nach dem Neustart zeigt das Gerät den grünen Statusbildschirm mit einer **Reseal-Schaltfläche** an.

> [!IMPORTANT]
> Bekannte Probleme: 
> - ESP wird nach dem Autopilot für die vorab bereitgestellte Bereitstellungs-Reseal-Funktion nicht erneut ausgeführt.
> - Das Gerät wird von Autopilot nicht für die vorab bereitgestellte Bereitstellung umbenannt. Das Gerät wird erst umbenannt, nachdem der Benutzerfluss von ESP durchlauft wurde.


## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Ändern zu Autopilot- und Registrierungsstatusseiteneinstellungen

Wenn das von Microsoft Managed Desktop verwendete Setup nicht genau Ihren Anforderungen entspricht, können Sie ein Supportticket über das [Admin Portal senden.](https://portal.azure.com/) Im Folgenden finden Sie einige Beispiele für die Konfiguration, die Sie möglicherweise benötigen:

### <a name="autopilot-settings-change"></a>Änderung der Autopiloteinstellungen

Möglicherweise möchten Sie eine andere Gerätenamenvorlage anfordern. Sie können jedoch nicht den Bereitstellungsmodus, die Verknüpfung mit Azure AD As, Datenschutzeinstellungen oder den Benutzerkontotyp ändern.

### <a name="enrollment-status-page-settings-change"></a>Einstellungen für registrierungsstatusseite ändern

- Eine längere Anzahl von Minuten für die Einstellung "Fehler anzeigen, wenn die Installation länger als die angegebene Anzahl von Minuten dauert".
- Die angezeigte Fehlermeldung
- Hinzufügen oder Entfernen von Anwendungen in der Einstellung "Gerätenutzung blockieren, bis diese erforderlichen Apps installiert sind, wenn sie dem Benutzer/Gerät zugewiesen sind".

## <a name="required-applications"></a>Erforderliche Anwendungen

- Sie müssen Anwendungen in den Gerätegruppen *Test,* First, Fast und Broad für moderne Workplace-Geräte verwenden. Anwendungen müssen im Kontext "System" installiert werden. Stellen Sie sicher, dass Sie die Tests mit ESP in der Testgruppe abschließen, bevor Sie sie allen Gruppen zuweisen.
- Für keine Anwendungen sollte das Gerät neu gestartet werden. Es wird empfohlen, dass Anwendungen beim Erstellen des Anwendungspakets auf "Do nothing" festgelegt werden, wenn sie einen Neustart erfordern.
- Beschränken Sie die erforderlichen Anwendungen auf die Kernanwendungen, die ein Benutzer sofort benötigt, wenn er sich beim Gerät anmeldet.
- Halten Sie die Gesamtgröße aller Anwendungen insgesamt unter 1 GB, um Timeouts während der Anwendungsinstallationsphase zu vermeiden.
- Im Idealfall sollten Apps keine Abhängigkeiten aufweisen. Wenn Sie über Apps verfügen, *die Abhängigkeiten* aufweisen müssen, stellen Sie sicher, dass Sie sie im Rahmen der ESP-Auswertung konfigurieren, testen und überprüfen.
- In der öffentlichen Vorschau von ESP können keine Anwendungen enthalten sein, die den "Benutzer"-Kontext erfordern (z. B. Teams).