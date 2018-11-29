---
title: Erhöhte Sicherheit von Office 365 für die Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide So aktivieren Sie zusätzliche Einstellungen von Office 365-Sicherheit Ihrer Umgebung für Microsoft 365 Enterprise.
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867826"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Erhöhte Sicherheit von Office 365 für die Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel konfigurieren Sie zusätzliche Einstellungen von Office 365 zum Erhöhen der Sicherheit in Ihrer testumgebung Microsoft 365 Enterprise.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen erhöhte Sicherheit für Office 365 konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise erhöhte Sicherheit für Office 365 konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Erhöhte Sicherheit für Office 365 Testen erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 


## <a name="phase-2-configure-increased-office-365-security"></a>Phase 2: Konfigurieren von erhöhte Sicherheit für Office 365

In dieser Phase können Sie erhöhte Sicherheit für Office 365 für Ihre Umgebung für Microsoft 365 Enterprise. Weitere Einzelheiten und Einstellungen finden Sie unter [Configure Ihre Office 365-Mandanten, um eine höhere Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurieren von SharePoint Online, um apps zu blockieren, die moderne Authentifizierung nicht unterstützen

Apps, die moderne Authentifizierung nicht unterstützen können nicht angewendet werden, also ein wichtiges Element der Schützen Ihres Microsoft-365-Abonnements und seine digitaler Objekte [Identität und Gerät zugreifen Konfigurationen](microsoft-365-policies-configurations.md) haben. 

1. Wechseln Sie zu Office 365-Portal ([https://portal.office.com](https://portal.office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.
    
  - Wenn Sie die einfache Microsoft 365 Test-Umgebung verwenden, melden Sie sich von Ihrem lokalen Computer.
    
  - Bei Verwendung die testumgebung simulierten Enterprise Microsoft 365 mithilfe von der [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer CLIENT1, und melden Sie sich von CLIENT1 aus.
 
2. Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** auf **Admin**.
3. Klicken Sie auf der Registerkarte Neu **Microsoft 365 Administrationscenter** auf **Zentriert Admin > SharePoint**.
4. Klicken Sie auf der Registerkarte Neu **SharePoint Administrationscenter** **Steuerung des Zugriffs**auf.
5. Klicken Sie unter **Apps, die moderne Authentifizierung nicht unterstützen**, auf **Blockieren > OK**.


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren Sie die erweiterte Threat Protection (ATP) für SharePoint, OneDrive und Microsoft-Teams

Office 365 erweiterte Threat Protection (ATP) ist ein Feature von Exchange Online Protection (EOP), mit deren behalten Schadsoftware aus Ihrer e-Mails. Mit ATP Sie Richtlinien erstellen, in der Exchange-Verwaltungskonsole (EAC) oder die Sicherheit und Compliance Center, die sicherstellen, dass Ihre Benutzer greifen Sie auf nur Links oder Anlagen in e-Mails, die als nicht bösartige identifiziert werden. Weitere Informationen finden Sie unter [erweiterte Schutz für sichere Anlagen und sichere Links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).

1. Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.
2. Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Bedrohung Verwaltung > Richtlinie**.
3. Klicken Sie auf **ATP sichere Anlagen**.
4. Klicken Sie im **sicheren Anlagen** aktivieren Sie das Kontrollkästchen **auf ATP für SharePoint, OneDrive, und Microsoft-Teams**, und klicken Sie dann auf **Speichern**.

### <a name="enable-anti-malware"></a>Anti-Malware aktivieren

Malware besteht Viren und Spyware. Viren infiziert andere Programme und Daten, und sie Ihren Computer Programme infiziert Nachrichtensymbol verteilt. Spyware bezieht sich auf Schadsoftware, die Ihre persönlichen Informationen, wie etwa-Anmeldung und persönliche Daten sammelt und sendet ihn wieder an den Autor Malware. 

Office 365 verfügt über integrierte Malware- und spamfilterfunktionen, die eingehende und ausgehende Nachrichten vor Schadsoftware schützen und Schutz vor Spam. Weitere Informationen finden Sie unter [Anti-Spam & Anti-Malware Protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

So stellen Sie sicher, dass Anti-Malware Verarbeitung für Dateien mit gemeinsamen Anlagendateitypen ausgeführt wird:

1. Klicken Sie auf die zurück-Schaltfläche in Ihrem Browser zu der Seite **Richtlinie** zurückzukehren.
2. Klicken Sie auf **Anti-Malware**.
3. Doppelklicken Sie auf die Richtlinie mit dem Namen **Default**.
4. Klicken Sie auf **Einstellungen**, klicken Sie im Fenster **Antischadsoftware - Richtlinie** .
4. Klicken Sie unter **allgemeine Typen von Anhängen Filter**auf **auf > Speichern**.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>Phase 3: Untersuchen Sie Sicherheits-Tools für Office 365 und Protokolle

In dieser Phase betrachten Sie integrierte Dienste, die über Sicherheitsereignisse informiert Sie und Ihre Sicherheitsstatus messen.

### <a name="threat-management-dashboard"></a>Threat Management dashboard

Office 365 Threat Management hilft Ihnen steuern und Verwalten von mobilen Gerätezugriff auf die Daten des Unternehmen, Ihre Organisation vor Datenverlust schützen und Schutz von eingehenden und ausgehenden Nachrichten vor Schadsoftware und Spam. Sie können auch Bedrohung, dass Management zum Schutz Ihrer Domäne und um zu bestimmen, ob Absender in böswilliger Absicht spoofing sind oder nicht von Ihrer Domäne Konten verwenden. Weitere Informationen finden Sie unter [Threat Management in Office 365-Sicherheit & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).

Verwenden Sie folgende Schritte aus, um das Office 365 Threat Management Dashboard anzuzeigen:

1. Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.
2. Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Bedrohung Verwaltung > Dashboard**.
3. Beachten Sie auf der neuen Registerkarte **Dashboard** in Ihrem Browser die Malwaretrends, Erkenntnisse und anderen Abschnitten des Dashboards.

### <a name="office-365-cloud-app-security-dashboard"></a>Dashboard für Office 365-Cloud-App-Sicherheit

Office 365 Cloud App-Sicherheit, früher bekannt als Office 365 Advanced Security Management können Sie Richtlinien erstellen, die für überwachen und informieren Sie verdächtige Aktivitäten in Ihrem Office 365-Abonnement, damit Sie überprüfen können, und möglich leiten Remediation-Aktion. Weitere Informationen finden Sie unter [Overview of Office 365 Cloud App-Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

1. Klicken Sie auf der Registerkarte **Microsoft 365 Administrationscenter** Ihres Browsers auf **Zentriert Admin > Sicherheit und Compliance**.
2. Klicken Sie auf der neuen Registerkarte **Sicherheit und Compliance** auf **Warnungen > erweiterte Benachrichtigungen verwalten > Gehe zu Office 365-Cloud-App-Sicherheit**.
3. Beachten Sie auf der Registerkarte Neu **Cloud App-Sicherheit** Dashboard-Ansicht und die Liste der Standard-Richtlinien, die überwacht werden, die für verschiedene Aktivitäten in Ihrem Office 365-Abonnement.
4. Klicken Sie auf das Dashboard-Symbol, um eine Zusammenfassung der Cloud App-Sicherheit Aktivitäten angezeigt, die überwacht werden.
5. Klicken Sie auf **Überprüfen** (das Symbol Brille) und dann auf **Aktivitätsprotokolls** , um die Liste der zuletzt verwendete Anmeldungen und andere Aktivitäten finden Sie unter.

### <a name="secure-score"></a>Sichere Score

1. Erstellen Sie eine neue Registerkarte in Ihrem Browser, und wechseln Sie zur **securescore.office.com**.
2. Beachten Sie auf der **Registerkarte Dashboard**Ihr aktuelles Ergebnis Secure und die Liste der Aktionen in der Warteschlange, um Ihr Ergebnis zu erhöhen.

Finden Sie im Schritt [konfigurieren eine höhere Sicherheit für Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) in der Phase **Information Protection** Informationen und Links zum Konfigurieren dieser Einstellungen in der Produktion.

## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

