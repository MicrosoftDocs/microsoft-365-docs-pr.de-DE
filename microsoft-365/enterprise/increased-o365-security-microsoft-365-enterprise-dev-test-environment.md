---
title: Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 für Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um zusätzliche Microsoft 365-Sicherheitseinstellungen für Ihre Microsoft 365 für Enterprise-Testumgebung zu aktivieren.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847000"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Erhöhte Microsoft 365-Sicherheit für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel Konfigurieren Sie zusätzliche Einstellungen von Microsoft 365, um die Sicherheit in Ihrer Microsoft 365 für Enterprise-Testumgebung zu verbessern.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](../downloads/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie die erhöhte Sicherheit von Microsoft 365 nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die erhöhte Sicherheit von Microsoft 365 in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der erhöhten Sicherheit von Microsoft 365 ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Phase 2: Konfigurieren der erhöhten Sicherheit von Microsoft 365

In dieser Phase aktivieren Sie die erhöhte Sicherheit von Microsoft 365 für Ihre Microsoft 365 für Enterprise-Testumgebung. Weitere Details und Einstellungen finden Sie unter [Konfigurieren Ihres Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurieren von SharePoint Online zum Blockieren von apps, die keine moderne Authentifizierung unterstützen

Für apps, die keine moderne Authentifizierung unterstützen, können keine [Identitäts-und Gerätezugriffs Konfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) angewendet werden, was ein wichtiges Element für die Sicherung Ihres Microsoft 365-Abonnements und seiner digitalen Objekte ist. 

1. Wechseln Sie zum Microsoft 365 Admin Center ( [https://portal.microsoft.com](https://portal.microsoft.com) ), und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.
    
  - Wenn Sie die einfache Microsoft 365-Testumgebung verwenden, melden Sie sich von Ihrem lokalen Computer aus an.
    
  - Wenn Sie die simulierte Enterprise Microsoft 365-Testumgebung verwenden, verwenden Sie das [Azure-Portal](https://portal.azure.com) , um eine Verbindung mit dem virtuellen Computer Client1 herzustellen, und melden Sie sich dann von CLIENT1 aus an.
 
2. Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** unter **Admin Center** im linken Navigationsbereich auf **SharePoint**.
3. Klicken Sie auf der neuen Registerkarte **SharePoint Admin Center** auf **Richtlinien > Zugriffssteuerung**.
4. Klicken Sie auf **apps, die die moderne Authentifizierung nicht unterstützen** , wählen Sie **Zugriff blockieren** aus, und klicken Sie dann auf **Speichern**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivieren von Defender für Office 365 für SharePoint, OneDrive für Unternehmen und Microsoft Teams

Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.

1. Wechseln Sie zum [Security & Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.

2. Klicken Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung** auf **Richtlinie** , und klicken Sie dann auf **sichere Anlagen**. 

3. Unter **Protect Files in SharePoint, OneDrive und Microsoft Teams**. Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** aus.

4. Klicken Sie auf **Speichern**.


### <a name="enable-anti-malware"></a>Anti-Malware aktivieren

Malware ist Schadsoftware, die aus Viren und Spyware besteht. Viren infizieren Programme und Daten und breiten sich auf dem ganzen Computer aus. Als Spyware wird Schadsoftware bezeichnet, die persönliche Informationen, wie etwa Anmelde- und persönliche Daten, auf Ihrem Computer erfasst und an den Urheber der Schadsoftware zurücksendet. 

Microsoft 365 verfügt über integrierte Funktionen für Malware und Spamfilterung, mit denen eingehende und ausgehende Nachrichten vor bösartiger Software geschützt werden und Sie vor Spam schützen können. Weitere Informationen finden Sie unter [Anti-Spam & Anti-Malware Protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Um sicherzustellen, dass die Antischadsoftware-Verarbeitung für Dateien mit gängigen Anlagendateitypen ausgeführt wird:

1. Klicken Sie auf die Schaltfläche "zurück" in Ihrem Browser, um zur **Richtlinien** Seite zurückzukehren.
2. Klicken Sie auf **Anti-Malware**.
3. Doppelklicken Sie auf die Richtlinie mit dem Namen **default**.
4. Klicken Sie im Fenster **Anti-Malware-Richtlinie** auf **Einstellungen**.
4. Wählen Sie unter **Allgemeine Anlagentypen Filter** die Option **ein** aus, und klicken Sie dann auf **Speichern**.


## <a name="phase-3-examine-the-security-dashboard"></a>Phase 3: Überprüfen des Sicherheits Dashboards

Threat Management in Microsoft 365 kann Ihnen dabei helfen, den Zugriff auf die Daten Ihrer Organisation zu steuern und zu verwalten, Ihre Organisation vor Datenverlust zu schützen und eingehende und ausgehende Nachrichten vor bösartiger Software und Spam zu schützen. Außerdem verwenden Sie Threat Management, um die Reputation Ihrer Domäne zu schützen und festzustellen, ob Absender böswillige Konten aus Ihrer Domäne Spoofing. 

So zeigen Sie das Sicherheits Dashboard an:

1. Wechseln Sie bei Bedarf zum [Security & Compliance Center](https://protection.office.com) , und melden Sie sich mit ihrem globalen Administratorkonto an.

2. Klicken Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung** auf **Dashboard**.

Werfen Sie einen Blick auf alle Karten im Dashboard, um sich mit den bereitgestellten Informationen vertraut zu machen.

Weitere Informationen finden Sie unter [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Phase 4: Untersuchen von Microsoft Secure Score

Microsoft Secure Score zeigt Ihre Sicherheitsposition als Nummer an, die Ihre aktuelle Ebene relativ zu den in Ihrem Abonnement verfügbaren Features angibt. Außerdem erhalten Sie eine Liste von Verbesserungs Aktionen, die Sie ausführen können, um Ihre Punktzahl zu verbessern.

1. Erstellen Sie eine neue Registerkarte in Ihrem Browser, und wechseln Sie zum [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/), und klicken Sie dann auf **sichere Bewertung**.
2. Notieren Sie sich auf der Registerkarte **Übersicht**  Ihre aktuelle sichere Bewertung und wie diese mit dem globalen Durchschnitt und Abonnements mit ähnlicher Anzahl von Lizenzen verglichen wird.
3. Lesen Sie auf der Registerkarte **Verbesserungs Aktionen** die Liste der Aktionen durch, die Sie ausführen können, um Ihre Punktzahl zu verbessern.

Weitere Informationen finden Sie unter [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Nächste Schritte

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
