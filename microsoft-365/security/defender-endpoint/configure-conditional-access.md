---
title: Konfigurieren des bedingten Zugriffs in Microsoft Defender ATP
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
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165861"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Dieser Abschnitt führt Sie durch alle Schritte, die Sie zum ordnungsgemäßen Implementieren des bedingten Zugriffs ausführen müssen.

### <a name="before-you-begin"></a>Vorbereitung
>[!WARNING]
>Beachten Sie, dass in diesem Szenario registrierte Azure AD-Geräte nicht unterstützt werden.</br>
>Nur in Intune registrierte Geräte werden unterstützt.


Sie müssen sicherstellen, dass alle Ihre Geräte in Intune registriert sind. Sie können eine der folgenden Optionen verwenden, um Geräte in Intune zu registrieren:


- IT-Administrator: Weitere Informationen zum Aktivieren der automatischen Registrierung finden Sie unter [Windows-Registrierung.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Endbenutzer: Weitere Informationen zum Registrieren Ihres Windows 10-Geräts in Intune finden Sie unter [Registrieren Ihres Windows 10-Geräts in Intune.](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)
- Alternative für Endbenutzer: Weitere Informationen zum Beitritt zu einer Azure AD-Domäne finden Sie unter [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).



Es gibt Schritte, die Sie im Microsoft Defender Security Center, im Intune-Portal und im Azure AD-Portal ausführen müssen.

Es ist wichtig, die erforderlichen Rollen für den Zugriff auf diese Portale zu notieren und bedingten Zugriff zu implementieren:
- **Microsoft Defender Security Center** – Sie müssen sich beim Portal mit einer globalen Administratorrolle anmelden, um die Integration zu aktivieren.
- **Intune** : Sie müssen sich beim Portal mit Sicherheitsadministratorrechten mit Verwaltungsberechtigungen anmelden. 
- **Azure AD-Portal** : Sie müssen sich als globaler Administrator, Sicherheitsadministrator oder Bedingter Zugriffsadministrator anmelden.


> [!NOTE]
> Sie benötigen eine Microsoft Intune-Umgebung, in der Intune verwaltet wird und Azure AD Windows 10-Geräten beigetreten ist.

Gehen Sie wie folgt vor, um bedingten Zugriff zu aktivieren:
- Schritt 1: Aktivieren der Microsoft Intune-Verbindung von Microsoft Defender Security Center
- Schritt 2: Aktivieren der Defender for Endpoint-Integration in Intune
- Schritt 3: Erstellen der Compliancerichtlinie in Intune
- Schritt 4: Zuweisen der Richtlinie 
- Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Schritt 1: Aktivieren der Microsoft Intune-Verbindung
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterte Features Microsoft**  >  **Intune-Verbindung aus.**
2. Umschalten der Microsoft Intune-Einstellung auf **Ein**.
3. Klicken **Sie auf Einstellungen speichern**.


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Schritt 2: Aktivieren der Defender for Endpoint-Integration in Intune
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen **Sie Gerätekonformität**  >  **Microsoft Defender ATP aus.**
3. Legen **Sie Connect Windows 10.0.15063+** auf Microsoft Defender Advanced Threat Protection auf Ein **fest.**
4. Klicken Sie auf **Speichern**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Schritt 3: Erstellen der Compliancerichtlinie in Intune
1. Wählen Sie [im Azure-Portal](https://portal.azure.com) **Alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune aus.**
2. Wählen **Sie Gerätekonformitätsrichtlinien**  >    >  **Erstellen einer Richtlinie aus.**
3. Geben Sie einen **Namen und** eine **Beschreibung ein.**
4. Wählen **Sie unter Plattform** Windows **10 und höher aus.**
5. Legen Sie in den  Einstellungen für **den** Geräteinte health die Einstellung Gerätebedrohungsstufe auf ihre bevorzugte Stufe festlegen:

   - **Gesichert:** Diese Stufe ist die sicherste. Das Gerät kann keine vorhandenen Bedrohungen haben und weiterhin auf Unternehmensressourcen zugreifen. Wenn Bedrohungen gefunden werden, wird das Gerät als nicht konform ausgewertet.
   - **Niedrig:** Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Ebene vorhanden sind. Geräte mit mittleren oder hohen Bedrohungsstufen sind nicht kompatibel.
   - **Medium**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedrig oder mittel sind. Wenn Bedrohungen auf hoher Ebene erkannt werden, wird das Gerät als nicht konform festgelegt.
   - **High**: Diese Stufe ist die am wenigsten sichere Stufe und ermöglicht alle Bedrohungsstufen. Geräte mit hohen, mittleren oder niedrigen Bedrohungsstufen werden daher als kompatibel betrachtet.

6. Wählen **Sie OK** und **Erstellen** aus, um Ihre Änderungen zu speichern (und die Richtlinie zu erstellen).

### <a name="step-4-assign-the-policy"></a>Schritt 4: Zuweisen der Richtlinie
1. Wählen Sie [im Azure-Portal](https://portal.azure.com) **Alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune aus.**
2. Wählen **Sie Gerätekonformitätsrichtlinien**  >  > Sie Ihre Microsoft Defender ATP-Konformitätsrichtlinie aus.
3. Wählen Sie **Zuweisungen** aus.
4. Schließen Sie Ihre Azure AD-Gruppen ein, oder schließen Sie sie aus, um ihnen die Richtlinie zuzuordnen.
5. Wählen Sie Speichern aus, um die Richtlinie für die Gruppen **zu bereitstellen.** Die benutzerorientierten Geräte, auf die die Richtlinie ausgerichtet ist, werden auf Compliance geprüft.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff
1. Öffnen Sie [im Azure-Portal](https://portal.azure.com) **Azure Active Directory** Conditional  >  **Access**  >  **Neue Richtlinie**.
2. Geben Sie einen **Richtliniennamen ein,** und wählen **Sie Benutzer und Gruppen aus.** Verwenden Sie die Optionen Include oder Exclude, um Ihre Gruppen für die Richtlinie hinzuzufügen, und wählen Sie **Fertig aus.**
3. Wählen **Sie Cloud-Apps** aus, und wählen Sie aus, welche Apps geschützt werden soll. Wählen Sie beispielsweise **Apps auswählen** aus, und wählen Sie **Office 365 SharePoint Online** und Office **365 Exchange Online aus.** Wählen Sie **Fertig** aus, um die Änderungen zu speichern.

4. Wählen **Sie Bedingungen**  >  **Client-Apps aus,** um die Richtlinie auf Apps und Browser anzuwenden. Wählen Sie beispielsweise **Ja** aus, und aktivieren Sie **dann Browser-** und **Mobile-Apps und Desktopclients.** Wählen Sie **Fertig** aus, um die Änderungen zu speichern.

5. Wählen **Sie Gewähren** aus, um bedingten Zugriff basierend auf der Gerätekonformität anzuwenden. Wählen Sie z. **B. Zugriff gewähren**  >  **Gerät als kompatibel markieren aus.** Wählen **Sie Auswählen** aus, um Ihre Änderungen zu speichern.

6. Wählen **Sie Richtlinie aktivieren** und dann **Erstellen** aus, um Ihre Änderungen zu speichern.

Weitere Informationen finden Sie unter [Aktivieren von Microsoft Defender ATP mit bedingten Zugriff in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
