---
title: App-basierte Bereitstellung für Microsoft Defender für Endpunkt unter iOS
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS mithilfe einer App bereitgestellt wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, App, Installation, bereitstellen, Deinstallation, Intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842290"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>Bereitstellen von Microsoft Defender für Endpunkt unter iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In diesem Thema wird die Bereitstellung von Defender für Endpunkt unter iOS auf Intune-Unternehmensportal registrierten Geräten beschrieben. Weitere Informationen zur Intune-Geräteregistrierung finden Sie unter [Registrieren von iOS/iPadOS-Geräten in Intune.](/mem/intune/enrollment/ios-enroll)

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Stellen Sie sicher, dass Sie Zugriff auf [das Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)haben.

- Stellen Sie sicher, dass die iOS-Registrierung für Ihre Benutzer erfolgt. Benutzern muss eine Defender für Endpunkt-Lizenz zugewiesen sein, um Defender für Endpunkt unter iOS verwenden zu können. Anweisungen zum Zuweisen von Lizenzen finden Sie unter ["Zuweisen von Lizenzen an Benutzer".](/azure/active-directory/users-groups-roles/licensing-groups-assign)

> [!NOTE]
> Microsoft Defender für Endpunkt unter iOS ist in der [Apple-App Store](https://aka.ms/mdatpiosappstore)verfügbar.

## <a name="deployment-steps"></a>Bereitstellungsschritte

Bereitstellen von Defender für Endpunkt unter iOS über Intune-Unternehmensportal.

### <a name="add-ios-store-app"></a>Hinzufügen einer iOS Store-App

1. Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Apps**  ->  **iOS/iPadOS**  ->    ->  **Hinzufügen der iOS Store-App,** und klicken Sie auf **"Auswählen".**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)

1. Klicken Sie auf der Seite "App hinzufügen" auf **"App Store durchsuchen",** und geben Sie **Microsoft Defender Endpoint** in der Suchleiste ein. Klicken Sie im Abschnitt mit den Suchergebnissen auf *Microsoft Defender Endpoint,* und klicken Sie auf **"Auswählen".**

1. Wählen Sie **iOS 11.0** als Mindestbetriebssystem aus. Überprüfen Sie die restlichen Informationen zur App, und klicken Sie auf **"Weiter".**

1. Wechseln Sie im Abschnitt *Aufgaben* zum Abschnitt **Erforderlich ,** und wählen Sie **Gruppe hinzufügen** aus. Sie können dann die Benutzergruppe(n) auswählen, für die Sie Defender für Endpunkt in der iOS-App als Ziel verwenden möchten. Klicken Sie auf **"Auswählen"** und dann auf **"Weiter".**

    > [!NOTE]
    > Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)

1. Überprüfen Sie im Abschnitt *"Überprüfen + Erstellen",* ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus. In wenigen Momenten sollte die Defender für Endpunkt-App erfolgreich erstellt werden, und in der oberen rechten Ecke der Seite sollte eine Benachrichtigung angezeigt werden.

1. Wählen Sie auf der angezeigten Seite "App-Informationen" im Abschnitt **"Monitor"** den **Geräteinstallationsstatus** aus, um zu überprüfen, ob die Geräteinstallation erfolgreich abgeschlossen wurde.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>Automatisches Onboarding des VPN-Profils (vereinfachtes Onboarding)

Administratoren können die automatische Einrichtung des VPN-Profils konfigurieren. Dadurch wird das Defender für Endpunkt-VPN-Profil automatisch eingerichtet, ohne dass der Benutzer dies während des Onboardings tun muss. Beachten Sie, dass VPN verwendet wird, um das Webschutzfeature bereitzustellen. Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.

1. Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu   ->  **"Gerätekonfigurationsprofile**  ->  **erstellen"**.
1. Wählen Sie **Plattform** als **iOS/iPadOS** und **Profiltyp** als **VPN** aus. Klicken Sie auf **Erstellen**.
1. Geben Sie einen Namen für das Profil ein, und klicken Sie auf **"Weiter".**
1. Wählen Sie **"Benutzerdefiniertes VPN** für Verbindungstyp" aus, und geben Sie im Abschnitt **"Basis-VPN"** Folgendes ein:
    - Verbindungsname = Microsoft Defender für Endpunkt
    - VPN-Serveradresse = 127.0.0.1
    - Auth-Methode = "Benutzername und Kennwort"
    - Split Tunneling = Deaktivieren
    - VPN-ID = com.microsoft.scmx
    - Geben Sie in den Schlüssel-Wert-Paaren das **Schlüssel-AutoOnboard** ein, und legen Sie den Wert auf **"True"** fest.
    - Typ des automatischen VPN = On-Demand-VPN
    - Klicken Sie auf **"Regeln** bei **Bedarf hinzufügen",** und wählen **Sie "Ich möchte folgendermaßen vorgehen = VPN einrichten"** aus, **ich möchte dies auf = alle Domänen beschränken.**

    ![Screenshot der VPN-Profilkonfiguration](images/ios-deploy-8.png)

1. Klicken Sie auf "Weiter", und weisen Sie das Profil den Zielbenutzern zu.
1. Überprüfen Sie im Abschnitt *"Überprüfen + Erstellen",* ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus.

## <a name="complete-onboarding-and-check-status"></a>Abschließen des Onboardings und Überprüfen des Status

1. Sobald Defender für Endpunkt unter iOS auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.

    ![Screenshot einer automatisch generierten Smartphone-Beschreibung](images/41627a709700c324849bf7e13510c516.png)

2. Tippen Sie auf das Symbol der Defender für Endpunkt-App (MSDefender), und befolgen Sie die Anweisungen auf dem Bildschirm, um die Integrationsschritte abzuschließen. Die Details umfassen die Akzeptanz von iOS-Berechtigungen durch Endbenutzer, die von Defender für Endpunkt unter iOS benötigt werden.

3. Nach erfolgreichem Onboarding wird das Gerät in der Liste "Geräte" in Microsoft Defender Security Center angezeigt.

    > [!div class="mx-imgBorder"]
    > ![Screenshot einer automatisch generierten Mobiltelefonbeschreibung](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Konfigurieren von Microsoft Defender für Endpunkt für den überwachten Modus

Die Microsoft Defender für Endpunkt unter iOS-App verfügt aufgrund der erweiterten Verwaltungsfunktionen der Plattform auf diesen Gerätetypen über spezielle Fähigkeiten auf überwachten iOS/iPadOS-Geräten. Um diese Funktionen nutzen zu können, muss die Defender für Endpunkt-App wissen, ob sich ein Gerät im überwachten Modus befindet.

### <a name="configure-supervised-mode-via-intune"></a>Konfigurieren des überwachten Modus über Intune

Mit Intune können Sie die Defender für iOS-App über eine App-Konfigurationsrichtlinie konfigurieren.

   > [!NOTE]
   > Diese App-Konfigurationsrichtlinie für überwachte Geräte gilt nur für verwaltete Geräte und sollte als bewährte Methode für alle verwalteten iOS-Geräte vorgesehen sein.

1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) an, und wechseln Sie zu **App-Konfigurationsrichtlinien**  >    >  **hinzufügen.** Klicken Sie auf **verwaltete Geräte.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)

1. Geben Sie auf der Seite *"App-Konfigurationsrichtlinie erstellen"* die folgenden Informationen an:
    - Policy Name
    - Plattform: Auswählen von iOS/iPadOS
    - Ziel-App: Microsoft **Defender-Endpunkt** aus der Liste auswählen

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)

1. Wählen Sie im nächsten Bildschirm **Konfigurations-Designer** als Format verwenden aus. Geben Sie die folgende Eigenschaft an:
    - Konfigurationsschlüssel: issupervised
    - Werttyp: Zeichenfolge
    - Konfigurationswert: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)

1. Klicken Sie auf **"Weiter",** um die Seite **"Bereichstags"** zu öffnen. Bereichstags sind optional. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

1. Wählen Sie auf der Seite **"Aufgaben"** die Gruppen aus, die dieses Profil erhalten. Für dieses Szenario empfiehlt es sich, alle Geräte als Ziel zu **verwenden.** Weitere Informationen zum Zuweisen von Profilen finden Sie unter [Zuweisen von Benutzer- und Geräteprofilen.](/mem/intune/configuration/device-profile-assign)

   Bei der Bereitstellung in Benutzergruppen muss sich ein Benutzer bei einem Gerät anmelden, bevor die Richtlinie angewendet wird.

   Klicken Sie auf **Weiter**.

1. Wenn Sie fertig sind, wählen Sie auf der Seite **"Überprüfen + Erstellen"** die Option **"Erstellen"** aus. Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.

1. Als Nächstes können Sie für erweiterte Antiphishingfunktionen ein benutzerdefiniertes Profil auf den überwachten iOS-Geräten bereitstellen. Führen Sie die folgenden Schritte aus:
    - Laden Sie das Konfigurationsprofil von [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Navigieren Sie zu  ->  **iOS-/iPadOS-Konfigurationsprofilen**  ->  **für**  ->  **Geräte– Profil erstellen**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)

    - Geben Sie einen Namen des Profils an. Wenn Sie aufgefordert werden, eine Konfigurationsprofildatei zu importieren, wählen Sie die oben heruntergeladene aus.
    - Wählen Sie im Abschnitt **"Zuordnung"** die Gerätegruppe aus, auf die Sie dieses Profil anwenden möchten. Als bewährte Methode sollte dies auf alle verwalteten iOS-Geräte angewendet werden. Klicken Sie auf **Weiter**.
    - Wenn Sie fertig sind, wählen Sie auf der Seite **"Überprüfen + Erstellen"** die Option **"Erstellen"** aus. Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren von Defender für Endpunkt unter iOS-Features](ios-configure-features.md)
