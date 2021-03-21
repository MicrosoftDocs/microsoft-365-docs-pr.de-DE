---
title: Berichte im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Verwenden Sie das Security & Compliance Center, um verschiedene Berichte für Ihre SharePoint Online- und Exchange Online-Organisation sowie Azure Active Directory-Berichte zu erhalten.
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926153"
---
# <a name="reports-in-the-security--compliance-center"></a>Berichte im Security & Compliance Center

Sie können die Seite Berichte **anzeigen** im Security & Compliance Center verwenden, um schnell auf Überwachungsberichte für Ihre SharePoint Online- und Exchange Online-Organisationen zu zugreifen. Sie können auch über die Seite Berichte anzeigen auf Azure Active Directory (AD)-Benutzer-Anmeldeberichte, Benutzeraktivitätsberichte und das Azure AD-Überwachungsprotokoll **zugreifen.** Der Grund dafür ist, dass Ihr kostenpflichtiges Microsoft 365-Abonnement ein kostenloses Abonnement für Microsoft Azure enthält. Wenn Sie zum ersten Mal versuchen, auf diese Azure-Berichte zu zugreifen, müssen Sie einen einmaligen Registrierungsprozess abschließen. 
  
> [!TIP]
> Weitere Berichte zu Aktivitäten in Ihrer Organisation finden Sie unter [Aktivitätsberichte im Microsoft 365 Admin Center](../admin/activity-reports/activity-reports.md). 
  
 **Bevor Sie beginnen:**
  
Sie benötigen die folgenden Berechtigungen zum Anzeigen von Berichten im Security & Compliance Center.
  
- Ihnen muss die Rolle "Security Reader" im Exchange Admin Center (EAC) zugewiesen werden, um Berichte im Security & Compliance Center anzeigen zu können. Diese Rolle wird standardmäßig den Rollengruppen Organisationsverwaltung und Sicherheitsleseprogramm in der EAC zugewiesen.
    
- Ihnen muss die Rolle View-Only DLP Compliance Management im Security & Compliance Center zugewiesen werden, um DLP-Berichte im Security & Compliance Center anzeigen zu können. Diese Rolle wird standardmäßig den Rollengruppen Complianceadministrator, Organisationsverwaltung, Sicherheitsadministrator und Sicherheitsleseprogramm im Security & Compliance Center zugewiesen.

- Darüber hinaus muss Ihnen die Rolle View-Only Empfänger in der EAC zugewiesen werden, um DLP-Berichte in der EAC anzeigen zu können. Diese Rolle wird standardmäßig den Rollengruppen Complianceverwaltung, Organisationsverwaltung und View-Only Organisationsverwaltung in der EAC zugewiesen.
  
 **So öffnen Sie die Seite Berichte anzeigen im Security & Compliance Center:**
  
1. Wechseln Sie zu [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto in Ihrer Organisation an.
    
Auf der **Seite Berichte anzeigen** können Sie die folgenden Typen von Berichten anzeigen: 
  
- [Überwachungsberichte](#auditing-reports)
- [Aufsichtsüberprüfungsbericht](#supervisory-review-report)
- [Berichte zur Verhinderung von Datenverlust](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Überwachungsberichte

In der folgenden Tabelle werden die Berichte im Abschnitt **Überwachung** auf der Seite Berichte **anzeigen** im Security & Compliance Center beschrieben. 
  
|**Bericht**|**Beschreibung**|
|:-----|:-----|
|**Überwachungsprotokollbericht** <br/> |Sie können das Überwachungsprotokoll nach Benutzer- und Administratoraktivitäten in Ihrer Organisation durchsuchen. Der Bericht enthält Einträge der Benutzer- und Administratoraktivitäten in Exchange Online, SharePoint Online, OneDrive for Business und Azure Active Directory, dem Verzeichnisdienst für Office 365. Weitere Informationen finden Sie [unter Durchsuchen des Überwachungsprotokolls in Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Azure AD-Berichte** <br/> |Um nach ungewöhnlichen oder verdächtigen Anmeldeaktivitäten in Ihrer Organisation zu suchen, können Sie Anmelde- und Aktivitätsberichte in Microsoft Azure verwenden. Sie können ereignisse auch im Azure AD-Überwachungsprotokoll anzeigen. Klicken Sie zum Anzeigen von Berichten in Azure einfach **auf Azure AD-Berichte anzeigen.** Weitere Informationen finden Sie unter: <br/><br/>[Verwenden Sie Ihr kostenloses Azure Active Directory-Abonnement in Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Zeigen Sie Ihre Zugriffs- und Verwendungsberichte an.](/azure/active-directory/reports-monitoring/overview-reports)  <br/> |
|**Exchange-Überwachungsberichte** <br/> | Sie können die Überwachungsfunktionalität in Microsoft 365 verwenden, um Änderungen nachverfolgt zu werden, die von den Administratoren Ihrer Organisation an Ihrer Exchange Online-Konfiguration vorgenommen wurden. Änderungen, die von einem Microsoft Data Center-Administrator oder einem delegierten Administrator an Ihrer Exchange Online-Organisation vorgenommen wurden, werden ebenfalls protokolliert. Für Exchange Online ist die Administrator-Überwachungsprotokollierung standardmäßig aktiviert, sodass Sie nichts tun müssen, um sie zu aktivieren. Exchange Online bietet auch die Postfach-Überwachungsprotokollierung, mit der Sie den Zugriff auf Postfächer von einer anderen Person als dem Postfachbesitzer nachverfolgen können. Die Postfachüberwachungsprotokollierung muss für jedes Postfach aktiviert werden, für das Sie den Zugriff durch Nicht-Besitzer nachverfolgen möchten.  <br/>  Für die Administrator- und Postfach-Überwachungsprotokollierung können Sie Überwachungsberichte ausführen, um die Überwachungsprotokolleinträge anzeigen zu können. Sie können auch Postfach- und Administrator-Überwachungsprotokolle exportieren, die ihnen innerhalb von 24 Stunden in einer XML-Datei gesendet werden, die an eine E-Mail-Nachricht angefügt ist. <br/><br/>Weitere Informationen zum Exportieren von Überwachungsprotokollen finden Sie unter:  <br/><br/> [Exportieren von Postfachüberwachungsprotokollen](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [Anzeigen und Exportieren des Überwachungsprotokolls des Rechenzentrumsadministrators](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [Durchsuchen der Rollengruppenänderungen oder Administratorüberwachungsprotokolle](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Exchange-Überwachungsberichte](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).  <br/> |
   
## <a name="supervisory-review-report"></a>Aufsichtsüberprüfungsbericht

Mit dem Aufsichtsbericht können Sie den Status aller Aufsichtsüberprüfungsrichtlinien in Ihrer Organisation anzeigen. Weitere Informationen finden Sie unter [Configure supervisory review policies for your organization](./communication-compliance-configure.md).
  
## <a name="data-loss-prevention-reports"></a>Berichte zur Verhinderung von Datenverlust

Berichte zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) enthalten Informationen zu den auf Inhalte angewendeten DLP-Richtlinien und -Regeln, die vertrauliche Daten in Ihrer Organisation enthalten. Sie können diese Berichte auch so konfigurieren, dass sie Informationen über DLP-Aktionen anzeigen, die auf Ihren DLP-Richtlinien und -Regeln basieren. Weitere Informationen finden Sie unter [View the report for data loss prevention](view-the-dlp-reports.md).