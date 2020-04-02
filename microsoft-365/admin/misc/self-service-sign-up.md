---
title: Verwenden der Self-Service-Registrierung in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Erfahren Sie mehr über die Office 365 Self-Service-Registrierung und verfügbaren Self-Service-Programmen wie Microsoft Power apps, Microsoft Flow und Dynamics 365 für Financials.
ms.custom: okr_SMB
ms.openlocfilehash: fa7e6dcb4c40a7a41599b7c1a81fa596868d8e2d
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106112"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Verwenden der Self-Service-Registrierung in Ihrer Organisation

Wir hören auf Ihr Feedback und haben es den Benutzern in Ihrer Organisation erleichtert, sich für Onlinedienste von Microsoft zu registrieren. Wir nennen diesen neuen Registrierungsvorgang "Self-Service-Registrierung", weil sich Ihre Benutzer für im Rahmen Ihres Abonnements bezahlte Dienste registrieren oder kostenlose Dienste verwenden können, ohne Sie bitten zu müssen, Aktionen in ihrem Auftrag auszuführen.
  
## <a name="how-self-service-sign-up-works"></a>So funktioniert die Self-Service-Registrierung

Im folgenden Beispiel wird beschrieben, wie die Self-Service-Registrierung für eine Schule oder Uni funktioniert. Dieser Vorgang gilt für alle Organisationen, in deren Mandanten Self-Service-Programme aktiviert sind.
  
1. Schüler und Studenten sowie Lehrkräfte verfügen über Schul- oder Uni-E-Mail-Adressen, die angeben, dass sie Ihrer Bildungseinrichtung zugeordnet sind. Die E-Mail-Adresse "jakob@uw.edu" gibt beispielsweise einen Studenten der University of Washington an.

2. Studenten und Dozenten gehen auf [unsere](https://go.microsoft.com/fwlink/p/?LinkId=536628)Website und verwenden Ihre e-Mail-Adresse, um sich für die von Ihrer Organisation angebotenen Dienste zu registrieren, beispielsweise Office 365 ProPlus. Sie können sich auch für andere ﻿kostenlose Dienste registrieren, die wir anbieten.

3. Wir validieren Ihre e-Mail-Adresse und können dann sofort mit der Verwendung von Office 365, Power BI oder anderen Diensten beginnen.

4. Als Geschäfts Administrator sehen Sie, wer sich für ein Abonnement angemeldet hat, indem Sie die Seite **Produkte & Dienste** im Admin Center anzeigen. Auf diese Weise können Sie sehen, wann neue oder nicht erkannte Lizenzen für Dienste in Ihrem Mandanten vorhanden sind. Um zu steuern, ob Benutzer sich für Self-Service-Abonnements anmelden können, verwenden Sie das Cmdlet " [MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell" mit dem Parameter " **AllowAdHocSubscriptions** ". Weitere Informationen finden Sie unter [wie kann ich Self-Service-Einstellungen steuern?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Verfügbare Self-Service-Programme

Im Folgenden werden die aktuell verfügbaren Self-Service-Programme aufgeführt. Diese Liste wird aktualisiert, wenn neue Programme hinzugefügt werden.
  
|||||
|:-----|:-----|:-----|:-----|
|**Programm** <br/> |**Beschreibung** <br/> |**Zusätzliche Informationen** <br/> |****Website für die Self-Service-Registrierung**** <br/> |
|Office 365 a1 * * * * <br/> |Jeder Schüler oder Lehrer kann eine Schul-e-Mail-Adresse verwenden, um sich kostenlos Office 365 anzumelden und Office-Apps für das Internet, 1TB von OneDrive-Cloud-Speicher und SharePoint Online für Klasse, Team und Projektwebsites zu erhalten.  <br/> |[Self-Service-Registrierung für Office 365 Education: Häufig gestellte technische Fragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 Plus** <br/> |Entsprechend berechtigte Schüler/Studierende und Lehrkräfte können sich für Office 365 A1 Plus registrieren, in dem alles vorstehend Erwähnte und zusätzlich Office 365 ProPlus enthalten ist. Bei Office 365 ProPlus handelt es sich um Produktivitätssoftware mit Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access und Skype for Business, die auf Ihrem Desktop- oder Laptopcomputer installiert wird.  <br/> |[Self-Service-Registrierung für Office 365 Education: Häufig gestellte technische Fragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI ermöglicht Benutzern das Visualisieren von Daten, die Freigabe von Ermittlungen und die Zusammenarbeit auf intuitiven, neuen wegen. <br/> Wenn Ihre Organisation bereits Office 365 abonniert hat, werden Ihnen möglicherweise zusätzlich Lizenzen für "Power BI pro Einzelbenutzer Testversion" angezeigt, die Benutzern begrenzten, freien Zugriff auf Erweiterte Funktionen bieten.  <br/> |[Power BI in Ihrer Organisation](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rechteverwaltungsdienste (RMS)** <br/> |RMS für Einzelpersonen ist ein kostenloses Self-Service-Abonnement für Benutzer in einer Organisation, denen vertrauliche Dateien gesendet wurden, die durch Azure Rights Management (Azure RMS) geschützt sind, deren IT-Abteilung jedoch Azure RMS oder Active Directory-Rechteverwaltungsdienste (Active Directory Rights Management Services, AD RMS) nicht implementiert hat.  <br/> |[RMS für Einzelpersonen und Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management-Portal](https://portal.azure.com/): Hier können Sie überprüfen, ob Sie ein bestimmtes durch RMS geschütztes Dokument öffnen können.  <br/> |
|**Microsoft PowerApps** <br/> |In PowerApps können Sie Organisationsdaten verwalten, indem Sie eine App ausführen, die Sie selbst erstellt haben oder die eine andere Person erstellt und für Sie freigegeben hat. Apps werden auf mobilen Geräten wie Smartphones ausgeführt, oder Sie können sie in einem Browser ausführen, indem Sie Dynamics 365 öffnen. Sie können eine unbegrenzte Vielfalt an Apps erstellen - und dies alles, ohne eine Programmiersprache wie z. B. C# erlernen zu müssen.  <br/> |[Self-Service-Registrierung für PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Erhalten Sie eine umfassende Business- und Finanzmanagementlösung für kleine und mittelständische Unternehmen. Dynamics 365 for Financials erleichtert das Bestellen, Verkaufen, Fakturieren und die Berichterstellung - und dies ab dem ersten Tag.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Steigern Sie die Geschwindigkeit Ihrer Geschäftsabläufe. Die vollständigen ERP-Tools in Dynamics 365 for Operations bieten globale Skalierbarkeit und digitale Intelligenz, damit Sie in Ihrem eigenen Tempo einfacher und schneller wachsen können.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource ist ein Ziel für Software-as-a-Service-Business-Apps, die auf der Microsoft-Cloudplattform erstellt werden. AppSource enthält Hunderte von Apps, Add-Ons und Inhaltspaketen, die die Funktionalität von Microsoft-Produkten wie Azure, Dynamics 365, Office 365 und Power BI erweitern.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft Partner Incentives** <br/> |Das Microsoft-Partnernetzwerk bietet drei Arten von Mitgliedschaften. Jede Art ist mit einer Reihe von Vorteilen verbunden, die zum Wachstum Ihres Unternehmens beitragen sollen. Während Sie Ihre Ziele erreichen, nehmen Sie am Programm auf der Ebene teil, die Ihren individuellen Anforderungen entspricht. So können Sie auf mehr Vorteile zugreifen und Ihre Beziehung mit uns und anderen Partnern im Netzwerk entwickeln.  <br/> |[Microsoft Partner Incentives](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft Partner Incentives](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Das Microsoft Business Center ist das Portal für Kunden, die über den Microsoft-Produkt-und Dienstleistungsvertrag (MPSA) Einkäufe getätigt haben. <br/> |[Schnellstart: Registrieren für das Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |Das Microsoft Volume License Service Center zeigt Lizenzen, die unter Enterprise, SELECT, Education (Campus oder School), Open Value, Open License und ISV Royalty Agreements erworben wurden.  <br/> |[VLSC Schulungen und Ressourcen](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Volumenlizenz Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Durch die Nutzung von Minecraft als Lernplattform können Lehrkräfte jeden Lernenden motivieren und inspirieren, mehr erreichen zu wollen, und eine Leidenschaft zum Lernen erwecken. Treten Sie einer Community von Lehrkräften bei, die lernen, wie sie mithilfe von Minecraft das Potenzial der Lernenden erschließen können.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Laden Sie Videos hoch, und geben Sie sie in der gesamten Organisation frei, um Kommunikation, Teilnahme und Lernerfolge zu verbessern.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) (in Englisch) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power-Automatisierung** <br/> |Power Automation ist ein Produkt, das Sie beim Einrichten von automatisierten Workflows zwischen Ihren bevorzugten apps und Diensten unterstützt, um Dateien zu synchronisieren, Benachrichtigungen zu erhalten, Daten zu sammeln und vieles mehr.  <br/> |[Registrieren und anmelden für Power Automation](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power-Automatisierung](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Mit Power Virtual Agents können Teams mühelos leistungsstarke Bots mithilfe einer geführten, nicht-Code-grafischen Oberfläche erstellen, ohne dass Daten Wissenschaftler oder Entwickler benötigt werden. Power Virtual Agents befassen sich mit vielen der wichtigsten Probleme mit dem bot-Gebäude in der Branche heute. Dadurch wird die Lücke zwischen den Experten des Fachbereichs und den Entwicklungsteams, die die Bots erstellen, und der langen Wartezeit zwischen den Teams, die ein Problem erkennen, und dem Aktualisieren des bot zur Lösung eliminiert.  <br/> |[Lizenzierungs-und Zugriffsdetails](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Registrieren für Power Virtual Agents](https://aka.ms/TryPVA) <br/> |