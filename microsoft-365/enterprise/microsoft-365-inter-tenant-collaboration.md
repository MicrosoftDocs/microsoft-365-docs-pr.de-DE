---
title: Microsoft 365 mandantenübergreifende Zusammenarbeit
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Erfahren Sie, wie Microsoft 365 Zusammenarbeit zwischen Mandanten und Organisationen funktioniert, sodass unterschiedliche Organisationen sicher zusammenarbeiten können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0a9d15608e046e72ba579b77ba44092ed2ecb46
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229851"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 mandantenübergreifende Zusammenarbeit

Angenommen, zwei Organisationen, Fabrikam und Contoso, verfügen jeweils über einen Microsoft 365 für Geschäftsmandanten und möchten an mehreren Projekten zusammenarbeiten. einige davon werden für einen begrenzten Zeitraum ausgeführt, und einige davon werden ausgeführt. Wie können Fabrikam und Contoso ihren Mitarbeitern und Teams ermöglichen, auf sichere Weise effektiver in ihren verschiedenen Microsoft 365 Mandanten zusammenzuarbeiten? Microsoft 365 bietet in Verbindung mit Azure Active Directory (Azure AD) B2B-Zusammenarbeit verschiedene Optionen. In diesem Artikel werden einige wichtige Szenarien beschrieben, die Fabrikam und Contoso in Betracht ziehen können.

Microsoft 365 Optionen für die mandantenübergreifende Zusammenarbeit umfassen die Verwendung eines zentralen Orts für Dateien und Unterhaltungen, das Freigeben von Kalendern, die Verwendung von Chats, Audio-/Videoanrufe für die Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen. In den folgenden Tabellen können Sie Lösungen auswählen und auf weitere Informationen zugreifen.

## <a name="exchange-online-collaboration-options"></a>Optionen für die Zusammenarbeit in Exchange Online

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Freigeben von Kalendern für eine andere Microsoft 365 Organisation |Administratoren können unterschiedliche Ebenen des Kalenderzugriffs in Exchange Online einrichten, damit Unternehmen mit anderen Unternehmen zusammenarbeiten können und Benutzer die Zeitpläne (Frei/Gebucht-Informationen) für andere freigeben können. | <ul><li>[Freigabe](/exchange/sharing/sharing) </li><li> [Organisationsbeziehungen](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Erstellen einer Organisationsbeziehung](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Ändern einer Organisationsbeziehung](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Entfernen einer Organisationsbeziehung](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Freigeben von Kalendern für externe Benutzer](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Steuern, wie Benutzer ihre Kalender für Personen außerhalb Ihrer Organisation freigeben können | Administratoren wenden Freigaberichtlinien auf Postfächer von Benutzern an, um zu steuern, für welche Personen diese freigegeben und welche Zugriffsebene erteilt werden kann. |  <ul><li> [Freigaberichtlinien](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Erstellen einer Freigaberichtlinie](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Anwenden von Freigaberichtlinien für Postfächer](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Ändern, Deaktivieren oder Entfernen einer Freigaberichtlinie](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Konfigurieren sicherer E-Mail-Kanäle und Steuern des Nachrichtenflusses mit Partnerorganisationen | Administratoren erstellen Connectors, um Sicherheit auf den E-Mail-Austausch mit einer Partnerorganisation oder einem Dienstanbieter anzuwenden. Die Connectors erzwingen Verschlüsselung über TLS (Transport Layer Security) und ermöglichen Einschränkungen für Domänennamen oder IP-Adressbereiche, von denen die Partner E-Mails senden können. |  <ul><li> [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [Konfigurieren des Nachrichtenflusses mit Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Remotedomänen](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Einrichten von Connectors für sicheren Nachrichtenfluss mit einer Partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Bewährte Methoden für den Nachrichtenfluss (Übersicht)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Optionen für die Zusammenarbeit in SharePoint Online und OneDrive for Business

| Freigabeziele | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Freigeben von Websites und Dokumenten für externe Benutzer | Administratoren konfigurieren die Freigabe auf Mandantenebene oder auf Websitesammlungsebene für authentifizierte Microsoft-Konten, authentifizierte Geschäfts-, Schul- oder Unikonten oder Gastkonten. |  <ul><li> [Verwalten der externen Freigabe für Ihre SharePoint-Online-Umgebung](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](/sharepoint/restricted-domains-sharing) </li><li> [Verwenden von SharePoint Online als Business-to-Business-Extranetlösung](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Nachverfolgen und Steuern der externen Freigabe für Endbenutzer | OneDrive for Business-Dateibesitzer und SharePoint Online-Endbenutzer konfigurieren die Freigabe von Websites und Dokumenten und richten Benachrichtigungen zum Nachverfolgen der Freigabe ein. |  <ul><li> [Konfigurieren von Benachrichtigungen für externe Freigaben für OneDrive for Business](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Freigeben von SharePoint-Dateien oder -Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Optionen für die Zusammenarbeit in Skype for Business

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Skype for Business Online – Chatnachrichten, Anrufe und Anwesenheitsinformationen für andere Skype for Business-Benutzer | Administratoren können ihren Skype for Business Onlinebenutzern die Möglichkeit geben, Chatnachrichten zu tätigen, Audio-/Videoanrufe zu tätigen und Anwesenheitsinformationen für Benutzer in einem anderen Microsoft 365 Mandanten anzuzeigen. | [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype for Business Online – Chatnachrichten, Anrufe und Anwesenheitsinformationen für Skype-Benutzer (Privatkunden) | Administratoren können für Skype for Business Online-Benutzer Chatnachrichten, Anrufe und die Anzeige von Anwesenheitsinformationen für Skype-Benutzer (Privatkunden) aktivieren. | [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Optionen für die Zusammenarbeit in Azure Active Directory B2B

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Azure Active Directory B2B-Zusammenarbeit – Inhaltsfreigabe durch Hinzufügen externer Benutzer zu einer Gruppe im Verzeichnis einer Organisation | Ein globaler Administrator für einen Microsoft 365 Mandanten kann Personen in einem anderen Microsoft 365 Mandanten einladen, ihrem Verzeichnis beizutreten, diese externen Benutzer einer Gruppe hinzuzufügen und Zugriff auf Inhalte zu gewähren, z. B. SharePoint Websites und Bibliotheken für die Gruppe. |  <ul><li> [Informationen zur Vorschau der Azure AD B2B-Zusammenarbeit](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure Active Directory B2B: Neue Updates erleichtern die unternehmensübergreifende Zusammenarbeit](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Externe Freigabe und Azure Active Directory B2B-Zusammenarbeit](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B-Zusammenarbeit: API und Anpassung](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD und Identity Show: Azure AD B2B-Zusammenarbeit (Business-to-Business)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Optionen für die Microsoft 365 Zusammenarbeit

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Microsoft 365 Gruppen – E-Mail, Kalender, OneNote und freigegebene Dateien an einem zentralen Ort | Gruppen werden in Business Essentials und Business Premium sowie den Plänen Enterprise E1, E3 und E5 unterstützt. Personen in einem Microsoft 365 Mandanten können eine Gruppe erstellen und Personen in einem anderen Microsoft 365 Mandanten als Gastbenutzer einladen. Dies gilt auch für Dynamics CRM. |  <ul><li> [Informationen zu Microsoft 365-Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Bereitstellen von Microsoft 365-Gruppen](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Optionen für die Zusammenarbeit in Yammer

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Yammer – Zusammenarbeit über ein soziales Medium des Unternehmens | Sofern die Möglichkeit zum Erstellen externer Gruppen nicht vom Yammer-Administrator deaktiviert wird, können Benutzer externe Gruppen für die Zusammenarbeit in Yammer über Unterhaltungen, die Möglichkeit zum Bewerten und Folgen für Beiträge, das Freigeben von Dateien und Onlinechats erstellen. | [Erstellen und Verwalten von externen Gruppen in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Optionen für die Zusammenarbeit in Teams

|Freigabeziel|Administratoraktion|Informationen zur Vorgehensweise|
|:-----|:-----|:-----|
|Zusammenarbeit in Teams Benutzern außerhalb Ihrer Organisation | Ein globaler Administrator für die einladende Microsoft 365 Mandanten muss die externe Zusammenarbeit in Teams ermöglichen. Globale Administratoren und Teambesitzer können nun jeden Gast, der über eine E-Mail-Adresse verfügt, einladen, um in Teams zusammenzuarbeiten.  <br/> Administratoren können auch bereits in Ihrem Mandanten vorhandene Gäste verwalten und bearbeiten. |  <ul><li> [Autorisieren des Gastzugriffs](/microsoftteams/teams-dependencies) </li><li> [Aktivieren und Deaktivieren des Gastzugriffs in Teams](/microsoftteams/set-up-guests) </li><li> [Verwenden von PowerShell zum Steuern des Gastzugriffs](/microsoftteams/guest-access-powershell) </li><li> [Checkliste für den Gastzugriff](/microsoftteams/guest-access-checklist) </li><li> [Anzeigen von Gastbenutzern](/microsoftteams/view-guests) </li><li> [Bearbeiten von Gastbenutzerinformationen](/microsoftteams/edit-guests-information) </li></ul> |
|Teambesitzer können Gäste einladen und verwalten, wie sie innerhalb Ihrer Teams mit ihnen zusammenarbeiten.  |Teambesitzer haben außerdem Kontrolle darüber, was die Gäste in ihren Teams tun können. |  <ul><li> [Hinzufügen von Gästen](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Hinzufügen eines Gasts zu einem Team](/microsoftteams/add-guests) </li><li> [Verwalten des Gastzugriffs in Microsoft Teams](/microsoftteams/manage-guests) </li><li> [Anzeigen, wer in einem Team oder Kanal ist](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gäste anderer Mandanten können Inhalte in Teams anzeigen und mit anderen Mitgliedern zusammenarbeiten. | Keine. | [Gastzugriff](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Optionen für die Zusammenarbeit in Power BI

| Freigabeziel | Administratoraktion | Informationen zur Vorgehensweise |
|:-----|:-----|:-----|
|Power BI ermöglicht externen Gastbenutzern, über Links freigegebene Inhalte zu nutzen. Dies ermöglicht es Benutzern, Inhalte auf sichere Art und Weise über Organisationsgrenzen hinweg zu verteilen.<br/> | Der Power BI-Administrator kann steuern, ob Benutzer externe Benutzer einladen können, Inhalte von innerhalb der Organisation anzuzeigen.| [Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure Active Directory B2B](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Punkte, die Sie über Microsoft 365 mandantenübergreifende Zusammenarbeit beachten sollten

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Gemeinsame Nutzung (Freigabe) von Benutzerkonten, Lizenzen, Abonnements und Speicher

Jede Organisation verwalte ihre eigenen Benutzerkonten, Identitäten, Sicherheitsgruppen, Abonnements, Lizenzen und Speicher. Personen verwenden die Features für die Zusammenarbeit in Microsoft 365 zusammen mit Freigaberichtlinien und Sicherheitseinstellungen, um Zugriff auf benötigte Informationen bereitzustellen und gleichzeitig die Kontrolle über die Unternehmensressourcen zu behalten.

- **Benutzerkonten:** Konten können nicht zwischen den Mandanten oder Partitionen in den lokalen Active Directory-Domänendiensten freigegeben oder dupliziert werden.

- **&amp; Lizenzabonnements:** In Microsoft 365 gewähren Lizenzen aus Lizenzierungsplänen (auch als SKUs oder Microsoft 365-Pläne bezeichnet) Benutzern Zugriff auf die Microsoft 365 Dienste, die für diese Pläne definiert sind.

- **Storage:** In Microsoft 365 Lizenzierungsplänen werden Softwarebeschränkungen und -beschränkungen für SharePoint Online separat von Postfachspeichergrenzwerten verwaltet. Speicherbegrenzungen für Postfächer werden mit Exchange Online eingerichtet und verwaltet. In beiden Szenarien kann der Speicher nicht mandantenübergreifend freigegeben werden.

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Können Domänennamespaces für Microsoft 365 Mandanten gemeinsam verwendet werden?

Nein. Organisationsdomänennamen, z. B. fabrikam.com oder tailspintoys.com, können nur einem einzelnen Microsoft 365 Mandanten zugeordnet und verwendet werden. Jeder Mandant muss über einen eigenen Namespace verfügen. UPN-, SMTP- und SIP-Namespaces können nicht mandantenübergreifend verwendet werden.

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Wie sieht es mit Hybridkomponenten und Microsoft 365 mandantenübergreifenden Zusammenarbeit aus?

Lokale Hybridkomponenten, z. B. eine Exchange-Organisation und Azure AD Connect, können nicht auf mehrere Mandanten aufgeteilt werden.
