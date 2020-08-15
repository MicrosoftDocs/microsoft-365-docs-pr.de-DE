---
title: Microsoft 365 Zusammenarbeit zwischen Mandanten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/08/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Microsoft 365-Zusammenarbeit in Mandanten und Organisationen funktioniert, sodass verschiedene Organisationen sicher zusammenarbeiten können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529d4a320fe9aefa5d1ddfbac56742991dbd732d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690623"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 Zusammenarbeit zwischen Mandanten

In diesem Artikel werden mehrere Möglichkeiten zur Zusammenarbeit zwischen zwei Microsoft 365-Mandanten beschrieben. Sie richtet sich an Microsoft 365-Administratoren.
  
Angenommen, zwei Organisationen, Fabrikam und Contoso, verfügen jeweils über einen Microsoft 365 for Business-Mandanten und möchten an mehreren Projekten zusammenarbeiten; Einige davon werden für eine bestimmte Zeit ausgeführt, von denen einige fortlaufend sind. Wie können Fabrikam und Contoso Ihre Mitarbeiter und Teams in die Lage versetzen, effektiver in ihren verschiedenen Microsoft 365-Mandanten auf sichere Weise zusammenzuarbeiten? Microsoft 365 bietet zusammen mit Azure Active Directory B2B-Zusammenarbeit mehrere Optionen. In diesem Artikel werden einige wichtige Szenarien beschrieben, die Fabrikam und Contoso in Betracht ziehen können.
  
Microsoft 365 intertenant-Zusammenarbeitsoptionen umfassen die Verwendung eines zentralen Speicherorts für Dateien und Unterhaltungen, das Freigeben von Kalendern, das Verwenden von Chatnachrichten, Audio-und Videoanrufe zur Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen. In den folgenden Tabellen können Sie Lösungen auswählen und auf weitere Informationen zugreifen.
  
## <a name="exchange-online-collaboration-options"></a>Optionen für die Zusammenarbeit in Exchange Online

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Freigeben von Kalendern für eine andere Microsoft 365-Organisation  <br/> |Administratoren können verschiedene Ebenen des Kalenderzugriffs in Exchange Online einrichten, sodass Unternehmen mit anderen Unternehmen zusammenarbeiten und die Benutzer Terminpläne (Frei/Gebucht-Informationen) für andere Personen freigeben können.  <br/> |[Freigabe in Exchange Online](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) <br/> [Organisationsbeziehungen in Exchange Online](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) <br/> [Erstellen einer Organisationsbeziehung in Exchange Online](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) <br/> [Ändern einer Organisationsbeziehung in Exchange Online](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) <br/> [Entfernen einer Organisationsbeziehung in Exchange Online](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) <br/> [Freigeben von Kalendern für externe Benutzer](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) <br/> |
|Steuern, wie Benutzer ihre Kalender für Personen außerhalb Ihrer Organisation freigeben können  <br/> |Administratoren wenden Freigaberichtlinien auf Postfächer von Benutzern an, um zu steuern, für welche Personen diese freigegeben und welche Zugriffsebene erteilt werden kann.  <br/> |[Freigaberichtlinien in Exchange Online](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) <br/> [Erstellen einer Freigaberichtlinie in Exchange Online](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) <br/> [Anwenden von Freigaberichtlinien auf Postfächer in Exchange Online](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) <br/> [Ändern, Deaktivieren oder Entfernen einer Freigaberichtlinie in Exchange Online](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) <br/> |
|Konfigurieren sicherer E-Mail-Kanäle und Steuern des Nachrichtenflusses mit Partnerorganisationen  <br/> |Administratoren erstellen Connectors, um Sicherheit auf den E-Mail-Austausch mit einer Partnerorganisation oder einem Dienstanbieter anzuwenden. Die Connectors erzwingen Verschlüsselung über TLS (Transport Layer Security) und ermöglichen Einschränkungen für Domänennamen oder IP-Adressbereiche, von denen die Partner E-Mails senden können.  <br/> |[Wie Exchange Online TLS zum Sichern von e-Mail-Verbindungen verwendet](https://technet.microsoft.com/library/mt163898.aspx) <br/> [Konfigurieren des Nachrichtenflusses mit Connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) <br/> [Remotedomänen in Exchange Online](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) <br/> [Einrichten von Connectors für sicheren Nachrichtenfluss mit einer Partnerorganisation](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) <br/> [Bewährte Methoden für den Nachrichtenfluss für Exchange Online (Übersicht)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) <br/> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Optionen für die Zusammenarbeit in SharePoint Online und OneDrive for Business

|**Freigabeziele**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Freigeben von Websites und Dokumenten für externe Benutzer  <br/> |Administratoren konfigurieren die Freigabe auf Mandantenebene oder auf Websitesammlungsebene für authentifizierte Microsoft-Konten, authentifizierte Geschäfts-, Schul- oder Unikonten oder Gastkonten.  <br/> |[Verwalten der externen Freigabe für Ihre SharePoint-Online-Umgebung](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> [Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) <br/> [Verwenden von SharePoint Online als Business-to-Business-Extranetlösung](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) <br/> |
|Nachverfolgen und Steuern der externen Freigabe für Endbenutzer  <br/> |OneDrive for Business-Dateibesitzer und SharePoint Online-Endbenutzer konfigurieren die Freigabe von Websites und Dokumenten und richten Benachrichtigungen zum Nachverfolgen der Freigabe ein.  <br/> |[Konfigurieren von Benachrichtigungen für externe Freigaben für OneDrive for Business](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) <br/> [Freigeben von SharePoint-Dateien oder -Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) <br/> |
   
## <a name="skype-for-business-collaboration-options"></a>Optionen für die Zusammenarbeit in Skype for Business

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Skype for Business Online – Chatnachrichten, Anrufe und Anwesenheitsinformationen für andere Skype for Business-Benutzer  <br/> |Administratoren können Ihren Skype for Business Online-Benutzern das Chatten ermöglichen, Audio-und Videoanrufe tätigen und die Anwesenheitsinformationen für Benutzer in einem anderen Microsoft 365-Mandanten anzeigen.  <br/> |[Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94) <br/> |
|Skype for Business Online – Chatnachrichten, Anrufe und Anwesenheitsinformationen für Skype-Benutzer (Privatkunden)  <br/> |Administratoren können für Skype for Business Online-Benutzer Chatnachrichten, Anrufe und die Anzeige von Anwesenheitsinformationen für Skype-Benutzer (Privatkunden) aktivieren.  <br/> |[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460) <br/> |
   
## <a name="azure-ad-b2b-collaboration-options"></a>Optionen für die Zusammenarbeit in Azure Active Directory B2B

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Azure Active Directory B2B-Zusammenarbeit – Inhaltsfreigabe durch Hinzufügen externer Benutzer zu einer Gruppe im Verzeichnis einer Organisation  <br/> |Ein globaler Administrator für einen Microsoft 365-Mandanten kann Personen in einem anderen Microsoft 365-Mandanten zur Teilnahme an Ihrem Verzeichnis einladen, diese externen Benutzer zu einer Gruppe hinzufügen und Zugriff auf Inhalte wie SharePoint-Websites und-Bibliotheken für die Gruppe gewähren.  <br/> |[Informationen zur Vorschau der Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) <br/> [Azure Active Directory B2B: Neue Updates erleichtern die unternehmensübergreifende Zusammenarbeit](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) <br/> [Externe Freigabe und Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) <br/> [Azure Active Directory B2B-Zusammenarbeit: API und Anpassung](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) <br/> [Azure AD und Identity Show: Azure AD B2B-Zusammenarbeit (Business-to-Business)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) <br/> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365-Zusammenarbeitsoptionen

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Microsoft 365 Gruppen – e-Mail, Kalender, OneNote und freigegebene Dateien an zentraler Stelle  <br/> |Gruppen werden in Business Essentials und Business Premium sowie den Plänen Enterprise E1, E3 und E5 unterstützt. Personen in einem Microsoft 365-Mandanten können eine Gruppe erstellen und Personen in einem anderen Microsoft 365-Mandanten als Gastbenutzer einladen. Dies gilt auch für Dynamics CRM.  <br/> |[Informationen zu Microsoft 365-Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br/> [Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) <br/> [Bereitstellen von Microsoft 365-Gruppen](https://technet.microsoft.com/library/dn896591.aspx) <br/> |
   
## <a name="yammer-collaboration-options"></a>Optionen für die Zusammenarbeit in Yammer

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Yammer – Zusammenarbeit über ein soziales Medium des Unternehmens  <br/> |Sofern die Möglichkeit zum Erstellen externer Gruppen nicht vom Yammer-Administrator deaktiviert wird, können Benutzer externe Gruppen für die Zusammenarbeit in Yammer über Unterhaltungen, die Möglichkeit zum Bewerten und Folgen für Beiträge, das Freigeben von Dateien und Onlinechats erstellen.  <br/> |[Erstellen und Verwalten von externen Gruppen in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a) <br/> |
   
## <a name="teams-collaboration-options"></a>Optionen für die Zusammenarbeit in Teams

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Zusammenarbeit in Teams Benutzern außerhalb Ihrer Organisation  <br/> |Ein globaler Administrator für den einladenden Microsoft 365-Mandanten muss die externe Zusammenarbeit in Teams aktivieren. Globale Administratoren und Teambesitzer können nun jeden Gast, der über eine E-Mail-Adresse verfügt, einladen, um in Teams zusammenzuarbeiten.  <br/> Administratoren können auch bereits in Ihrem Mandanten vorhandene Gäste verwalten und bearbeiten.  <br/> |[Autorisieren des Gastzugriffs](https://docs.microsoft.com/microsoftteams/teams-dependencies) <br/> [Aktivieren und Deaktivieren des Gastzugriffs in Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) <br/> [Verwenden von PowerShell zum Steuern des Gastzugriffs](https://docs.microsoft.com/microsoftteams/guest-access-powershell) <br/> [Checkliste für den Gastzugriff](https://docs.microsoft.com/microsoftteams/guest-access-checklist) <br/> [Anzeigen von Gastbenutzern](https://docs.microsoft.com/microsoftteams/view-guests) <br/> [Bearbeiten von Gastbenutzerinformationen](https://docs.microsoft.com/microsoftteams/edit-guests-information) <br/> |
|Teambesitzer können Gäste einladen und verwalten, wie sie innerhalb Ihrer Teams mit ihnen zusammenarbeiten.  <br/> |Teambesitzer haben außerdem Kontrolle darüber, was die Gäste in ihren Teams tun können.  <br/> |[Hinzufügen von Gästen](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) <br/> [Hinzufügen eines Gasts zu einem Team](https://docs.microsoft.com/microsoftteams/add-guests) <br/> [Verwalten des Gastzugriffs in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-guests) <br/> [Anzeigen, wer in einem Team oder Kanal ist](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> |
|Gäste anderer Mandanten können Inhalte in Teams anzeigen und mit anderen Mitgliedern zusammenarbeiten.  <br/> |Keine.  <br/> |[Gastzugriff](https://docs.microsoft.com/microsoftteams/guest-experience) <br/> |

## <a name="power-bi-collaboration-options"></a>Optionen für die Zusammenarbeit in Power BI

|**Freigabeziel**|**Administratoraktion**|**Informationen zur Vorgehensweise**|
|:-----|:-----|:-----|
|Power BI ermöglicht externen Gastbenutzern, über Links freigegebene Inhalte zu nutzen. Dies ermöglicht es Benutzern, Inhalte auf sichere Art und Weise über Organisationsgrenzen hinweg zu verteilen.<br/> | Der Power BI-Administrator kann steuern, ob Benutzer externe Benutzer einladen können, Inhalte von innerhalb der Organisation anzuzeigen. <br/> |[Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure Active Directory B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) <br/> |
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Hinweise zur Zusammenarbeit zwischen Mandanten in Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Gemeinsame Nutzung (Freigabe) von Benutzerkonten, Lizenzen, Abonnements und Speicher

Jede Organisation verwalte ihre eigenen Benutzerkonten, Identitäten, Sicherheitsgruppen, Abonnements, Lizenzen und Speicher. Personen verwenden die Features für die Zusammenarbeit in Microsoft 365 zusammen mit Freigaberichtlinien und Sicherheitseinstellungen, um Zugriff auf benötigte Informationen bereitzustellen und gleichzeitig die Kontrolle über Unternehmensressourcen beizubehalten.
  
- **Benutzerkonten:** Es ist nicht möglich, Konten zwischen den Mandanten oder Partitionen in den lokalen Active Directory-Verzeichnisdiensten freizugeben oder zu duplizieren. 
    
- **Lizenz &amp; Abonnements:** in Microsoft 365 erteilen Lizenzen aus Lizenzierungs Plänen (auch SKUs oder Microsoft 365-Pläne genannt) Benutzern den Zugriff auf die Microsoft 365-Dienste, die für diese Pläne definiert sind. 
    
- **Speicher:** In Microsoft 365-Plänen werden Softwarebeschränkungen und-Grenzwerte für SharePoint Online getrennt von Postfachspeicher Grenzen verwaltet. Speicherbegrenzungen für Postfächer werden mit Exchange Online eingerichtet und verwaltet. In beiden Fällen kann Speicher nicht von mehreren Mandanten gemeinsam genutzt werden. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Können Domänen Namespaces in Microsoft 365-Mandanten gemeinsam genutzt werden?

Nein. Benutzerdefinierte Domänen, z. B. „fabrikam.com“ oder „tailspintoys.com“, können nur jeweils einem Mandanten zugeordnet sein und von diesem verwendet werden. Jeder Mandant muss einen eigenen Namespace haben; UPN-, SMTP- und SIP-Namespaces können nicht von Mandanten gemeinsam genutzt werden.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Was ist mit Hybrid-Komponenten und Microsoft 365 Zusammenarbeit zwischen Mandanten?

Lokale Hybridkomponenten, z. B. eine Exchange-Organisation und Azure AD Connect, können nicht auf mehrere Mandanten aufgeteilt werden.
  

