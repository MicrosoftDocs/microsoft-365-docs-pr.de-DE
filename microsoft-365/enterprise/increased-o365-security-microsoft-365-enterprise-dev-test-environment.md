---
title: Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Test Labor Handbuch, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283655"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Microsoft 365-Einstellungen, um die Sicherheit in Ihrer Microsoft 365 Enterprise-Testumgebung zu verbessern.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie nur erhöhte Sicherheit von Microsoft 365 auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der erhöhten Sicherheit von Microsoft 365 erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365

In dieser Phase aktivieren Sie erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 Enterprise-Testumgebung. Weitere Informationen und Einstellungen finden Sie unter [Konfigurieren Ihres Office 365-Mandanten für mehr Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen

Apps, die die moderne Authentifizierung nicht unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md) verwenden, was ein wichtiger Bestandteil der Sicherung ihres Microsoft 365-Abonnements und der digitalen Objekte ist. 

1. Wechseln Sie zum Office-Portal[https://office.com](https://office.com)(), und melden Sie sich bei ihrem Office 365-Testabonnement mit ihrem globalen Administratorkonto an.
    
  - Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich auf dem lokalen Computer an.
    
  - Wenn Sie die simulierte Enterprise-Testumgebung von Microsoft 365 verwenden, stellen Sie mithilfe des [Azure](https://portal.azure.com) -Portals eine Verbindung mit dem virtuellen Computer Client1 her, und melden Sie sich dann bei CLIENT1 an.
 
2. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **Admin**.
3. Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** auf **Admin Center > SharePoint**.
4. Klicken Sie auf der neuen Registerkarte **SharePoint Admin Center** auf **Zugriffssteuerung**.
5. Klicken Sie unter **apps, die die moderne Authentifizierung nicht unterstützen**auf **blockieren**, und klicken Sie dann auf **OK**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivieren von Advanced Threat Protection für SharePoint, OneDrive for Business und Microsoft Teams

Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.

1. Wechseln Sie zum [Office 365 Security _AMP_ Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.

2. Wählen Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie > sichere Anlagen**aus. 

3. Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.

4. Klicken Sie auf **Speichern**.


### <a name="enable-anti-malware"></a>Aktivieren von Antischadsoftware

Malware ist Schadsoftware, die aus Viren und Spyware besteht. Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus. Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet. 

Office 365 verfügt über integrierte Funktionen zur Filterung von Schadsoftware und Spam, die eingehende und ausgehende Nachrichten vor Schadsoftware schützen und Sie vor Spam schützen. Weitere Informationen finden Sie unter [Antispam-&-Schutz vor Schadsoftware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

So stellen Sie sicher, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Dateitypen von Anlagen ausgeführt wird:

1. Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.
2. Klicken **** Sie auf Antischadsoftware.
3. Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.
4. Klicken Sie im Fenster Antischadsoftware **-Richtlinie** auf **Einstellungen**.
4. Klicken Sie unter **Allgemeine Anlagentypen Filter** **auf > speichern**.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>Phase 3: Untersuchen von Office 365-Sicherheitstools und-Protokollen

In dieser Phase sehen Sie sich die integrierten Dienste an, die Sie über Sicherheitsereignisse informieren und ihre allgemeine Sicherheitsposition messen.

### <a name="threat-management-dashboard"></a>Risikomanagement-Dashboard

Mithilfe von Office 365 Threat Management können Sie den Zugriff mobiler Geräte auf die Daten Ihrer Organisation steuern und verwalten, Ihre Organisation vor Datenverlust schützen und eingehende und ausgehende Nachrichten vor Schadsoftware und Spam schützen. Sie verwenden auch die Bedrohungs Verwaltung, um die Reputation Ihrer Domäne zu schützen und zu ermitteln, ob Absender in böswilliger Absicht Konten aus Ihrer Domäne spoofen. Weitere Informationen finden Sie unter [Threat Management im Microsoft 365 Security Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).


### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 Cloud App-Sicherheits Dashboard

Office 365 Cloud App Security, bisher bekannt als Office 365 Advanced Security Management, ermöglicht Ihnen das Erstellen von Richtlinien, mit denen Sie verdächtige Aktivitäten in Ihrem Office 365-Abonnement überwachen und darüber informieren können, damit Sie untersuchen und mögliche Korrekturaktion. Weitere Informationen finden Sie unter [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktionsumgebung finden Sie unter [Konfigurieren von mehr Sicherheit für Microsoft 365](infoprotect-configure-increased-security-office-365.md) Schritt in der **Informationsschutz** Phase.

Erkunden Sie zusätzliche Features und Funktionen zum [Schutz von Informationen](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

