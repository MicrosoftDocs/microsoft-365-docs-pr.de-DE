---
title: Konfigurieren des bedingten Zugriffs in Microsoft Defender für Endpunkt
description: Erfahren Sie mehr über die Schritte, die Sie in Intune, Microsoft Defender Security Center und Azure ausführen müssen, um bedingten Zugriff zu implementieren.
keywords: bedingter Zugriff, bedingter Zugriff, Geräterisiko, Risikostufe, Integration, Intune-Integration
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843974"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Konfigurieren des bedingten Zugriffs in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Dieser Abschnitt führt Sie durch alle Schritte, die Sie ausführen müssen, um den bedingten Zugriff ordnungsgemäß zu implementieren.

### <a name="before-you-begin"></a>Bevor Sie beginnen
>[!WARNING]
>Es ist wichtig zu beachten, dass registrierte Azure AD-Geräte in diesem Szenario nicht unterstützt werden.</br>
>Nur in Intune registrierte Geräte werden unterstützt.


Sie müssen sicherstellen, dass alle Ihre Geräte in Intune registriert sind. Sie können eine der folgenden Optionen verwenden, um Geräte in Intune zu registrieren:


- IT-Administrator: Weitere Informationen zum Aktivieren der automatischen Registrierung finden Sie unter [Windows-Registrierung.](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Endbenutzer: Weitere Informationen zum Registrieren Ihres Windows 10 Geräts in Intune finden Sie unter [Registrieren Ihres Windows 10 Geräts in Intune.](/intune/quickstart-enroll-windows-device)
- Alternative Endbenutzer: Weitere Informationen zum Beitreten zu einer Azure AD-Domäne finden Sie unter [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).



Es gibt Schritte, die Sie in Microsoft Defender Security Center, im Intune-Portal und im Azure AD-Portal ausführen müssen.

Es ist wichtig, die erforderlichen Rollen zu beachten, um auf diese Portale zuzugreifen und den bedingten Zugriff zu implementieren:
- **Microsoft Defender Security Center** : Sie müssen sich mit einer globalen Administratorrolle beim Portal anmelden, um die Integration zu aktivieren.
- **Intune** : Sie müssen sich beim Portal mit Sicherheitsadministratorrechten mit Verwaltungsberechtigungen anmelden. 
- **Azure AD-Portal** – Sie müssen sich als globaler Administrator, Sicherheitsadministrator oder Administrator für bedingten Zugriff anmelden.


> [!NOTE]
> Sie benötigen eine Microsoft Intune Umgebung mit intune-verwalteten und Azure AD-Windows 10 Geräten.

Führen Sie die folgenden Schritte aus, um den bedingten Zugriff zu aktivieren:
- Schritt 1: Aktivieren der Microsoft Intune Verbindung von Microsoft Defender Security Center
- Schritt 2: Aktivieren der Defender für Endpunkt-Integration in Intune
- Schritt 3: Erstellen der Compliancerichtlinie in Intune
- Schritt 4: Zuweisen der Richtlinie 
- Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Schritt 1: Aktivieren der Microsoft Intune Verbindung
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterte Features** Microsoft Intune  >  **Verbindung** aus.
2. Umschalten der einstellung Microsoft Intune auf **"Ein".**
3. Klicken Sie auf **"Einstellungen speichern".**


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Schritt 2: Aktivieren der Defender für Endpunkt-Integration in Intune
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie **"Gerätekompatibilität"**  >  **Microsoft Defender ATP** aus.
3. Legen Sie **Verbinden Windows 10.0.15063+-Geräte auf ein Microsoft Defender Advanced Threat Protection** **fest.**
4. Klicken Sie auf **Speichern**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Schritt 3: Erstellen der Compliancerichtlinie in Intune
1. Wählen Sie im [Azure-Portal](https://portal.azure.com) **alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune** aus.
2. Wählen Sie **"Gerätekompatibilitätsrichtlinien**  >    >  **erstellen" aus.**
3. Geben Sie einen **Namen** und eine **Beschreibung** ein.
4. Wählen Sie **in** **"Plattform"** Windows 10 und höher aus.
5. Legen Sie in den Einstellungen für die **Geräteintegrität** fest, **dass sich das Gerät auf oder unter der Geräte-Bedrohungsstufe auf** Die bevorzugte Ebene befinden soll:

   - **Gesichert:** Diese Stufe ist die sicherste. Das Gerät kann keine vorhandenen Bedrohungen haben und weiterhin auf Unternehmensressourcen zugreifen. Wenn Bedrohungen gefunden werden, wird das Gerät als nicht konform ausgewertet.
   - **Niedrig:** Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Ebene vorhanden sind. Geräte mit mittleren oder hohen Bedrohungsstufen sind nicht konform.
   - **Mittel:** Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedrig oder mittel sind. Wenn Bedrohungen auf hoher Ebene erkannt werden, wird das Gerät als nicht konform eingestuft.
   - **Hoch:** Diese Stufe ist am wenigsten sicher und lässt alle Bedrohungsebenen zu. Geräte mit hohen, mittleren oder niedrigen Bedrohungsstufen werden daher als konform betrachtet.

6. Wählen Sie **"OK"** und **"Erstellen"** aus, um Ihre Änderungen zu speichern (und die Richtlinie zu erstellen).

### <a name="step-4-assign-the-policy"></a>Schritt 4: Zuweisen der Richtlinie
1. Wählen Sie im [Azure-Portal](https://portal.azure.com) **alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune** aus.
2. Wählen Sie **"Gerätekompatibilitätsrichtlinien"**  >   aus,> Wählen Sie Ihre Microsoft Defender für Endpunkt-Compliancerichtlinie aus.
3. Wählen Sie **Zuweisungen** aus.
4. Schließen Sie Ihre Azure AD-Gruppen ein, oder schließen Sie sie aus, um ihnen die Richtlinie zuzuweisen.
5. Um die Richtlinie für die Gruppen bereitzustellen, wählen Sie **Speichern** aus. Die Benutzergeräte, auf die die Richtlinie abzielt, werden auf Compliance ausgewertet.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff
1. Öffnen Sie im [Azure-Portal](https://portal.azure.com) **Azure Active Directory**  >  Neue Richtlinie für **bedingten Zugriff.**  >  
2. Geben Sie einen **Richtliniennamen** ein, und wählen Sie **"Benutzer und Gruppen"** aus. Verwenden Sie die Optionen "Einschließen" oder "Ausschließen", um Ihre Gruppen für die Richtlinie hinzuzufügen, und wählen Sie **"Fertig"** aus.
3. Wählen Sie **Cloud-Apps** aus, und wählen Sie aus, welche Apps geschützt werden sollen. Wählen Sie beispielsweise **"Apps auswählen"** und **"Office 365 SharePoint Online"** und **"Office 365 Exchange Online"** aus. Wählen Sie **Fertig** aus, um die Änderungen zu speichern.

4. Wählen Sie "Bedingungen"-Client-Apps  >   aus, um die Richtlinie auf Apps und Browser anzuwenden. Wählen Sie beispielsweise **"Ja"** aus, und aktivieren Sie dann **Browser-** und **mobile Apps und Desktopclients.** Wählen Sie **Fertig** aus, um die Änderungen zu speichern.

5. Wählen Sie **"Gewähren"** aus, um bedingten Zugriff basierend auf der Gerätekompatibilität anzuwenden. Wählen Sie beispielsweise **"Zugriff gewähren"** aus,  >  **damit das Gerät als kompatibel gekennzeichnet ist.** Wählen Sie **"Auswählen"** aus, um Ihre Änderungen zu speichern.

6. Wählen Sie **"Richtlinie aktivieren"** und dann **"Erstellen"** aus, um Die Änderungen zu speichern.

Weitere Informationen finden Sie unter Erzwingen der [Compliance für Microsoft Defender für Endpunkt mit bedingtem Zugriff in Intune.](/intune/advanced-threat-protection)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
