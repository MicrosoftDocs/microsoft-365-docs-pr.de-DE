---
title: App-basierte Bereitstellung für Microsoft Defender ATP für iOS
ms.reviewer: ''
description: Beschreibt die Bereitstellung von Microsoft Defender ATP für iOS mithilfe einer App
keywords: microsoft, defender, atp, ios, app, installation, deploy, deinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c7f60df38ce9f34fecae975be40206d7270b0863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062535"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a>Bereitstellen von Microsoft Defender for Endpoint für iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Thema wird die Bereitstellung von Defender for Endpoint für iOS auf registrierten Geräten des Intune-Unternehmensportals beschrieben. Weitere Informationen zur Registrierung von Intune-Geräten finden Sie unter [Registrieren von iOS-/iPadOS-Geräten in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).

## <a name="before-you-begin"></a>Vorbereitung

- Stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center haben.](https://go.microsoft.com/fwlink/?linkid=2109431)

- Stellen Sie sicher, dass die iOS-Registrierung für Ihre Benutzer erfolgt. Benutzern muss eine Defender for Endpoint-Lizenz zugewiesen sein, um Defender for Endpoint für iOS verwenden zu können. Anweisungen zum [Zuweisen von](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) Lizenzen finden Sie unter Zuweisen von Lizenzen zu Benutzern.

> [!NOTE]
> Microsoft Defender ATP (Microsoft Defender for Endpoint) für iOS ist jetzt im [Apple App Store verfügbar.](https://aka.ms/mdatpiosappstore)

## <a name="deployment-steps"></a>Bereitstellungsschritte

Bereitstellen von Defender for Endpoint für iOS über das Intune-Unternehmensportal.

### <a name="add-ios-store-app"></a>Hinzufügen einer iOS-Store-App

1. Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Apps**  ->  **iOS/iPadOS**  ->    ->  **iOS Store-App** hinzufügen, und klicken Sie auf **Auswählen**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)

1. Klicken Sie auf der Seite App hinzufügen auf **Den App Store durchsuchen,** und geben Sie **Microsoft Defender ATP** in die Suchleiste ein. Klicken Sie im Abschnitt Suchergebnisse auf *Microsoft Defender ATP,* und klicken Sie auf **Auswählen**.

1. Wählen **Sie iOS 11.0 als** Mindestbetriebssystem aus. Überprüfen Sie die restlichen Informationen zur App, und klicken Sie auf **Weiter**.

1. Wechseln Sie *im Abschnitt Zuweisungen* zum Abschnitt **Erforderlich,** und wählen Sie **Gruppe hinzufügen aus.** Sie können dann die Benutzergruppen auswählen, für die Sie Defender for Endpoint für iOS-App verwenden möchten. Klicken **Sie auf Auswählen** und dann auf **Weiter**.

    > [!NOTE]
    > Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)

1. Überprüfen Sie *im Abschnitt Überprüfen +* Erstellen, ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann Erstellen **aus.** In wenigen Momenten sollte die Defender for Endpoint-App erfolgreich erstellt werden, und in der oberen rechten Ecke der Seite sollte eine Benachrichtigung angezeigt werden.

1. Wählen Sie auf der angezeigten App-Informationsseite  im Abschnitt **Monitor** die Option Geräteinstallationsstatus aus, um sicherzustellen, dass die Geräteinstallation erfolgreich abgeschlossen wurde.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)

## <a name="complete-onboarding-and-check-status"></a>Vollständiger Onboarding- und Überprüfungsstatus

1. Sobald Defender for Endpoint für iOS auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.

    ![Ein Screenshot eines automatisch generierten Smartphones Beschreibung](images/41627a709700c324849bf7e13510c516.png)

2. Tippen Sie auf das Symbol der Defender for Endpoint-App, und befolgen Sie die Anweisungen auf dem Bildschirm, um die Onboardingschritte zu ausführen. Die Details umfassen die Endbenutzerakzeptanz der iOS-Berechtigungen, die von Defender for Endpoint für iOS erforderlich sind.

3. Nach dem erfolgreichen Onboarding wird das Gerät in der Liste Geräte im Microsoft Defender Security Center angezeigt.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines automatisch generierten Mobiltelefons Beschreibung](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Konfigurieren von Microsoft Defender for Endpoint für den überwachten Modus

Die Microsoft Defender for Endpoint für iOS-App verfügt über spezielle Funktionen für überwachte iOS/iPadOS-Geräte, da die Plattform auf diesen Gerätetypen mehr Verwaltungsfunktionen bietet. Um diese Funktionen nutzen zu können, muss die Defender for Endpoint-App wissen, ob sich ein Gerät im überwachten Modus befindet.

### <a name="configure-supervised-mode-via-intune"></a>Konfigurieren des überwachten Modus über Intune

Mit Intune können Sie die Defender für iOS-App über eine App-Konfigurationsrichtlinie konfigurieren.

   > [!NOTE]
   > Diese App-Konfigurationsrichtlinie für überwachte Geräte gilt nur für verwaltete Geräte und sollte als bewährte Methode für alle verwalteten iOS-Geräte gelten.

1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center an,](https://go.microsoft.com/fwlink/?linkid=2109431) und wechseln Sie zu **Apps**  >  **App-Konfigurationsrichtlinien**  >  **Hinzufügen**. Klicken Sie auf **Verwaltete Geräte**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)

1. Geben Sie *auf der Seite App-Konfigurationsrichtlinie erstellen* die folgenden Informationen an:
    - Policy Name
    - Plattform: Auswählen von iOS/iPadOS
    - Ziel-App: Wählen **Sie Microsoft Defender ATP** aus der Liste aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)

1. Wählen Sie im nächsten Bildschirm **Konfigurations-Designer als** Format verwenden aus. Geben Sie die folgende Eigenschaft an:
    - Konfigurationsschlüssel: issupervised
    - Werttyp: Zeichenfolge
    - Konfigurationswert: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)

1. Klicken **Sie auf Weiter,** um die **Seite Bereichstags zu** öffnen. Bereichstags sind optional. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

1. Wählen Sie **auf** der Seite Zuordnungen die Gruppen aus, die dieses Profil erhalten. Für dieses Szenario ist es bewährte Methode, alle **Geräte als Ziel zu verwenden.** Weitere Informationen zum Zuweisen von Profilen finden Sie unter [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

   Bei der Bereitstellung in Benutzergruppen muss sich ein Benutzer bei einem Gerät anmelden, bevor die Richtlinie angewendet wird.

   Klicken Sie auf **Weiter**.

1. Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.** Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.

1. Als Nächstes können Sie für erweiterte Antiphishingfunktionen ein benutzerdefiniertes Profil auf den überwachten iOS-Geräten bereitstellen. Führen Sie die folgenden Schritte aus:
    - Laden Sie das Konfigurationsprofil von herunter. [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Navigieren Sie **zu**  ->  **Geräte iOS/iPadOS**  ->  **Konfigurationsprofile**  ->  **Profil erstellen**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)

    - Geben Sie einen Namen des Profils an. Wenn Sie aufgefordert werden, eine Konfigurationsprofildatei zu importieren, wählen Sie die oben heruntergeladene aus.
    - Wählen Sie **im Abschnitt Zuordnung** die Gerätegruppe aus, auf die Sie dieses Profil anwenden möchten. Dies sollte als bewährte Methode auf alle verwalteten iOS-Geräte angewendet werden. Klicken Sie auf **Weiter**.
    - Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.** Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren von Defender for Endpoint für iOS-Features](ios-configure-features.md)
