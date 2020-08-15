---
title: Microsoft 365-Berichterstellungsfeatures
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: Hier finden Sie Informationen zu verschiedenen Berichtsfeatures in Microsoft 365, einschließlich Azure Active Directory und Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 104d587ea87a61a66b73aa1441170f37e082a72f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690718"
---
# <a name="microsoft-365-reporting-features"></a>Microsoft 365-Berichterstellungsfeatures

Die Berichtsfeatures in Microsoft 365 bieten verschiedene Überwachungsberichte für Azure Active Directory (Azure AD), Exchange Online, Geräteverwaltung, aufsichtsüberprüfung und Verhinderung von Datenverlust (DLP). Diese Berichte sind unterschiedlich und von den Microsoft 365-Aktivitätsberichten getrennt.

## <a name="microsoft-365-reports-dashboard"></a>Microsoft 365 Reports-Dashboard

Das Dashboard Berichte in der Microsoft 365 Admin Center-Vorschau zeigt Verwendungs Aktivitäten in Microsoft 365 an. Microsoft 365 globale Administratoren oder ein Exchange Online, SharePoint Online oder Skype for Business Administrator können einen detaillierten Einblick in die Verwendung dieses Diensts erhalten. Beispielsweise die Anzahl der Benutzer in einem bestimmten Microsoft 365-Dienst, die Anzahl der Benutzer, die Microsoft 365-Apps für Enterprise aktiviert haben (zuvor Office 365 ProPlus genannt) und wie viele e-Mails über die Organisation fließen. Berichte stehen für die letzten 7, 30, 90 und 180 Tage zur Verfügung.

Die folgenden Berichte stehen zur Verfügung:

- [E-Mail-Aktivitätsbericht](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Bericht über Microsoft Office Aktivierungen](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online Websiteverwendungsbericht](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive für Unternehmen Nutzungsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer-Aktivitätsbericht](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype for Business Aktivitätsbericht](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype for Business Peer-to-Peer-Aktivitätsbericht](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Bericht Skype for Business Konferenz Organisators](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Aktivitätsbericht Skype for Business Konferenzteilnehmers](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Weitere Informationen finden Sie unter [Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).

## <a name="azure-ad-reports"></a>Azure AD Berichte

Microsoft 365 verwendet Azure AD für die Authentifizierung und Identitätsverwaltung. Microsoft 365-Administratoren verwenden von Azure generierte Berichte, um ungewöhnliche Aktivitäten und nicht autorisierten Zugriff auf Ihre Daten zu identifizieren. Sie können Zugriffs-und Verwendungsberichte in Azure AD verwenden, um Einblick in die Verzeichnisintegrität und-Sicherheit für Ihre Organisation zu erhalten. Anhand dieser Informationen können Sie mögliche Sicherheitsrisiken erkennen und mindern.

Azure AD Berichte können in Microsoft Excel exportiert und mit anderen Daten von Microsoft 365 korreliert werden. Beispielsweise können die Ergebnisse einer Überwachungsprotokoll Suche Einblicke in Zugriffs-, Authentifizierungs-und Anwendungsebene-Aktivitäten bieten. Erweiterte Anomalien und Ressourcen Nutzungsberichte stehen mit Azure AD Premium zur Verfügung. Diese erweiterten Berichte helfen Ihnen, ihre Sicherheitslage zu verbessern und Sie bei der Reaktion auf mögliche Bedrohungen zu unterstützen, indem Sie Analysen zum Geräte Zugriff und zur Anwendungsnutzung anwenden. Weitere Informationen finden Sie unter [Azure Active Directory Reporting](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Exchange Online Überwachungsberichte

Exchange Online Überwachungsberichte enthalten Details zum Postfachzugriff und Änderungen, die Administratoren an Ihren Exchange Online Mandanten vorgenommen haben. Mit der postfachüberwachung können Sie die Aufgaben in der folgenden Tabelle verwenden, um Berichte auszuführen und Exchange Online Überwachungsprotokolle zu exportieren.

> [!NOTE]
> Sie müssen die postfachüberwachungsprotokollierung für jedes Postfach aktivieren, damit überwachte Ereignisse im Überwachungsprotokoll für dieses Postfach gespeichert werden. Wenn die postfachüberwachungsprotokollierung für ein Postfach nicht aktiviert ist, werden Ereignisse für dieses Postfach nicht im Überwachungsprotokoll gespeichert und nicht in Post Fach Überwachungsberichten angezeigt. Weitere Informationen finden Sie unter [Aktivieren der postfachüberwachung](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Aufgabe | Beschreibung |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Ausführen eines Berichts zum Postfachzugriff durch Nicht-Besitzer](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Zeigt die Liste der Postfächer an, auf die ein anderer Benutzer als der Besitzer des Postfachs zugreift. Der Bericht enthält Informationen darüber, wer auf das Postfach zugegriffen hat, welche Aktionen er im Postfach durchgeführt hat und ob die Aktionen erfolgreich waren. |
| [Exportieren von Postfachüberwachungsprotokollen](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Postfachüberwachungsprotokolle enthalten Informationen zu Zugriff und Aktionen in einem Postfach, das von einem anderen Benutzer als dem Postfachbesitzer übernommen wurde. Administratoren können Postfächer zusammen mit einem Datumsbereich angeben, um Berichte zu generieren. Die Protokolle werden in XML exportiert, an eine Nachricht angefügt und an bestimmte Benutzer gesendet, wie vom Administrator festgelegt. |
| [Ausführen eines Berichts für Administratorrollengruppen](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | Die Administratorrollengruppe weist Benutzern Administratorrechte zu. Diese Berechtigungen ermöglichen Benutzern das Ausführen von Verwaltungsaufgaben wie das Zurücksetzen von Kennwörtern, das Erstellen oder Ändern von Postfächern und das Zuweisen von Administratorrechten für andere Benutzer. Der Bericht Administratorrollengruppe zeigt Änderungen an Rollengruppen an, einschließlich des Hinzufügens oder Entfernens von Mitgliedern. |
| [Anzeigen des administratorüberwachungsprotokolls](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | Der Administrator-Überwachungsprotokollbericht listet alle CREATE-, Update-und DELETE-Funktionen auf, die von Administratoren in Exchange Online ausgeführt werden. Protokolleinträge enthalten Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen waren. |
| [Suche und Aufbewahrung von Postfachinhalten](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Enthält Informationen zu Änderungen an in-situ-eDiscovery-oder in-situ-Speichereinstellungen für Postfächer. |
| [Exportieren des Administrator-Überwachungsprotokolls](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | Im administratorüberwachungsprotokoll werden bestimmte administrative Aktionen wie CREATE, Update und DELETE in Exchange Online aufgezeichnet. Die Ergebnisse aus dem Protokoll werden in XML exportiert, und Administratoren können wählen, dieses Protokoll an eine Gruppe von Benutzern zu senden. |
| [Ausführen eines Berichts zur Beweissicherung pro Postfach](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Enthält Informationen zu Änderungen an Beweis Sicherungseinstellungen für Postfächer. |
| [Anzeigen und Exportieren des externen administratorüberwachungsprotokolls](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Enthält Details zu Aktionen, die von externen Administratoren ausgeführt werden. Die Einträge enthalten Informationen darüber, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, sowie alle Aktionen, die Objekte in Exchange Online erstellen, ändern oder löschen. |

## <a name="device-compliance-reports"></a>Geräte Kompatibilitätsberichte

Sie verwalten und sichern mit Ihrem Abonnement verbundene Mobile Geräte mithilfe von Microsoft 365 Mobile Device Management (MDM). Mobile Geräte, die für den Zugriff auf Arbeits-e-Mails, Kalender, Kontakte und Dokumente verwendet werden, spielen eine wichtige Rolle, um sicherzustellen, dass die Mitarbeiter jederzeit und von überall arbeiten können. Es ist wichtig, dass Sie die Informationen Ihrer Organisation schützen. Sie verwenden Microsoft 365 MDM, um Gerätesicherheitsrichtlinien und Zugriffsregeln festzulegen. Wenn Sie verloren gehen oder gestohlen werden, verwenden Sie auch Microsoft 365 MDM, um mobile Geräte abzuwischen.

MDM-Konformitätsberichte bieten eine Übersicht über Richtlinien, die von einer Organisation eingerichtet wurden, um mobile Geräte zu sichern, die auf Microsoft 365-Daten zugreifen. Der Bericht ermöglicht das Filtern von Geräten durch den Kompatibilitätsstatus, gemeldete Verstöße, blockierte Geräte und wie viele Geräte aufgrund von Sicherheitsrichtlinien gelöscht wurden. Weitere Informationen finden Sie unter [Übersicht über die Verwaltung mobiler Geräte für Microsoft 365](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

DLP-Richtlinien helfen bei der Verwaltung der Sicherheit und des Informationsflusses in einer Organisation. Sie können Richtlinien einrichten, um den Zugriff auf Inhalte zu blockieren, Daten zu verschlüsseln oder Benutzer über Richtlinien-und Richtlinienverstöße mithilfe von in der Anwendung verwendeten DLP-Richtlinien Tipps zu informieren. DLP-Berichte bieten Einblicke in die Anzahl von Richtlinien-und Regel Übereinstimmungen, Außerkraftsetzungen und falsch positiven Ergebnissen.

Verwenden Sie das Microsoft 365 Admin Center, um Informationen über die Anzahl der Nachrichten anzuzeigen, die von ihren DLP-Richtlinien erkannt wurden. DLP-Berichte bieten Einblicke in Richtlinien-und Regel Übereinstimmungen für gesendete und empfangene e-Mails. Sie können die Anzahl der Übereinstimmungen, Außerkraftsetzungen und falsch positiver Ergebnisse für jede Richtlinie in den letzten 24 Stunden auch über das Exchange Admin Center anzeigen. Wenn Sie einen Excel-Bericht herunterladen, können Sie noch ausführlichere Details anzeigen, beispielsweise wer die Nachricht gesendet hat, an welchem Tag und welche Richtlinien Übereinstimmungen ausgelöst wurden. Weitere Informationen finden Sie unter [Anzeigen von Berichten zu DLP-Richtlinien Erkennungen](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj889415(v=exchg.150)).

## <a name="auditing-in-yammer-enterprise"></a>Überwachung in jammern Enterprise

Jammern Enterprise bietet Administratoren die Möglichkeit, Benutzeraktivitätsdaten aus Ihrem Jammer Netzwerk über die [Datenexport-API "jammern](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)" oder manuell über die Seite "Netzwerkadministrator jammern" zu exportieren. Die Möglichkeit zum Exportieren von Protokollen ist auf Netzwerkadministratoren in jammern beschränkt. (Alle Microsoft 365 globalen Administratoren sind jammern von Netzwerkadministratoren.)

Die folgenden Daten sind exportierbar:

| Filename | Beschreibung |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Alle neuen, ausstehenden und angehalten Benutzer im Netzwerk |
| Messages.csv | Alle Nachrichten im Netzwerk |
| Files.csv (Metadaten) | Metadaten wie filename, Datei-API-URL, Uploader-ID, hochgeladen usw. |
| Files.csv (Original Dateien) | ZIP-Datei der ursprünglichen Dateien, die von Benutzern in "jammern" hochgeladen wurden |
| Topics.csv | Im Netzwerk erstellte Themen |
| Pages.csv | Seiten (Notizen), die von Benutzern im Netzwerk erstellt wurden |
| Admins.csv | Alle überprüften Administratoren im Netzwerk |
| Networks.csv | Alle jammern externer Netzwerke |

Jammern von Unternehmensdaten ist auch über die Microsoft 365-Aktivitätsberichte verfügbar. Darüber hinaus arbeitet jammern aktiv an der Bereitstellung zusätzlicher Protokollierung über die Microsoft 365-Verwaltungs Aktivitäts-API und an der Möglichkeit, Daten mit Power BI zu überdenken. Weitere Informationen zu diesen Features finden Sie in der [Office-Roadmap](https://fasttrack.microsoft.com/roadmap?filters=yammer) .
