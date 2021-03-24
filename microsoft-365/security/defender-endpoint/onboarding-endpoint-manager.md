---
title: Onboarding mit Microsoft Endpoint Manager
description: Informationen zum Onboarding in Microsoft Defender for Endpoint mithilfe von Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
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
ms.openlocfilehash: 4028fbaedd4e0b89b37a774b79ac5302d899ec3c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060996"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Onboarding mit Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für ein Onboarding. 

Im Thema [Planning](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt. In diesem Thema wird die cloudeigene Architektur behandelt. 

![Abbildung der cloudeigenen Architektur ](images/cloud-native-architecture.png)
 *Diagramm der Umgebungsarchitekturen*

Während Defender for Endpoint das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt. Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie unter [Onboarding overview](onboarding.md).


[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) ist eine Lösungsplattform, die mehrere Dienste vereint. Es umfasst [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) für die cloudbasierte Geräteverwaltung.


In diesem Thema werden Benutzer in den themen:
- Schritt 1: Onboarding von Geräten in den Dienst durch Erstellen einer Gruppe im Microsoft Endpoint Manager (MEM) zum Zuweisen von Konfigurationen für
- Schritt 2: Konfigurieren von Defender for Endpoint-Funktionen mithilfe von Microsoft Endpoint Manager

In diesem Onboardingleitfaden werden Sie durch die folgenden grundlegenden Schritte geleitet, die Sie bei der Verwendung von Microsoft Endpoint Manager ausführen müssen:

-   [Identifizieren von Zielgeräten oder Benutzern](#identify-target-devices-or-users)

    -   Erstellen einer Azure Active Directory-Gruppe (Benutzer oder Gerät)

-   [Erstellen eines Konfigurationsprofils](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   In Microsoft Endpoint Manager führen wir Sie beim Erstellen einer separaten Richtlinie für jede Funktion.





## <a name="resources"></a>Ressourcen


Hier sind die Links, die Sie für den Rest des Prozesses benötigen:

-   [MEM-Portal](https://aka.ms/memac)

-   [Security Center](https://securitycenter.windows.com/)

-   [Intune-Sicherheitsgrundwerte](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Weitere Informationen zu Microsoft Endpoint Manager finden Sie in den folgenden Ressourcen:
- [Microsoft Endpoint Manager-Seite](https://docs.microsoft.com/mem/)
- [Blogbeitrag zur Konvergenz von Intune und ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Einführungsvideo zu MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Schritt 1: Onboarding von Geräten durch Erstellen einer Gruppe in MEM zum Zuweisen von Konfigurationen für
### <a name="identify-target-devices-or-users"></a>Identifizieren von Zielgeräten oder Benutzern
In diesem Abschnitt erstellen wir eine Testgruppe zum Zuweisen Ihrer Konfigurationen.

>[!NOTE]
>Intune verwendet Azure Active Directory (Azure AD)-Gruppen zum Verwalten von Geräten und Benutzern. Als Intune-Administrator können Sie Gruppen entsprechend Ihren Organisatorischen Anforderungen einrichten.<br>
Weitere Informationen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Erstellen einer Gruppe

1.  Öffnen Sie das MEM-Portal.

2.  Öffnen **Sie Gruppen > Neue Gruppe**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Geben Sie Details ein, und erstellen Sie eine neue Gruppe.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Fügen Sie Ihren Testbenutzer oder Ihr Gerät hinzu.

5.  Öffnen Sie **im Bereich > Alle Gruppen** ihre neue Gruppe.

6.  Wählen **Sie Mitglieder > Mitglieder hinzufügen aus.**

7.  Suchen Sie Den Testbenutzer oder Ihr Gerät, und wählen Sie ihn aus.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  Ihre Testgruppe hat nun ein Mitglied zum Testen.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Schritt 2: Erstellen von Konfigurationsrichtlinien zum Konfigurieren von Microsoft Defender for Endpoint-Funktionen
Im folgenden Abschnitt erstellen Sie eine Reihe von Konfigurationsrichtlinien.

Zunächst wird eine Konfigurationsrichtlinie verwendet, um auszuwählen, welche Benutzergruppen oder Geräte in Defender for Endpoint onboarded werden:

- [Endpunkterkennung und -antwort](#endpoint-detection-and-response) 

Anschließend erstellen Sie verschiedene Arten von Endpunktsicherheitsrichtlinien:

- [Schutz der nächsten Generation](#next-generation-protection)
- [Reduzierung der Angriffsfläche](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Erkennung und Reaktion am Endpunkt

1.  Öffnen Sie das MEM-Portal.

2.  Navigieren Sie **zu Endpoint security > Endpoint detection and response**. Klicken Sie auf **Profil erstellen**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  Wählen **Sie unter Plattform windows 10 und höher Profil – Endpunkterkennung und -antwort > Erstellen aus.**

4.  Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Wählen Sie die Einstellungen nach Bedarf aus, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > In dieser Instanz wurde dies automatisch aufgefüllt, da Defender for Endpoint bereits in Intune integriert wurde. Weitere Informationen zur Integration finden Sie unter [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).
    > 
    > Die folgende Abbildung ist ein Beispiel dafür, was Sie sehen werden, wenn Microsoft Defender for Endpoint NICHT in Intune integriert ist:
    >
    > ![Abbildung des Microsoft Endpoint Manager-Portals7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Fügen Sie test group hinzu, indem Sie **auf** Gruppen auswählen klicken, um Ihre Gruppe hinzuzufügen und auszuwählen, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Überprüfen und akzeptieren Sie, und wählen Sie **dann Erstellen aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  Sie können ihre abgeschlossene Richtlinie anzeigen.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Schutz der nächsten Generation

1.  Öffnen Sie das MEM-Portal.

2.  Navigieren Sie **zu Endpoint security > Antivirus > Create Policy**.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Wählen **Sie Plattform – Windows 10 und höher – Windows und Profil – Microsoft Defender Antivirus > Erstellen aus.**

4.  Geben Sie Namen und Beschreibung ein, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  Auf der **Seite Konfigurationseinstellungen:** Legen Sie die für Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection und Remediation) benötigten Konfigurationen festgelegt.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Wählen Sie Gruppen aus, die sie enthalten soll, weisen Sie ihrer Testgruppe zu, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Überprüfen und erstellen, und wählen Sie **dann Erstellen aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  Sie sehen die von Ihnen erstellte Konfigurationsrichtlinie.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Regeln zur Reduzierung der Angriffsfläche

1.  Öffnen Sie das MEM-Portal.

2.  Navigieren Sie **zu Endpoint security > Attack surface reduction**.

3.  Wählen **Sie Richtlinie erstellen aus.**

4.  Wählen **Sie Plattform – Windows 10 und höher – Profil – Attack surface reduction rules > Create aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  Wählen Sie **auf der Seite Konfigurationseinstellungen**: Festlegen der Konfigurationen, die Sie für Attack surface reduction rules benötigen, dann **Weiter aus.**

    > [!NOTE]
    > Wir konfigurieren alle Attack surface reduction-Regeln auf Audit.
    > 
    > Weitere Informationen finden Sie unter [Attack surface reduction rules](attack-surface-reduction.md).

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Fügen Sie Bereichstags nach Bedarf hinzu, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Wählen Sie Gruppen aus, die einer Testgruppe zugewiesen werden, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Überprüfen Sie die Details, und wählen Sie **dann Erstellen aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Anzeigen der Richtlinie.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Web Protection

1.  Öffnen Sie das MEM-Portal.

2.  Navigieren Sie **zu Endpoint security > Attack surface reduction**.

3.  Wählen **Sie Richtlinie erstellen aus.**

4.  Wählen **Sie Windows 10 und höher – Webschutz > Erstellen aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  Wählen Sie **auf der Seite Konfigurationseinstellungen**: Legen Sie die für Web Protection benötigten Konfigurationen ein, und wählen Sie **dann Weiter aus.**

    > [!NOTE]
    > Wir konfigurieren Web Protection so, dass es blockiert wird.
    > 
    > Weitere Informationen finden Sie unter [Web Protection](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Fügen **Sie Bereichstags wie erforderlich > Next hinzu.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Wählen **Sie Zuweisen zu Testgruppen > Weiter aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Wählen **Sie Überprüfen und Erstellen > Erstellen aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Anzeigen der Richtlinie.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Microsoft Endpoint Manager-Portals32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Überprüfen von Konfigurationseinstellungen


### <a name="confirm-policies-have-been-applied"></a>Bestätigen, dass Richtlinien angewendet wurden


Nachdem die Konfigurationsrichtlinie zugewiesen wurde, dauert es einige Zeit, bis sie angewendet wurde.

Informationen zum Timing finden Sie unter [Intune-Konfigurationsinformationen](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Führen Sie den folgenden Prozess für jede Konfigurationsrichtlinie aus, um zu bestätigen, dass die Konfigurationsrichtlinie auf Ihr Testgerät angewendet wurde.

1.  Öffnen Sie das MEM-Portal, und navigieren Sie zu der relevanten Richtlinie, wie in den obigen Schritten gezeigt. Das folgende Beispiel zeigt die Schutzeinstellungen der nächsten Generation.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Microsoft Endpoint Manager-Portals33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Wählen Sie die **Konfigurationsrichtlinie aus,** um den Richtlinienstatus anzeigen zu können.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Microsoft Endpoint Manager-Portals34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Wählen  **Sie Gerätestatus aus,** um den Status zu sehen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Microsoft Endpoint Manager-Portals35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Wählen  **Sie Benutzerstatus aus,** um den Status zu sehen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Microsoft Endpoint Manager-Portals36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Wählen  **Sie Status pro Einstellung aus,** um den Status zu sehen.

    >[!TIP]
    >Diese Ansicht ist sehr nützlich, um Einstellungen zu identifizieren, die mit einer anderen Richtlinie in Konflikt stehen.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Microsoft Endpoint Manager-Portals37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Erkennung und Reaktion am Endpunkt


1.  Vor dem Anwenden der Konfiguration sollte der Defender for Endpoint Protection-Dienst nicht gestartet werden.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Dienstbereichs1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  Nachdem die Konfiguration angewendet wurde, sollte der Defender for Endpoint Protection Service gestartet werden.

    > [!div class="mx-imgBorder"]
    > [![Abbildung des Dienstbereichs2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  Nachdem die Dienste auf dem Gerät ausgeführt wurden, wird das Gerät im Microsoft Defender Security Center angezeigt.

    > [!div class="mx-imgBorder"]
    > [![Abbildung von Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Schutz der nächsten Generation

1.  Bevor Sie die Richtlinie auf ein Testgerät anwenden, sollten Sie die Einstellungen wie unten gezeigt manuell verwalten können.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Einstellung Seite1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  Nachdem die Richtlinie angewendet wurde, sollten Sie die Einstellungen nicht manuell verwalten können.

    > [!NOTE]
    > In der folgenden Abbildung **werden der in der Cloud** übermittelte Schutz und der **Echtzeitschutz** aktivieren als verwaltet angezeigt.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Einstellung Seite2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Regeln zur Reduzierung der Angriffsfläche


1.  Bevor Sie die Richtlinie auf ein Testgerät anwenden, geben Sie ein PowerShell-Fenster ein, und geben Sie ein `Get-MpPreference` .

2.  Dies sollte mit den folgenden Zeilen ohne Inhalt antworten:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Abbildung der Befehlszeile1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  Öffnen Sie nach dem Anwenden der Richtlinie auf ein Testgerät ein PowerShell-Windows, und geben Sie `Get-MpPreference` ein.

4.  Dies sollte mit den folgenden Zeilen mit Inhalten wie unten gezeigt reagieren:

    ![Abbildung der Befehlszeile2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Web Protection

1.  Öffnen Sie auf dem Testgerät ein PowerShell-Windows, und geben Sie `(Get-MpPreference).EnableNetworkProtection` ein.

2.  Dies sollte wie unten gezeigt mit 0 antworten.

    ![Abbildung der Befehlszeile3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  Öffnen Sie nach dem Anwenden der Richtlinie ein PowerShell-Windows, und geben Sie `(Get-MpPreference).EnableNetworkProtection` ein.

4.  Dies sollte wie unten gezeigt mit 1 antworten.

    ![Abbildung der Befehlszeile4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
