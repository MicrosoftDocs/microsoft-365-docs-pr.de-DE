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
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 'Verwenden Sie das Security & Compliance Center, um verschiedene Berichte für Ihre SharePoint Online und Exchange Online Organisation sowie Azure Active Directory-Berichte zu erhalten.  '
ms.openlocfilehash: 2199c84673e20e338cd2a475de5aae9bb344f032
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621327"
---
# <a name="reports-in-the-security--compliance-center"></a>Berichte im Security & Compliance Center

Sie können die Seite **Berichte anzeigen** im Security & Compliance Center verwenden, um schnell auf Überwachungsberichte für Ihre SharePoint Online und Exchange Online Organisationen zuzugreifen. Sie können auf der Seite **Berichte anzeigen** auch auf Azure Active Directory (AD)-Benutzeranmelde Berichte, Benutzer Aktivitätsberichte und das Azure AD Überwachungsprotokoll zugreifen. Dies liegt daran, dass Ihr bezahltes Microsoft 365-Abonnement ein kostenloses Abonnement für Microsoft Azure enthält. Wenn Sie erstmals versuchen, auf diese Azure-Berichte zuzugreifen, müssen Sie einen einmaligen Registrierungsvorgang abschließen. 
  
> [!TIP]
> Weitere Berichte zu Aktivitäten in Ihrer Organisation finden Sie unter [Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Bevor Sie beginnen:**
  
Zum Anzeigen von Berichten im Security & Compliance Center benötigen Sie die folgenden Berechtigungen.
  
- Sie müssen die Rolle Sicherheits Leser in der Exchange-Verwaltungskonsole (EAC) erhalten, um Berichte im Security & Compliance Center anzuzeigen. Diese Rolle wird standardmäßig der Rollengruppe Organisationsverwaltung und Sicherheits Leser in der Exchange-Verwaltungskonsole zugewiesen.
    
- Sie müssen im Security & Compliance Center die Verwaltungsrolle "DLP-Compliance-Verwaltung anzeigen" zugewiesen sein, um DLP-Berichte im Security & Compliance Center anzuzeigen. Diese Rolle wird standardmäßig den Rollengruppen Compliance-Administrator, Organisationsverwaltung, Sicherheitsadministrator und Sicherheits Leser im Security & Compliance Center zugewiesen.

- Darüber hinaus müssen Sie in der Exchange-Verwaltungskonsole die Rolle "View-Only Recipients" besitzen, um DLP-Berichte in der Exchange-Verwaltungskonsole anzuzeigen. Diese Rolle wird standardmäßig den Verwaltungsrollengruppen "Verwaltung der Richtlinientreue", "Organisationsverwaltung" und "nur anzeigen" in der Exchange-Verwaltungskonsole zugewiesen.
  
 **So öffnen Sie die Seite "Berichte anzeigen" im Security & Compliance Center:**
  
1. Wechseln Sie zu [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto in Ihrer Organisation an.
    
Auf der Seite **Berichte anzeigen** können Sie die folgenden Berichtstypen anzeigen: 
  
- [Überwachungsberichte](#auditing-reports)
- [Aufsichts Überprüfungsbericht](#supervisory-review-report)
- [Berichte zur Verhinderung von Datenverlust](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Überwachungsberichte

In der folgenden Tabelle werden die Berichte im Abschnitt " **Überwachung** " auf der Seite " **Berichte anzeigen** " im Security & Compliance Center beschrieben. 
  
|**Bericht**|**Beschreibung**|
|:-----|:-----|
|**Überwachungsprotokollbericht** <br/> |Sie können das Überwachungsprotokoll nach Benutzer-und Administratoraktivitäten in Ihrer Organisation durchsuchen. Der Bericht enthält Einträge Benutzer-und Administratoraktivitäten in Exchange Online, SharePoint Online, OneDrive für Unternehmen und Azure Active Directory, bei dem es sich um den Verzeichnisdienst für Office 365 handelt. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Azure AD-Berichte** <br/> |Um nach ungewöhnlichen oder verdächtigen Anmeldeaktivitäten in Ihrer Organisation zu suchen, können Sie Anmelde-und Aktivitätsberichte in Microsoft Azure verwenden. Sie können auch Ereignisse im Azure AD Überwachungsprotokoll anzeigen. Zum Anzeigen von Berichten in Azure klicken Sie einfach auf **Azure AD Berichte anzeigen**. Weitere Informationen finden Sie unter: <br/><br/>[Verwenden Sie Ihr kostenloses Azure Active Directory-Abonnement in Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Zeigen Sie Ihre Zugriffs-und Verwendungsberichte](https://go.microsoft.com/fwlink/p/?LinkId=506902)an.  <br/> |
|**Exchange-Überwachungsberichte** <br/> | Sie können die Überwachungsfunktionalität in Microsoft 365 verwenden, um Änderungen nachzuverfolgen, die von den Administratoren Ihrer Organisation an Ihrer Exchange Online Konfiguration vorgenommen wurden. Änderungen, die von einem Microsoft Data Center-Administrator oder von einem Delegierten Administrator an Ihrer Exchange Online Organisation vorgenommen wurden, werden ebenfalls protokolliert. Für Exchange Online ist die Administrator-Überwachungsprotokollierung standardmäßig aktiviert, sodass Sie keine Aktionen ausführen müssen, um Sie zu aktivieren. Exchange Online bietet auch die postfachüberwachungsprotokollierung, damit Sie den Zugriff auf Postfächer von einem anderen als dem Postfachbesitzer nachverfolgen können. Die Postfachüberwachungsprotokollierung muss für jedes Postfach aktiviert werden, für das Sie den Zugriff durch Nicht-Besitzer nachverfolgen möchten.  <br/>  Sowohl für die Administrator-als auch für die postfachüberwachungsprotokollierung können Sie Überwachungsberichte ausführen, um die Überwachungsprotokolleinträge anzuzeigen. Sie können auch Post Fach-und Administratorüberwachungsprotokolle exportieren, die Ihnen innerhalb von 24 Stunden in einer XML-Datei gesendet werden, die an eine e-Mail-Nachricht angefügt ist. <br/><br/>Weitere Informationen zum Exportieren von Überwachungsprotokollen finden Sie unter:  <br/><br/> [Exportieren von Postfachüberwachungsprotokollen](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Anzeigen und Exportieren des Überwachungsprotokolls des Datencenter-Administrators](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Durchsuchen der Rollengruppenänderungen oder Administratorüberwachungsprotokolle](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange-Überwachungsberichte](https://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Aufsichts Überprüfungsbericht

Mit dem Bericht über Aufsichts Überprüfungen können Sie den Status aller Aufsichts Überprüfungsrichtlinien in Ihrer Organisation anzeigen. Weitere Informationen finden Sie unter [Konfigurieren von Aufsichts Überprüfungsrichtlinien für Ihre Organisation](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Berichte zur Verhinderung von Datenverlust

DLP-Berichte (Data Loss Prevention) enthalten Informationen zu den DLP-Richtlinien und-Regeln, die auf Inhalte angewendet wurden, die vertrauliche Daten in Ihrer Organisation enthalten. Sie können diese Berichte auch so konfigurieren, dass sie Informationen über DLP-Aktionen anzeigen, die auf Ihren DLP-Richtlinien und -Regeln basieren. Weitere Informationen finden Sie unter [Anzeigen des Berichts zur Verhinderung von Datenverlust](view-the-dlp-reports.md).
