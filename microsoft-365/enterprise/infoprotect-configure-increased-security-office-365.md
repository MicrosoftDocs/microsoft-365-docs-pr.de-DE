---
title: 'Schritt 3: Konfigurieren der erhöhten Sicherheit für Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der erhöhten Sicherheit für Office 365, einschließlich Office 365 ATP.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868085"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>Schritt 3: Konfigurieren der erhöhten Sicherheit für Office 365

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Um sicherzustellen, dass Ihr Office 365-Abonnement und die darin enthaltenen Daten vor böswilligen Angriffen geschützt sind, lesen Sie die Informationen unter [Konfigurieren Ihres Office 365-Mandanten für erhöhte Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355), und konfigurieren Sie die folgende zusätzliche Sicherheit:

- Richtlinien für die Bedrohungsverwaltung im Office 365 Security & Compliance Center
- Zusätzliche mandantenweite Exchange Online-Einstellungen
- Mandantenweite Freigaberichtlinien im SharePoint Admin Center
- Azure Active Directory-Einstellungen

Nachdem Sie diese konfiguriert haben, können Sie Informationen zu Ihrem Sicherheitsstatus abrufen von:

- Dashboards und Berichte im Security & Compliance Center
- [Office 365 Secure Score](https://securescore.office.com/)
 
  Um auf diese Seite zugreifen zu können, müssen Sie als Office 365-Mandantenadministrator angemeldet sein.

Sie können Cloud App Security oder Office 365 Cloud App Security auch zur Überwachung von Sicherheitsvorfällen verwenden. Weitere Informationen finden Sie unter [Übersicht über Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).

Ein zusätzliches Sicherheitsfeature ist Office 365 Advanced Threat Protection (ATP), mit dem Ihre Organisation sicherer zusammenarbeiten kann, indem:

- Links und Anlagen in E-Mails geschützt werden. 
- Spoofintelligenz und Anti-Phishing-Funktionen für E-Mails in Exchange Online und Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams bereitgestellt wird. 

>[!Note]
>Office 365 ATP ist im Lieferumfang von Microsoft 365 Enterprise E5 enthalten. Wenn Sie über Microsoft 365 Enterprise E3 verfügen, können Sie einzelne Lizenzen für ATP erwerben.
>

Informationen zum Aktivieren von Office 365 ATP finden Sie unter [Aktivieren](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Konfigurieren der erhöhten Sicherheit von Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Konfigurieren von Privileged Access Management](infoprotect-configure-privileged-access-management.md)|


