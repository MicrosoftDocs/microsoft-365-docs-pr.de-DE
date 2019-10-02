---
title: SharePoint Online Website für hoch vertrauliche digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: wie Contoso eine SharePoint Online Website für hochregulierte Daten implementiert, um die Zusammenarbeit zwischen den Forschungsteams zu vereinfachen.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369526"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint Online Website für hoch vertrauliche digitale Objekte der Contoso Corporation

 **Zusammenfassung:** Wie Contoso eine SharePoint Online Website für hochregulierte Daten implementiert, um die Zusammenarbeit zwischen den Forschungsteams zu vereinfachen.
  
Die wertvollsten Ressourcen von Contoso sind das geistige Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigungstechniken und Designspezifikationen für Produkte, die sich in der Entwicklung befinden. Diese Objekte befinden sich in digitaler Form, werden ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert. Bei der Bereitstellung von Microsoft 365 Enterprise durch Contoso wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit zwischen den Forschungsteams in Paris, Moskau, New York, Beijing und Bangalore umstellen. 
  
Aufgrund Ihrer sensiblen Natur muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:

- Beschränkt auf die Gruppe von Personen, die Sie anzeigen oder ändern dürfen, mit laufenden Berechtigungen für die Website, die nur von SharePoint-Administratoren verwaltet wird. 
- Geschützt durch Datenverlust Verhinderung (DLP), um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.
- Verschlüsselt und mit Zugriffssteuerungslisten geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt werden.

Sicherheits-und SharePoint-Administratoren in der IT-Abteilung von Contoso haben beschlossen, eine [SharePoint Online Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.
  
Contoso hat diese Schritte zum Erstellen und Sichern einer SharePoint Online Teamwebsites für Ihre Forschungsteams verwendet.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Schritt 1: überprüfen und Überprüfen der Mitglieder der Gruppe "Forschungsteams"

Contoso IT-Administratoren haben eine Überprüfung der Gruppe von Sicherheitsgruppen für Ihre Forschungsteams durchgeführt. Sie haben alle Personen entfernt, die kein Forscher waren oder keinen Zugriff auf Forschungsressourcen benötigten. 

Außerdem wurden diese neuen Sicherheitsgruppen erstellt:

- **Forschung-Administratoren**  Die Gruppe von SharePoint-Administratoren, die Vollzugriff auf die Website haben, einschließlich der Fähigkeit, Berechtigungen zu ändern.
- **Forschung-Mitglieder**  Die Gruppe von Sicherheitsgruppen für die Forschungsteams auf der ganzen Welt.
- **Forschung-Betrachter**  Die Gruppe von Verwaltungs Benutzern wie Führungskräfte in der Forschungsorganisation, die nur die Objekte auf der Website anzeigen können.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Schritt 2: Erstellen einer isolierten SharePoint Online Teamwebsite 

Contoso SharePoint-Administratoren haben zuerst eine neue Teamwebsite mit dem Namen **Research**erstellt. Anschließend wurde Folgendes konfiguriert:

- Die Berechtigungsstufe "Vollzugriff" zur Verwendung der SharePoint-Gruppe "Research Owners" mit der Sicherheitsgruppe " **Research-Admins** " als Mitglied
- Die Berechtigungsstufe "Bearbeiten" zur Verwendung der SharePoint-Gruppe "Forschungs Mitglieder" mit der Sicherheitsgruppe " **Forschungs Mitglieder** " als Mitglied
- Die Berechtigungsstufe "lesen" zur Verwendung der SharePoint-Gruppe "Research Visitors" mit der Sicherheitsgruppe " **Research-Viewers** " als Mitglied

Im folgenden finden Sie die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder.

![SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Als nächstes haben Sie zusätzliche Einschränkungen für die Website konfiguriert.

Informationen zu den Konfigurationsdetails finden Sie unter [Deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>Schritt 3: Konfigurieren der Website für eine restriktive DLP-Richtlinie

Zunächst wendeten Contoso-Administratoren die **streng vertrauliche** Office 365 Aufbewahrungs Bezeichnung für die **Forschungs** Website an.

Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie mit dem Namen " **Forschung** " erstellt:

- Verwendet die Office 365 Aufbewahrungs Bezeichnung mit **hoher Vertraulichkeit** . 
- Auf die **Forschungs** Website angewendet wird.
- Blockiert Benutzer, wenn Sie versuchen, ein digitales Objekt auf der **Forschungs** Website außerhalb von Contoso freizugeben.

Informationen zu den Konfigurationsdetails finden Sie unter [Protect SharePoint Online files with Retention Labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Schritt 4: Erstellen einer Azure Information Protection-unter Bezeichnung für die Website

Contoso-Administratoren haben eine neue unter Bezeichnung für Azure Information Protection mit dem Namen **Research** of the Standard Label **highly Confidential** in einer bereichsbezogenen Richtlinie erstellt, die Folgendes umfasst:

- Verschlüsselung erforderlich.
- Ermöglicht den vollständigen Zugriff durch Mitglieder der Sicherheitsgruppe " **Research-Members** ".
- Ermöglicht Lesezugriff durch Mitglieder der Sicherheitsgruppe " **Research-Viewers** ".

Als nächstes haben Sie den Azure Information Protection-Client für die Geräte der Mitglieder des Forschungsteams bereitgestellt.

Informationen zu den Konfigurationsdetails finden Sie unter [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Hier ist die resultierende Konfiguration der **Forschungs** Website für streng vertrauliche Ressourcen.

![Die resultierende Konfiguration des * * Research * *-Standorts für hoch vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Dateien in Ordnern der **Forschungs** Website sind geschützt durch:

- Die unter Bezeichnung Azure Information Protection für **Forschung** , die Verschlüsselung und permssions auf jede Datei anwendet, die mit der Datei reist, wenn Sie von der **Forschungs** Website verschoben oder kopiert wird.
- Die DLP-Richtlinie für **Forschung** , die die **streng vertrauliche** Aufbewahrungs Bezeichnung und Einstellungen verwendet, die verhindern, dass die Datei für externe Benutzer freigegeben wird.
- Die Gruppe von Websiteberechtigungen, die nur Mitgliedern der Sicherheitsgruppe " **Research-Admins** " den Zugriff auf die Mitglieder der Sicherheitsgruppen "Research- **Members** " und " **Research-Viewers** " und "Verwaltung" ermöglichen.

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Schritt 5: Migrieren der lokalen SharePoint-Forschungsdaten

Contoso-Administratoren haben alle lokalen Forschungs Dateien in der lokalen SharePoint Server 2016-Website in Ordner auf der neuen **Research** SharePoint Online-Website verschoben.

## <a name="step-6-trained-their-users"></a>Schritt 6: Schulung der Benutzer 

Mitarbeiter von Contoso Security haben die Forschungsteams in einem obligatorischen Kurs ausgebildet, der Sie durchschritten hat:

- So greifen Sie auf die neue **Research** SharePoint Online-Website und Ihre vorhandenen Dateien zu.
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.
- Verwenden des Azure Information Protection-Clients zum Beschriften von Recherche Dateien mit der unter Bezeichnung " **Research** ".
- Eine Demonstration der Art und Weise, wie die **Forschungs** -unter Bezeichnung eine Datei schützt, auch wenn Sie von der Website durchgesickert ist.

Das Endergebnis ist eine sichere Umgebung, in der die Forscher innerhalb der Organisation in einer sicheren Umgebung zusammenarbeiten können. 

Wenn ein Forschungsdokument mit dem **Recherche** -unter Label von der **Forschungs** Website durchgesickert ist, ist es verschlüsselt und nur für Mitglieder der Sicherheitsgruppen " **Research-Members** " und " **Research-Viewers** " mit gültigen Anmeldeinformationen zugänglich.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.

