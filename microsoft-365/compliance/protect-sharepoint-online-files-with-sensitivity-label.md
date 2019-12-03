---
title: Schützen von SharePoint Online-Dateien mit Vertraulichkeitsbezeichnungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Zusammenfassung: Verwenden Sie Azure Information Protection zum Schützen von Dateien auf einer streng vertraulichen SharePoint Online-Teamwebsite.'
ms.openlocfilehash: b5251d393249e9023f6f437cb3df6c074ebdf436
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39637827"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>Schützen von SharePoint Online-Dateien mit Vertraulichkeitsbezeichnungen

Führen Sie die in diesem Artikel aufgeführten Schritte aus, um eine Office 365-Vertraulichkeitsbezeichnung so zu konfigurieren, dass Verschlüsselung und Berechtigungen für Dateien bereitgestellt werden. Diese Dateien können einer SharePoint-Bibliothek hinzugefügt werden, die für streng vertraulichen Schutz konfiguriert ist. Sie können eine Datei auch direkt von der Website öffnen und die Bezeichnung anwenden. Der Schutz durch die Verschlüsselung und Berechtigungen ist mit einer Datei verbunden, selbst wenn sie von der Website heruntergeladen wird. 

Diese Schritte sind Teil einer umfangreicheren Lösung zur Konfiguration eines Schutzes streng vertraulicher Daten für SharePoint-Websites und die Dateien innerhalb dieser Websites. Weitere Informationen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection). 

Die Verwendung von Vertraulichkeitsbezeichnungen für Dateien in SharePoint Online wird nicht für alle Benutzer empfohlen, sie ist jedoch eine Option für Kunden, die für eine Teilmenge von Dateien diese Ebene des Schutzes benötigen.

Einige wichtige Hinweise zu dieser Lösung:
- Wenn Verschlüsselung auf in Office 365 gespeicherte Dateien angewendet wird, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten. Gemeinsame Dokumenterstellung, eDiscovery, Suche, Delve und andere Features für die Zusammenarbeit funktionieren nicht. DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) können nur auf die Metadaten (einschließlich der Office 365-Bezeichnungen), aber nicht auf die Inhalte dieser Dateien (z.B. Kreditkartennummern in Dateien) angewendet werden.

- Für diese Lösung muss ein Benutzer eine Bezeichnung auswählen, die den Schutz anwendet. Wenn Sie eine automatische Verschlüsselung benötigen und möchten, dass SharePoint die Dateien indiziert und überprüft, sollten Sie die Verwendung von Information Rights Management (IRM) in SharePoint Online in Betracht ziehen. Wenn Sie eine SharePoint-Bibliothek für IRM konfigurieren, werden Dateien automatisch verschlüsselt, wenn sie zur Bearbeitung heruntergeladen werden.  SharePoint IRM enthält Beschränkungen, die möglicherweise Einfluss auf Ihre Entscheidung haben. Weitere Informationen finden Sie unter [Einrichten der Verwaltung von Informationsrechten (IRM) im SharePoint Admin Center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Einrichten eines Administrators

Um diese zusätzliche Sicherheitsstufe für Dateien in einer bestimmten SharePoint Online-Teamwebsite zu erreichen, müssen Sie eine benutzerdefinierte Vertraulichkeitsbezeichnung konfigurieren, bei der es sich entweder um eine eigene Bezeichnung oder um eine Unterbezeichnung der allgemeinen Bezeichnung für stark regulierte Daten handelt. Nur Mitglieder der Office 365-Gruppe für die SharePoint Online-Teamwebsite sehen die angepasste Bezeichnung oder Unterbezeichnung in der Liste von Bezeichnungnen.

- Verwenden Sie eine Vertraulichkeitsbezeichnung, wenn Sie nur eine kleine Anzahl von Bezeichnungen für die globale Nutzung und für einzelne private Teams benötigen.

- Verwenden Sie eine Vertraulichkeitsunterbezeichnung, wenn Sie über eine große Anzahl von Bezeichnungen verfügen oder Bezeichnungen für streng vertrauliche Teams unter der streng regulierten Bezeichnung organisieren möchten.

Verwenden Sie [diese Anweisungen ](encryption-sensitivity-labels.md) zum Konfigurieren einer separaten Bezeichnung oder einer Unterbezeichnung mit den folgenden Einstellungen:

- Der Name der Bezeichnung oder Unterbezeichnung enthält den Namen der Teamwebsite.
- Die Verschlüsselung ist aktiviert.
- Die Office 365-Gruppe für die Teamwebsite verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.

Veröffentlichen Sie nach dem Erstellen die neue Bezeichnung oder die neue Unterbezeichnung für Ihre Benutzer, die diese dann auf Dateien entweder lokal vor dem Hochladen in das Team oder später nach dem Speichern der Datei im Team anwenden können.
 
Wenn Ihre Benutzer die Vertraulichkeitsbezeichnung über die Option **Vertraulichkeit** auf dem Menüband **Start** in Microsoft Word, Excel und PowerPoint auswählen können.
  
> [!NOTE]
> Wenn Sie über mehrere streng vertrauliche SharePoint Online-Teamwebsites verfügen, sollten Sie mehrere Vertraulichkeitsbezeichnungen erstellen. 
  
## <a name="adding-permissions-for-external-users"></a>Hinzufügen von Berechtigungen für externe Benutzer
Es gibt zwei Möglichkeiten, wie Sie externen Benutzern Zugriff auf Dateien gewähren können, die mit einer Vertraulichkeitsbezeichnung geschützt sind. In beiden Fällen benötigen externe Benutzer ein Azure AD-Konto. Wenn externe Benutzer nicht Mitglied einer Organisation sind, die Azure AD verwendet, können sie ein Azure AD-Konto als Einzelperson auf dieser Anmeldeseite beantragen: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Fügen Sie externe Benutzer zur Office 365-Gruppe für die Teamwebsite hinzu. Sie müssen zuerst das Konto als B2B-Benutzer in Ihrem Verzeichnis hinzufügen. Das [Zwischenspeichern einer Gruppenmitgliedschaft durch Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) kann einige Stunden in Anspruch nehmen.  
 - Externe Benutzerkonten können direkt zur Bezeichnungskonfiguration hinzugefügt werden. Sie können alle Benutzer einer Organisation (z.B. „Fabrikam.com“), eine Office 365-Gruppe (z.B. eine Finanzgruppe innerhalb einer Organisation) oder einen Benutzer hinzufügen. Beispielsweise können Sie ein externes Team einer Regulierungsbehörde zu den Berechtigungen Ihrer Vertraulichkeitsbezeichnung hinzufügen.

## <a name="see-also"></a>Siehe auch

[Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
