---
title: Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: f430acb4a7fd1842a4ae26025ad5a63cccf8392f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640367"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Einstellungen von Microsoft 365, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der erhöhten Sicherheit von Microsoft 365 ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365

In dieser Phase aktivieren Sie die erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung. Weitere Details und Einstellungen finden Sie unter [Konfigurieren des Office 365 Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen

Für apps, die keine moderne Authentifizierung unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md) angewendet werden, was ein wichtiges Element für die Sicherung Ihres Microsoft 365-Abonnements und seiner digitalen Objekte ist. 

1. Wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich bei Ihrem Office 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.
    
  - Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer aus an.
    
  - Wenn Sie die simulierte Enterprise Microsoft 365-Testumgebung verwenden, verwenden Sie das [Azure-Portal](https://portal.azure.com) , um eine Verbindung mit dem virtuellen Computer Client1 herzustellen, und melden Sie sich dann von CLIENT1 aus an.
 
2. Klicken Sie auf der neuen Registerkarte " **Microsoft 365 Admin Center** " auf admin Centers **#a0 SharePoint**.
3. Klicken Sie auf der neuen **SharePoint Admin Center** -Registerkarte auf **Zugriffssteuerung**.
4. Klicken Sie unter **apps, die die moderne Authentifizierung nicht unterstützen**auf **blockieren**, und klicken Sie dann auf **OK**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivieren von Advanced Threat Protection für SharePoint, OneDrive für Unternehmen und Microsoft Teams

Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.

1. Wechseln Sie zum [Office 365 Security #a0 Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.

2. Wählen Sie im linken Navigationsbereich unter **Threat Management**die Option **Richtlinie #a0 sichere Anlagen**aus. 

3. Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.

4. Klicken Sie auf **Speichern**.


### <a name="enable-anti-malware"></a>Anti-Malware aktivieren

Malware ist Schadsoftware, die aus Viren und Spyware besteht. Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus. Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet. 

Office 365 verfügt über integrierte Funktionen für Malware und Spamfilterung, mit denen eingehende und ausgehende Nachrichten vor bösartiger Software geschützt werden und Sie vor Spam schützen können. Weitere Informationen finden Sie unter [Anti-Spam-#a0 Schutz vor Schadsoftware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Um sicherzustellen, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:

1. Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.
2. Klicken Sie auf **Anti-Malware**.
3. Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.
4. Klicken Sie im Fenster **Anti-Malware-Richtlinie** auf **Einstellungen**.
4. Klicken Sie unter **Allgemeine Filter für Anlagentypen** **auf #a0 speichern**.


## <a name="phase-3-examine-the-threat-management-dashboard"></a>Phase 3: Untersuchen des Threat Management-Dashboards

Office 365 Threat Management kann Ihnen dabei helfen, den Zugriff auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor bösartiger Software und Spam zu schützen. Außerdem verwenden Sie Threat Management, um die Reputation Ihrer Domäne zu schützen und festzustellen, ob Absender böswillige Konten aus Ihrer Domäne Spoofing. Weitere Informationen finden Sie unter [Threat Management im Microsoft 365 Security Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Nächste Schritte

Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktion finden Sie im Schritt [configure more Security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) in der **Information Protection** -Phase.

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

