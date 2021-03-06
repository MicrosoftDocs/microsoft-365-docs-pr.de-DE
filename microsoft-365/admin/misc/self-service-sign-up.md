---
title: Verwenden der Self-Service-Registrierung in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Erfahren Sie mehr über die Microsoft 365 Self-Service-Registrierung und verfügbare Self-Service-Programme wie Microsoft Power Apps, Microsoft Flow und Dynamics 365 for Finance.
ms.date: 03/17/2021
ms.openlocfilehash: 7aec03abce468342cfeb23da490b1f950ecd7050
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286585"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Verwenden der Self-Service-Registrierung in Ihrer Organisation

Die Self-Service-Registrierung erleichtert Benutzern in Ihrer Organisation die Registrierung für Onlinedienste von Microsoft. Wir bezeichnen diesen Registrierungsvorgang als "Self-Service-Registrierung", da sich Ihre Benutzer für die Nutzung von Diensten registrieren können, die von Ihrem Abonnement bezahlt werden, oder kostenlose Dienste nutzen können, ohne Sie zu bitten, in ihrem Namen Maßnahmen zu ergreifen.

## <a name="how-self-service-sign-up-works"></a>Funktionsweise der Self-Service-Registrierung

Im folgenden Beispiel wird beschrieben, wie die Self-Service-Registrierung für eine Schule oder Uni funktioniert. Dieser Vorgang gilt für alle Organisationen, in deren Mandanten Self-Service-Programme aktiviert sind.

1. Schüler und Studenten sowie Lehrkräfte verfügen über Schul- oder Uni-E-Mail-Adressen, die angeben, dass sie Ihrer Bildungseinrichtung zugeordnet sind. Beispielsweise kann die E-Mail-Adresse jakob@uw.edu einen Kursteilnehmer an der University of Washington angeben.
2. Studenten und Lehrkräfte wechseln zu [unserer Website](https://go.microsoft.com/fwlink/p/?LinkId=536628)und verwenden ihre E-Mail-Adresse, um sich für die Dienste zu registrieren, die Ihre Organisation anbietet, z. B. Microsoft 365 Apps for Enterprise. Sie können sich auch für andere kostenlose Dienste registrieren, die wir anbieten.
3. Wir überprüfen ihre E-Mail-Adresse und können dann sofort mit der Verwendung von Microsoft 365, Power BI oder anderen Diensten beginnen.
4. Als Geschäftsadministrator können Sie sehen, wer sich für ein Abonnement angemeldet hat, indem Sie das Abonnement auf der Seite **"Lizenzierung"** im Microsoft 365 Admin Center auswählen. Auf diese Weise können Sie sehen, ob es neue oder nicht erkannte Lizenzen für Dienste in Ihrem Mandanten gibt. Um zu steuern, ob Benutzer sich für Self-Service-Abonnements registrieren können, verwenden Sie das [PowerShell-Cmdlet "Set-MsolCompanySettings"](/powershell/module/msonline/set-msolcompanysettings) mit dem Parameter **"AllowAdHocSubscriptions".** Weitere Informationen finden Sie unter "Steuern von [Self-Service-Einstellungen"?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Verfügbare Self-Service-Programme

Im Folgenden werden die aktuell verfügbaren Self-Service-Programme aufgeführt. Diese Liste wird aktualisiert, wenn neue Programme hinzugefügt werden.

| Programm <br/> | Beschreibung <br/> | Zusätzliche Informationen <br/> | Website für die Self-Service-Registrierung <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1 <br/> |Jeder Schüler oder Lehrer kann eine E-Mail-Adresse einer Schule verwenden, um sich kostenlos Office 365 anzumelden und Office Apps für das Web, 1 TB OneDrive Cloudspeicher und SharePoint Online für Kurs-, Team- und Projektwebsites zu erhalten.  <br/> |[Self-Service-Registrierung für Office 365 Education: Häufig gestellte technische Fragen](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Berechtigte Schüler/Studenten und Lehrkräfte können sich für Office 365 A1 Plus registrieren, das alles enthält, was oben erwähnt wird, sowie Microsoft 365 Apps for Enterprise. Microsoft 365 Apps for Enterprise ist Produktivitätssoftware, einschließlich Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access und Skype for Business, die auf Ihrem Desktop- oder Laptopcomputer installiert ist.  <br/> |[Self-Service-Registrierung für Office 365 Education: Häufig gestellte technische Fragen](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI ermöglicht Benutzern, Daten zu visualisieren, Entdeckungen zu teilen und auf intuitive neue Weise zusammenzuarbeiten. <br/> Wenn Ihre Organisation bereits Abonniert hat, werden möglicherweise zusätzlich Lizenzen für "Power BI Pro Testversion einzelner Benutzer" angezeigt, die Benutzern eingeschränkten, kostenlosen Zugriff auf erweiterte Funktionen bieten.  <br/> |[Power BI in Ihrer Organisation](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rechteverwaltungsdienste (RMS)** <br/> |RMS für Einzelpersonen ist ein kostenloses Self-Service-Abonnement für Benutzer in einer Organisation, denen vertrauliche Dateien gesendet wurden, die durch Azure Rights Management (Azure RMS) geschützt sind, deren IT-Abteilung jedoch Azure RMS oder Active Directory-Rechteverwaltungsdienste (Active Directory Rights Management Services, AD RMS) nicht implementiert hat.  <br/> |[RMS für Einzelpersonen und Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management-Portal](https://portal.azure.com/): Hier können Sie überprüfen, ob Sie ein bestimmtes durch RMS geschütztes Dokument öffnen können.  <br/> |
|**Microsoft PowerApps** <br/> |In PowerApps können Sie Organisationsdaten verwalten, indem Sie eine App ausführen, die Sie selbst erstellt haben oder die eine andere Person erstellt und für Sie freigegeben hat. Apps werden auf mobilen Geräten wie Smartphones ausgeführt, oder Sie können sie in einem Browser ausführen, indem Sie Dynamics 365 öffnen. Sie können eine unbegrenzte Vielfalt an Apps erstellen - und dies alles, ohne eine Programmiersprache wie z. B. C# erlernen zu müssen.  <br/> |[Self-Service-Registrierung für PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Erhalten Sie eine umfassende Business- und Finanzmanagementlösung für kleine und mittelständische Unternehmen. Dynamics 365 for Financials erleichtert das Bestellen, Verkaufen, Fakturieren und die Berichterstellung - und dies ab dem ersten Tag.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Steigern Sie die Geschwindigkeit Ihrer Geschäftsabläufe. Die vollständigen ERP-Tools in Dynamics 365 for Operations bieten globale Skalierbarkeit und digitale Intelligenz, damit Sie in Ihrem eigenen Tempo einfacher und schneller wachsen können.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource ist ein Ziel für Software-as-a-Service-Business-Apps, die auf der Microsoft-Cloudplattform erstellt werden. AppSource bietet Hunderte von Apps, Add-Ons und Inhaltspaketen, die die Funktionalität von Microsoft-Produkten wie Azure, Dynamics 365, Office 365 und Power BI erweitern.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft Partner Incentives** <br/> |Das Microsoft-Partnernetzwerk bietet drei Arten von Mitgliedschaften. Jede Art ist mit einer Reihe von Vorteilen verbunden, die zum Wachstum Ihres Unternehmens beitragen sollen. Während Sie Ihre Ziele erreichen, nehmen Sie am Programm auf der Ebene teil, die Ihren individuellen Anforderungen entspricht. So können Sie auf mehr Vorteile zugreifen und Ihre Beziehung mit uns und anderen Partnern im Netzwerk entwickeln.  <br/> |[Microsoft Partner Incentives](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft Partner Incentives](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Das Microsoft Business Center ist das Portal für Kunden, die Käufe über den Microsoft-Vertrag für Produkte und Dienste (MICROSOFT Products and Services Agreement, MPSA) getätigt haben. <br/> |[Schnellstart: Registrieren für das Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |Das Microsoft Volume License Service Center zeigt Lizenzen an, die unter Enterprise, Select, Education (Campus oder School), Open Value, Open License und ISV-Lizenzverträgen erworben wurden.  <br/> |[VLSC-Schulung und -Ressourcen](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Volume License Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Durch die Nutzung von Minecraft als Lernplattform können Lehrkräfte jeden Lernenden motivieren und inspirieren, mehr erreichen zu wollen, und eine Leidenschaft zum Lernen erwecken. Treten Sie einer Community von Lehrkräften bei, die lernen, wie sie mithilfe von Minecraft das Potenzial der Lernenden erschließen können.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Laden Sie Videos hoch, und geben Sie sie in der gesamten Organisation frei, um Kommunikation, Teilnahme und Lernerfolge zu verbessern.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) (in Englisch) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate ist ein Produkt, mit dem Sie automatisierte Workflows zwischen Ihren bevorzugten Apps und Diensten einrichten können, um Dateien zu synchronisieren, Benachrichtigungen zu erhalten, Daten zu sammeln und vieles mehr.  <br/> |[Registrieren und Anmelden für Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents ermöglicht Teams das einfache Erstellen leistungsstarker Bots mithilfe einer geführten, codefreien grafischen Oberfläche, ohne dass Datenentwickler oder Entwickler benötigt werden. Power Virtual Agents befasst sich mit vielen der wichtigsten Probleme beim Erstellen von Bots in der Branche. Es beseitigt die Lücke zwischen den Fachexperten und den Entwicklungsteams, die die Bots erstellen, und die lange Latenz zwischen Teams, die ein Problem erkennen und den Bot aktualisieren, um es zu beheben.  <br/> |[Lizenzierungs- und Zugriffsdetails](/power-virtual-agents/requirements-licensing) <br/> |[Registrieren für Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) Business-to-Business (B2B)-Zusammenarbeit können Sie externe Benutzer (oder "Gastbenutzer") einladen, Ihre kostenpflichtigen Azure AD-Dienste zu verwenden. Einige Features sind kostenlos, aber für alle kostenpflichtigen Azure AD-Features können Sie bis zu fünf Gastbenutzer für jede Azure AD-Edition-Lizenz einladen, die Sie für einen Mitarbeiter oder einen Nicht-Gastbenutzer in Ihrem Mandanten besitzen. <br/> |[Self-Service for Azure AD B2B Collaboration Sign-up](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B-Lizenzierungsleitfaden für die Zusammenarbeit](/azure/active-directory/b2b/licensing-guidance) <br/> |
