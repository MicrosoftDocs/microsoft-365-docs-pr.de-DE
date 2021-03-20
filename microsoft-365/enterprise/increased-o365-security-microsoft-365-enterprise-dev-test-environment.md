---
title: Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Testumgebungshandbuch, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 for Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 928deae34dc16c70776eb512188d1a36ae169da5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909786"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel konfigurieren Sie zusätzliche Microsoft 365-Einstellungen, um die Sicherheit in Ihrer Microsoft 365 for Enterprise-Testumgebung zu erhöhen.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](../downloads/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung

Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie erhöhte Microsoft 365-Sicherheit in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen erhöhter Microsoft 365-Sicherheit erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur. Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Phase 2: Konfigurieren erhöhter Microsoft 365-Sicherheit

In dieser Phase aktivieren Sie erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 for Enterprise-Testumgebung. Weitere Details und Einstellungen finden Sie unter [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurieren von SharePoint Online zum Blockieren von Apps, die keine moderne Authentifizierung unterstützen

Apps, die die moderne Authentifizierung nicht unterstützen, können keine Identitäts- und Gerätezugriffskonfigurationen auf sie angewendet werden. [Dies](../security/office-365-security/microsoft-365-policies-configurations.md) ist ein wichtiges Element zum Sichern Ihres Microsoft 365-Abonnements und seiner digitalen Ressourcen. 

1. Wechseln Sie zum Microsoft 365 Admin Center ( ) und melden Sie sich mit Ihrem globalen Administratorkonto bei Ihrem [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365-Testumgebungsabonnement an.
    
  - Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer an.
    
  - Wenn Sie die simulierte Microsoft 365-Testumgebung [](https://portal.azure.com) des Unternehmens verwenden, verwenden Sie das Azure-Portal, um eine Verbindung mit dem virtuellen CLIENT1-Computer herzustellen, und melden Sie sich dann über CLIENT1 an.
 
2. Klicken Sie auf der neuen **Registerkarte Microsoft 365 Admin Center** unter Admin **Center** im linken Navigationsbereich auf **SharePoint**.
3. Klicken Sie auf der neuen **Registerkarte SharePoint Admin Center** auf Richtlinien > **Zugriffssteuerung**.
4. Klicken Sie auf Apps, die die moderne **Authentifizierung nicht unterstützen,** wählen Sie **Zugriff blockieren** aus, und klicken Sie dann auf **Speichern**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivieren von Defender für Office 365 für SharePoint, OneDrive for Business und Microsoft Teams

Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.

1. Wechseln Sie zum [Security & Compliance Center,](https://protection.office.com) und melden Sie sich mit Ihrem globalen Administratorkonto an.

2. Klicken Sie im linken Navigationsbereich unter **Bedrohungsverwaltung** auf **Richtlinie,** und klicken Sie dann auf **Sichere Anlagen**. 

3. Unter **Dateien in SharePoint, OneDrive und Microsoft Teams schützen**. Wählen **Sie ATP für SharePoint, OneDrive** und Microsoft Teams aktivieren aus.

4. Klicken Sie auf **Speichern**.


### <a name="enable-anti-malware"></a>Aktivieren von Schadsoftware

Malware ist Schadsoftware, die aus Viren und Spyware besteht. Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus. Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet. 

Microsoft 365 verfügt über integrierte Schadsoftware- und Spamfilterfunktionen, die ein- und ausgehende Nachrichten vor Schadsoftware schützen und Sie vor Spam schützen. Weitere Informationen finden Sie unter [Antispamschutz & Schutz vor Schadsoftware](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

So stellen Sie sicher, dass die Schadsoftwareverarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:

1. Klicken Sie auf die Schaltfläche Zurück in Ihrem Browser, um zur Seite **Richtlinie zurück** zu gelangen.
2. Klicken Sie **auf An malware**.
3. Doppelklicken Sie auf die Richtlinie mit dem Namen **Standard**.
4. Klicken Sie im Fenster Richtlinie für **Schadsoftware** auf **Einstellungen**.
4. Wählen **Sie unter Filter Allgemeine Anlagentypen** die Option **Ein** aus, und klicken Sie dann auf **Speichern.**


## <a name="phase-3-examine-the-security-dashboard"></a>Phase 3: Untersuchen des Sicherheitsdashboards

Die Bedrohungsverwaltung in Microsoft 365 kann Ihnen helfen, den Zugriff mobiler Geräte auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor Schadsoftware und Spam zu schützen. Sie verwenden auch die Bedrohungsverwaltung, um die Reputation Ihrer Domäne zu schützen und zu bestimmen, ob Absender Konten aus Ihrer Domäne böswillig spoofieren. 

So sehen Sie das Sicherheitsdashboard:

1. Wechseln Sie bei Bedarf zum [Security & Compliance Center,](https://protection.office.com) und melden Sie sich mit Ihrem globalen Administratorkonto an.

2. Klicken Sie im linken Navigationsbereich unter **Bedrohungsverwaltung** auf **Dashboard**.

Werfen Sie einen genauen Blick auf alle Karten auf dem Dashboard, um sich mit den bereitgestellten Informationen vertraut zu machen.

Weitere Informationen finden Sie unter [Security Dashboard](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Phase 4: Überprüfen der Microsoft Secure Score

Microsoft Secure Score zeigt Ihre Sicherheitslage als Zahl an, die Ihre aktuelle Stufe relativ zu den Features angibt, die in Ihrem Abonnement verfügbar sind. Außerdem erhalten Sie eine Liste der Verbesserungsmaßnahmen, die Sie zur Verbesserung Ihrer Bewertung ergreifen können.

1. Erstellen Sie eine neue Registerkarte in Ihrem Browser, wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com/)und klicken Sie dann auf **Punktzahl sichern.**
2. Notieren Sie **sich**  auf der Registerkarte Übersicht Ihre aktuelle Secure Score und wie sie mit dem globalen Durchschnitt und Abonnements mit einer ähnlichen Anzahl von Lizenzen verglichen wird.
3. Lesen Sie **auf der** Registerkarte Verbesserungsaktionen die Liste der Aktionen durch, die Sie zum Erhöhen Ihrer Bewertung ergreifen können.

Weitere Informationen finden Sie unter [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)