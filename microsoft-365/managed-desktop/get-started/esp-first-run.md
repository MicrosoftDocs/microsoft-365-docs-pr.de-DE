---
title: Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite
description: Bereitstellen der ESP-Oberfläche, der verwendeten Einstellungen und Konfigurationsänderungen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b65ad2a6ac1a9b9abe06cc108a980be21152bc86
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844958"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Eindruck beim ersten Ausführen mit Autopilot und der Registrierungsstatusseite

Microsoft Managed Desktop verwendet sowohl [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) als auch die [Registrierungsstatusseite (Enrollment Status Page, ESP)](/windows/deployment/windows-autopilot/enrollment-status) von Microsoft Intune, um Ihren Benutzern die bestmögliche Erste Ausführung zu ermöglichen.

Die Registrierungsstatusseite befindet sich derzeit in der öffentlichen Vorschau.

## <a name="initial-deployment"></a>Erstbereitstellung

Um die ESP-Erfahrung bereitzustellen, müssen Sie Geräte im Microsoft Managed Desktop-Dienst registrieren. Weitere Informationen zur Registrierung finden Sie unter ["Registrieren neuer Geräte selbst"](../get-started/register-devices-self.md) oder ["Schritte für Partner" zum Registrieren](../get-started/register-devices-partner.md)von Geräten.

Nachdem Ihre Geräte beim Dienst registriert wurden, können Sie ESP für Ihre Microsoft Managed Desktop-Geräte aktivieren, indem Sie über das [Verwaltungsportal](https://portal.azure.com/)ein Supportticket einreichen. Wir stellen die ESP-Konfiguration zunächst für die Testgruppe bereit, wenn Sie das Ticket einreichen. Es wird alle 24 Stunden für die anderen nachfolgenden Bereitstellungsgruppen (First, Fast und Broad) bereitgestellt. Wenn Sie die Bereitstellung anhalten möchten, geben Sie ein weiteres Ticket ein, in dem Operations zur Aufbewahrung aufgefordert wird.

## <a name="autopilot-profile-settings"></a>Autopilot-Profileinstellungen

Microsoft Managed Desktop verwendet diese Einstellungen im Autopilot-Profil, das für die Geräte Ihrer Benutzer verwendet wird:

<br>

****

|Einstellung|Wert|
|---|---|
|Bereitstellungsmodus|Benutzergesteuert|
|Beitreten zu Azure AD als|In Azure AD eingebunden|
|Sprache (Region)|Benutzerauswahl|
|Automatisches Konfigurieren der Tastatur|Nein|
|Microsoft-Softwarelizenzbedingungen|Ausblenden|
|Datenschutzeinstellungen|Ausblenden|
|Ausblenden von Änderungskontooptionen|Anzeigen|
|Benutzerkontotyp|Standard|
|White Glove OOBE zulassen|Ja|
|Anwenden der Gerätenamenvorlage|Ja|
|Geben Sie einen Namen ein.|MMD-%RAND:11 %|
|

## <a name="enrollment-status-page-settings"></a>Einstellungen der Registrierungsstatusseite

Microsoft Managed Desktop verwendet diese Einstellungen für die Registrierungsstatusseite:

<br>

****

|Einstellung|Wert|
|---|---|
|Anzeigen des Fortschritts der App- und Profilkonfiguration|Ja|
|Fehler anzeigen, wenn die Installation länger als die angegebene Anzahl von Minuten dauert|60|
|Anzeigen einer benutzerdefinierten Meldung, wenn ein Zeitlimitfehler auftritt|Ja|
|Fehlermeldung|Ja, das Einrichten Ihres Geräts dauert etwas länger als erwartet. Klicken Sie unten, um loszulegen, und wir werden die Einrichtung im Hintergrund abschließen.|
|Zulassen, dass Benutzer Protokolle zu Installationsfehlern sammeln|Ja|
|Seite nur für Geräte anzeigen, die über die Windows-Willkommensseite bereitgestellt werden|Ja|
|Geräteverwendung blockieren, bis alle Apps und Profile installiert sind|Ja|
|Zulassen, dass Benutzer das Gerät zurücksetzen, wenn ein Installationsfehler auftritt|Ja|
|Benutzern die Verwendung des Geräts gestatten, wenn ein Installationsfehler auftritt|Ja|
|Geräteverwendung blockieren, bis diese erforderlichen Apps installiert werden, wenn sie dem Benutzer/Gerät zugewiesen sind|Moderner Arbeitsplatz – Zeitkorrektur|
|

Die Registrierungsstatusseite erfolgt in drei Phasen. Weitere Informationen finden Sie unter Informationen zur Nachverfolgung der [Registrierungsstatusseite.](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

Die Erfahrung wird wie folgt fortgesetzt:

1. Die Autopilot-Umgebung wird gestartet, und der Benutzer gibt seine Anmeldeinformationen ein.
2. Das Gerät öffnet die Registrierungsstatusseite und durchläuft die Phasen "Gerätevorbereitung" und "Geräteeinrichtung". Der dritte Schritt (Kontoeinrichtung) wird derzeit in der Microsoft Managed Desktop Konfiguration *übersprungen,* da die Benutzer-ESP deaktiviert ist. Das Gerät wird neu gestartet.
3. Nach dem Neustart öffnet das Gerät die Windows Anmeldeseite mit **einem anderen Benutzer.**
4. Die Benutzer geben ihre Anmeldeinformationen erneut ein, und der Desktop wird geöffnet.

> [!NOTE]
> Win32-Apps werden nur während der ESP bereitgestellt, wenn die Windows 10 Version 1903 oder höher ist.

![Startseite des Autopilot-Setups mit den Phasen "Gerätevorbereitung" und "Geräteeinrichtung".](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>Autopilot für vorab bereitgestellte Bereitstellung

> [!NOTE]
> Autopilot für die vorab bereitgestellte Bereitstellung in Microsoft Managed Desktop befindet sich derzeit in der öffentlichen Vorschau.

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Zusätzliche Voraussetzungen für Autopilot für die vorab bereitgestellte Bereitstellung

- Sie müssen die Registrierungsstatusseite (ESP) aktiviert haben. Weitere Informationen finden Sie unter ["Anfängliche Bereitstellung".](#initial-deployment)
- Das Gerät muss über eine kabelgebundene Netzwerkverbindung verfügen.
- Wenn Sie Geräte haben, die vor August 2020 über das Microsoft Managed Desktop-Portal registriert wurden, deaktivieren Sie die Registrierung, und registrieren Sie sie erneut.
- Geräte müssen über ein Factoryimage verfügen, das das kumulative Update [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) vom November [2020 oder 20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) enthält, sofern installiert oder mit dem neuesten Microsoft Managed Desktop Image neu gestartet werden muss.
- Physische Geräte müssen TPM 2.0 und den Gerätenachweis unterstützen. Virtuelle Computer werden nicht unterstützt. Der Vorabbereitstellungsprozess verwendet Windows Autopilot Self-Deploying-Funktionen, sodass TPM 2.0 erforderlich ist. Der TPM-Nachweisprozess erfordert auch Zugriff auf eine Reihe von HTTPS-URLs, die für jeden TPM-Anbieter eindeutig sind. Weitere Informationen finden Sie im Eintrag für den Autopilot Self-Deploying-Modus und die vorab bereitgestellte Autopilot-Bereitstellung in [Windows Autopilot-Netzwerkanforderungen.](/mem/autopilot/networking-requirements#tpm)

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Abfolge von Ereignissen in Autopilot für die vorab bereitgestellte Bereitstellung

1. Der IT-Administrator stellt das Gerät bei Bedarf neu auf oder setzt es zurück.
2. DER IT-Administrator startet das Gerät, erreicht die Out-of-Box-Umgebung und drückt fünf mal die Windows Taste.
3. It Admin selects Windows Autopilot Provisioning and then selects **Continue**. Auf dem Windows Autopilot-Konfigurationsbildschirm werden Informationen zum Gerät angezeigt.
4. DER IT-Administrator wählt **"Bereitstellung"** aus, um den Bereitstellungsprozess zu starten.
5. Das Gerät startet ESP und durchläuft die Phasen der Gerätevorbereitung und -einrichtung. Während der Geräteeinrichtungsphase wird **die App-Installation x von x** angezeigt (abhängig von der genauen Konfiguration des ESP-Profils).
6. Der Kontoeinrichtungsschritt wird derzeit in der Microsoft Managed Desktop Konfiguration übersprungen, da wir die Benutzer-ESP deaktivieren.
7. Das Gerät wird neu gestartet.

Nach dem Neustart zeigt das Gerät den grünen Statusbildschirm mit einer **Schaltfläche "Erneut** senden" an.

> [!IMPORTANT]
> Bekannte Probleme:
>
> - ESP wird nach dem Autopilot für die vorab bereitgestellte Bereitstellungsfunktion nicht erneut ausgeführt.
> - Das Gerät wird von Autopilot nicht für die vorab bereitgestellte Bereitstellung umbenannt. Das Gerät wird nur umbenannt, nachdem der ESP-Benutzerablauf durchlaufen wurde.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Ändern der Einstellungen der Autopilot- und Registrierungsstatusseite

Wenn das von Microsoft Managed Desktop verwendete Setup nicht genau Ihren Anforderungen entspricht, können Sie ein Supportticket über das [Verwaltungsportal](https://portal.azure.com/)einreichen. Hier sind einige Beispiele für die Arten von Konfigurationen, die Sie möglicherweise benötigen:

### <a name="autopilot-settings-change"></a>Ändern der Autopilot-Einstellungen

Möglicherweise möchten Sie eine andere Gerätenamenvorlage anfordern. Sie können jedoch den Bereitstellungsmodus, den Beitritt zu Azure AD As, den Datenschutz Einstellungen oder den Benutzerkontotyp nicht ändern.

### <a name="enrollment-status-page-settings-change"></a>Einstellungen der Registrierungsstatusseite ändern sich

- Eine längere Anzahl von Minuten für die Einstellung "Fehler anzeigen, wenn die Installation länger als die angegebene Anzahl von Minuten dauert".
- Die angezeigte Fehlermeldung
- Hinzufügen oder Entfernen von Anwendungen in der Einstellung "Geräteverwendung blockieren, bis diese erforderlichen Apps installiert werden, wenn sie dem Benutzer/Gerät zugewiesen sind"

## <a name="required-applications"></a>Erforderliche Anwendungen

- Sie müssen auf Anwendungen in den *Modern Workplace-Gerätegruppen* "Test", "First", "Fast" und "Broad" abzielen. Anwendungen müssen im Kontext "System" installiert werden. Stellen Sie sicher, dass Sie die Tests mit ESP in der Testgruppe abschließen, bevor Sie sie allen Gruppen zuweisen.
- Für keine Anwendungen sollte das Gerät neu gestartet werden müssen. Es wird empfohlen, dass Anwendungen beim Erstellen des Anwendungspakets auf "Nichts ausführen" festgelegt werden, wenn sie einen Neustart erfordern.
- Beschränken Sie erforderliche Anwendungen auf die Kernanwendungen, die ein Benutzer sofort benötigt, wenn er sich beim Gerät anmeldet.
- Behalten Sie die Gesamtgröße aller Anwendungen zusammen unter 1 GB, um Timeouts während der Anwendungsinstallationsphase zu vermeiden.
- Im Idealfall sollten Apps keine Abhängigkeiten aufweisen. Wenn Sie Apps haben, die Abhängigkeiten aufweisen *müssen,* stellen Sie sicher, dass Sie sie im Rahmen der ESP-Auswertung konfigurieren, testen und überprüfen.
- In die öffentliche Vorschau von ESP können keine Anwendungen einbezogen werden, die den Kontext "Benutzer" erfordern (z. B. Teams).
