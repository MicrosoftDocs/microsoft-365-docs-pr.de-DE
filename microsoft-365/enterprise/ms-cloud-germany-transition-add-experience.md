---
title: Post-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Post-Migrationsaktivitäten nach der Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) nach Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930415"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Post-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland

Die folgenden Abschnitte enthalten Post-Migrationsaktivitäten für mehrere Dienste nach dem Wechsel von Microsoft Cloud Deutschland zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD-Verbundauthentifizierung mit AD FS
**Gilt für:** Alle Kunden, die Verbundauthentifizierung mit AD FS verwenden

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen Sie Vertrauensstellungen der vertrauenden Gruppen aus Microsoft Cloud Deutschland AD FS. | Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden. An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Gruppe zu den Microsoft Cloud Deutschland-Endpunkten entfernen. Dies kann nur geschehen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte verweisen, wenn Azure AD als Identitätsanbieter (Identity Provider, IdP) verwendet wird. | Organisationen mit Verbundauthentifizierung | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Gruppengenehmigungen
**Gilt für:** Endbenutzer, deren Azure AD-Gruppengenehmigungsanforderungen nicht in den letzten 30 Tagen vor der Migration genehmigt wurden 

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Anforderungen für den Beitritt einer Azure AD-Gruppe in den letzten 30 Tagen vor der Migration müssen erneut durchgeführt werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde. | Kunden von Endbenutzern müssen den Zugriffsbereich verwenden, um erneut Anforderungen zum Beitritt zu einer Azure AD-Gruppe zu senden, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden. |  Als Endbenutzer: <ol><li>Navigieren Sie zum [Zugriffsbereich](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Suchen Sie eine Azure AD-Gruppe, für die innerhalb von 30 Tagen vor der Migration eine Mitgliedschaftsgenehmigung ausstehend war.</li><li>Fordern Sie den Beitritt zur Azure AD-Gruppe erneut an.</li></ol> Anforderungen zum Betritt zu einer Gruppe, die weniger als 30 Tage vor der Migration aktiv sind, können nicht genehmigt werden, es sei denn, sie werden nach der Migration wiederholt. |
||||

## <a name="custom-dns-updates"></a>Benutzerdefinierte DNS-Updates
**Gilt für:** Alle Kunden, die ihre eigenen DNS-Zonen verwalten

| Schritte: | Beschreibung | Auswirkung |
|:------|:-------|:-------|
| Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienstendpunkte. | Vom Kunden verwaltete DNS-Einträge, die auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365 Global-Dienstendpunkte verweisen. Bitte schlagen Sie unter [Domänen im Microsoft 365 Admin Center](https://admin.microsoft.com/Adminportal/Home#/Domains) nach und übernehmen Sie die Änderungen in Ihre DNS-Konfiguration. | Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen. |
||||

## <a name="third-party-services"></a>Drittanbieterdienste
**Gilt für:** Kunden, die Drittanbieterdienste für Office 365-Dienstendpunkte verwenden.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Aktualisieren Sie Partner und Drittanbieterdienste für Office 365-Dienstendpunkte. | <ul><li>Drittanbieterdienste und Partner, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen. Beispiel: Registrieren Sie die Galerie-App-Version der Anwendungen, falls verfügbar, in Übereinstimmung mit Ihren Anbietern und Partnern neu. </li><li>Verweisen Sie alle benutzerdefinierten Anwendungen, die die Graph-API von `graph.microsoft.de` verwenden, auf `graph.microsoft.com`. Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls sie genutzt werden. </li><li>Ändern Sie alle Unternehmensanwendungen von Drittanbietern so, dass sie zu den weltweiten Endpunkten umgeleitet werden. </li></ul>| Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Softwareclients führen. |
||||