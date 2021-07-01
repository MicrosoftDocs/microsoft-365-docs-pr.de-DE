---
title: Onboarding mithilfe des Microsoft Endpoint Manager
description: Erfahren Sie, wie Sie das Onboarding in Microsoft Defender für Endpunkt mithilfe von Microsoft Endpoint Manager
keywords: Onboarding, Konfiguration, bereitstellen, Bereitstellung, Endpunkt-Manager, Microsoft Defender für Endpunkt, Sammlungserstellung, Endpunkterkennungsantwort, Schutz der nächsten Generation, Verringerung der Angriffsfläche, Microsoft Endpoint Manager
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 397aa8a0e8f0523c9975d40759d39369c221222b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228975"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Onboarding mithilfe des Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für eine Onboardingmethode.

Im [Thema "Planung"](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt. In diesem Thema wird die cloudeigene Architektur behandelt.

![Abbildung der cloudeigenen Architektur ](images/cloud-native-architecture.png)
 *(Diagramm der Umgebungsarchitekturen)*

Während Defender für Endpunkt das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt. Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie in der [Onboarding-Übersicht.](onboarding.md)

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) ist eine Lösungsplattform, die mehrere Dienste vereinheitlicht. Es enthält [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) für die cloudbasierte Geräteverwaltung.

In diesem Thema werden Benutzer zu folgenden Themen geleitet:

- Schritt 1: Onboarding von Geräten in den Dienst durch Erstellen einer Gruppe in Microsoft Endpoint Manager (MEM) zum Zuweisen von Konfigurationen
- Schritt 2: Konfigurieren von Defender für Endpunkt-Funktionen mit Microsoft Endpoint Manager

Dieser Onboardingleitfaden führt Sie durch die folgenden grundlegenden Schritte, die Sie bei der Verwendung von Microsoft Endpoint Manager ausführen müssen:

- [Identifizieren von Zielgeräten oder Benutzern](#identify-target-devices-or-users)
  - Erstellen einer Azure Active Directory Gruppe (Benutzer oder Gerät)
- [Erstellen eines Konfigurationsprofils](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - In Microsoft Endpoint Manager führen wir Sie beim Erstellen einer separaten Richtlinie für jede Funktion.

## <a name="resources"></a>Ressourcen

Hier sind die Links, die Sie für den Rest des Prozesses benötigen:

- [MEM-Portal](https://aka.ms/memac)
- [Sicherheitscenter](https://securitycenter.windows.com/)
- [Intune-Sicherheitsgrundwerte](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Weitere Informationen zu Microsoft Endpoint Manager finden Sie in den folgenden Ressourcen:

- [Microsoft Endpoint Manager Seite](/mem/)
- [Blogbeitrag zur Konvergenz von Intune und ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Einführungsvideo zu MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Schritt 1: Onboarding von Geräten durch Erstellen einer Gruppe in MEM zum Zuweisen von Konfigurationen

### <a name="identify-target-devices-or-users"></a>Identifizieren von Zielgeräten oder Benutzern

In diesem Abschnitt erstellen wir eine Testgruppe zum Zuweisen Ihrer Konfigurationen.

> [!NOTE]
> Intune verwendet Azure Active Directory (Azure AD)-Gruppen zum Verwalten von Geräten und Benutzern. Als Intune-Administrator können Sie Gruppen für Ihre Organisatorischen Anforderungen einrichten.
>
> Weitere Informationen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten.](/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Erstellen einer Gruppe

1. Öffnen Sie das MEM-Portal.

2. Öffnen **Sie Gruppen > neue Gruppe.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal1](images/66f724598d9c3319cba27f79dd4617a4.png)

3. Geben Sie Details ein, und erstellen Sie eine neue Gruppe.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4. Fügen Sie Ihren Testbenutzer oder Ihr Testgerät hinzu.

5. Öffnen Sie im Bereich **"Gruppen > Alle Gruppen"** die neue Gruppe.

6. Wählen Sie  **Mitglieder > Mitglieder hinzufügen** aus.

7. Suchen Sie Den Testbenutzer oder das Testgerät, und wählen Sie es aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8. Ihre Testgruppe verfügt nun über ein Mitglied zum Testen.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Schritt 2: Erstellen von Konfigurationsrichtlinien zum Konfigurieren von Microsoft Defender für Endpunktfunktionen

Im folgenden Abschnitt erstellen Sie eine Reihe von Konfigurationsrichtlinien.

Zunächst ist eine Konfigurationsrichtlinie zum Auswählen der Gruppen von Benutzern oder Geräten, die in Defender für Endpunkt integriert werden:

- [Erkennung und Reaktion am Endpunkt](#endpoint-detection-and-response)

Anschließend erstellen Sie mehrere verschiedene Arten von Endpunktsicherheitsrichtlinien:

- [Schutz der nächsten Generation](#next-generation-protection)
- [Verringerung der Angriffsfläche](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Erkennung und Reaktion am Endpunkt

1. Öffnen Sie das MEM-Portal.

2. Navigieren Sie zu **Endpunktsicherheit > Endpunkterkennung und -antwort.** Klicken Sie auf **Profil erstellen.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal4](images/58dcd48811147feb4ddc17212b7fe840.png)

3. Wählen Sie unter **Plattform Windows 10 und höher, Profil – Endpunkterkennung und -antwort > Erstellen** aus.

4. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5. Wählen Sie nach Bedarf Einstellungen aus, und wählen Sie dann  **Weiter** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > In diesem Fall wurde dies automatisch ausgefüllt, da Defender für Endpunkt bereits in Intune integriert wurde. Weitere Informationen zur Integration finden Sie unter [Aktivieren von Microsoft Defender für Endpunkt in Intune.](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)
    >
    > Die folgende Abbildung ist ein Beispiel dafür, was Sie sehen werden, wenn Microsoft Defender für Endpunkt NICHT in Intune integriert ist:
    >
    > ![Abbildung von Microsoft Endpoint Manager Portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6. Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7. Fügen Sie eine Testgruppe hinzu, indem Sie auf "Gruppen auswählen" klicken, um ihre Gruppe **einzuschließen** und auszuwählen, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8. Überprüfen und akzeptieren Sie, und wählen Sie dann  **Erstellen** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9. Sie können die abgeschlossene Richtlinie anzeigen.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Schutzlösungen der nächsten Generation

1. Öffnen Sie das MEM-Portal.

2. Navigieren Sie zu **Endpunktsicherheit > Antivirus > Richtlinie erstellen.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3. Plattform auswählen **– Windows 10 und höher – Windows und Profil – Microsoft Defender Antivirus > Erstellen**.

4. Geben Sie Den Namen und die Beschreibung ein, und wählen Sie dann  **Weiter** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5. Legen Sie auf der **Seite "Konfigurationseinstellungen"** die Konfigurationen fest, die Sie für Microsoft Defender Antivirus (CloudSchutz, Ausschlüsse, Real-Time Schutz und Wartung) benötigen.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6. Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7. Wählen Sie Die einzuschließenden Gruppen aus, weisen Sie sie Ihrer Testgruppe zu, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal16](images/48318a51adee06bff3908e8ad4944dc9.png)

8. Überprüfen und erstellen Sie, und wählen Sie dann  **"Erstellen"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal17](images/dfdadab79112d61bd3693d957084b0ec.png)

9. Die von Ihnen erstellte Konfigurationsrichtlinie wird angezeigt.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Regeln zur Verringerung der Angriffsfläche

1. Öffnen Sie das MEM-Portal.

2. Navigieren Sie zu **Endpunktsicherheit > Attack Surface Reduction.**

3. Wählen Sie  **"Richtlinie erstellen"** aus.

4. Select **Platform – Windows 10 and later – Profile – Attack Surface Reduction rules > Create**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6. Auf der **Seite "Konfigurationseinstellungen":** Legen Sie die Konfigurationen fest, die Sie für Attack Surface Reduction-Regeln benötigen, und wählen Sie dann  **"Weiter"** aus.

    > [!NOTE]
    > Wir werden alle Attack Surface Reduction-Regeln für die Überwachung konfigurieren.
    >
    > Weitere Informationen finden Sie unter [Attack Surface Reduction-Regeln.](attack-surface-reduction.md)

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal21](images/dd0c00efe615a64a4a368f54257777d0.png)

7. Fügen Sie bereichsbezogene Tags nach Bedarf hinzu, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. Wählen Sie Gruppen aus, die der Testgruppe zugeordnet werden sollen, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Überprüfen Sie die Details, und  **wählen** Sie dann erstellen aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Zeigen Sie die Richtlinie an.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Webschutz

1. Öffnen Sie das MEM-Portal.

2. Navigieren Sie zu **Endpunktsicherheit > Attack Surface Reduction.**

3. Wählen Sie  **"Richtlinie erstellen"** aus.

4. Wählen Sie **Windows 10 und höher – Webschutz > Erstellen** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6. Auf der **Seite "Konfigurationseinstellungen":** Legen Sie die Konfigurationen fest, die Sie für Webschutz benötigen, und wählen Sie dann  **"Weiter"** aus.

    > [!NOTE]
    > Wir konfigurieren Webschutz so, dass er blockiert wird.
    >
    > Weitere Informationen finden Sie unter [Webschutz.](web-protection-overview.md)

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7. Fügen Sie **> Nächsten nach Bedarf Bereichstags** hinzu.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. Wählen Sie **"Zu Testgruppe zuweisen" > "Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal30](images/45cefc8e4e474321b4d47b4626346597.png)

9. Wählen Sie **"Überprüfen" und "Erstellen > Erstellen"** aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Zeigen Sie die Richtlinie an.

    > [!div class="mx-imgBorder"]
    > ![Abbildung von Microsoft Endpoint Manager Portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Überprüfen von Konfigurationseinstellungen

### <a name="confirm-policies-have-been-applied"></a>Bestätigen, dass Richtlinien angewendet wurden

Nachdem die Konfigurationsrichtlinie zugewiesen wurde, dauert es einige Zeit, bis sie angewendet wurde.

Informationen zum Timing finden Sie unter [Intune-Konfigurationsinformationen.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Um zu bestätigen, dass die Konfigurationsrichtlinie auf Ihr Testgerät angewendet wurde, führen Sie den folgenden Prozess für jede Konfigurationsrichtlinie aus.

1. Öffnen Sie das MEM-Portal, und navigieren Sie zur entsprechenden Richtlinie, wie in den obigen Schritten gezeigt. Das folgende Beispiel zeigt die Schutzeinstellungen der nächsten Generation.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Endpoint Manager Portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2. Wählen Sie die **Konfigurationsrichtlinie** aus, um den Richtlinienstatus anzuzeigen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Endpoint Manager Portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3. Wählen Sie  **"Gerätestatus"** aus, um den Status anzuzeigen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Endpoint Manager Portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4. Wählen Sie  **"Benutzerstatus"** aus, um den Status anzuzeigen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Endpoint Manager Portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5. Wählen Sie  **"Status pro Einstellung"** aus, um den Status anzuzeigen.

    > [!TIP]
    > Diese Ansicht ist sehr nützlich, um Einstellungen zu identifizieren, die mit einer anderen Richtlinie in Konflikt stehen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Endpoint Manager Portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Erkennung und Reaktion am Endpunkt

1. Vor dem Anwenden der Konfiguration sollte der Defender für Endpoint Protection-Dienst nicht gestartet werden.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Dienstbereichs1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2. Nachdem die Konfiguration angewendet wurde, sollte der Defender für Endpoint Protection-Dienst gestartet werden.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Dienstbereichs2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3. Nachdem die Dienste auf dem Gerät ausgeführt wurden, wird das Gerät im Microsoft Defender Security Center angezeigt.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Schutzlösungen der nächsten Generation

1. Bevor Sie die Richtlinie auf ein Testgerät anwenden, sollten Sie in der Lage sein, die Einstellungen wie unten dargestellt manuell zu verwalten.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Einstellungsseite1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2. Nachdem die Richtlinie angewendet wurde, sollten Sie die Einstellungen nicht manuell verwalten können.

    > [!NOTE]
    > In der folgenden Abbildung wird das Aktivieren des über die **Cloud bereitgestellten Schutzes** und das Aktivieren des **Echtzeitschutzes** als verwaltet angezeigt.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Einstellungsseite2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Regeln zur Verringerung der Angriffsfläche

1. Bevor Sie die Richtlinie auf ein Testgerät anwenden, stiften Sie ein PowerShell-Fenster, und geben Sie `Get-MpPreference` ein.

2. Dies sollte mit den folgenden Zeilen ohne Inhalt antworten:

    > AttackSurfaceReductionOnlyExclusions:
    >
    > AttackSurfaceReductionRules_Actions:
    >
    > AttackSurfaceReductionRules_Ids:

    ![Abbildung der Befehlszeile1](images/cb0260d4b2636814e37eee427211fe71.png)

3. Öffnen Sie nach dem Anwenden der Richtlinie auf einem Testgerät ein PowerShell-Windows und geben Sie `Get-MpPreference` .

4. Dies sollte mit den folgenden Zeilen mit Inhalt wie unten dargestellt antworten:

    ![Abbildung der Befehlszeile2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Webschutz

1. Öffnen Sie auf dem Testgerät eine PowerShell-Windows und geben Sie `(Get-MpPreference).EnableNetworkProtection` .

2. Dies sollte mit einer 0 wie unten dargestellt antworten.

    ![Abbildung der Befehlszeile3](images/196a8e194ac99d84221f405d0f684f8c.png)

3. Öffnen Sie nach dem Anwenden der Richtlinie eine PowerShell-Windows und geben Sie `(Get-MpPreference).EnableNetworkProtection` .

4. Dies sollte mit einer 1 antworten, wie unten dargestellt.

    ![Abbildung der Befehlszeile4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
