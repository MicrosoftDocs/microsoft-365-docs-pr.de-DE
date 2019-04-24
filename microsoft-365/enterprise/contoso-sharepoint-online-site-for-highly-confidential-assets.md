---
title: SharePoint Online-Website für hoch vertrauliche digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: wie Contoso eine SharePoint Online-Website für hochregulierte Daten implementiert hat, um die Zusammenarbeit zwischen ihren Forschungsteams zu vereinfachen.'
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289221"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint Online-Website für hoch vertrauliche digitale Objekte der Contoso Corporation

 **Zusammenfassung:** Wie Contoso eine SharePoint Online-Website für hochregulierte Daten implementiert hat, um die Zusammenarbeit zwischen ihren Forschungsteams zu vereinfachen.
  
Die wertvollsten Ressourcen von Contoso sind Ihr geistiges Eigentum in Form von Geschäftsgeheimnisse, wie proprietäre Herstellungsverfahren und Designspezifikationen für Produkte, die sich in der Entwicklung befinden. Diese Objekte sind in digitaler Form, die ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert wurden. Als Contoso Microsoft 365 Enterprise bereitgestellt hat, wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit über Forschungsteams in Paris, Moskau, New York, Peking und Bangalore hinweg in die Cloud überführen. 
  
Aufgrund Ihrer sensiblen Art muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:

- Beschränkt auf die Gruppe von Personen, die Sie anzeigen oder ändern dürfen, mit laufenden Berechtigungen für die Website, die nur von SharePoint-Administratoren verwaltet wird. 
- Protected with Data Loss Prevention (DLP), um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.
- Verschlüsselt und mit Zugriffssteuerungslisten geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt sind.

Sicherheit und SharePoint-Administratoren in der IT-Abteilung von Contoso haben sich entschieden, eine [SharePoint Online-Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.
  
Contoso hat die folgenden Schritte zum Erstellen und Sichern einer SharePoint Online-Teamwebsite für Ihre Forschungsteams verwendet.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Schritt 1: überprüfen und Überprüfen der Mitglieder von Forschungsteam Gruppen

Contoso-IT-Administratoren haben eine Überprüfungen der Gruppe von Sicherheitsgruppen für Ihre Forschungsteams durchgeführt. Sie haben alle Personen entfernt, die kein Forscher waren oder keinen Zugriff auf Forschungsobjekte benötigten. 

Außerdem haben Sie die folgenden neuen Sicherheitsgruppen erstellt:

- **Forschung-Administratoren**  Die Gruppe von SharePoint-Administratoren, die über vollständige Kontrolle über die Website verfügen, einschließlich der Möglichkeit, Berechtigungen zu ändern.
- **Research-Mitglieder**  Die Gruppe von Sicherheitsgruppen für die Teams weltweit.
- **Forschung – Betrachter**  Die Gruppe der Verwaltungs Benutzer, wie beispielsweise Führungskräfte in der Forschungsorganisation, die nur die Objekte auf der Website anzeigen können.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Schritt 2: Erstellen einer isolierten SharePoint Online-Teamwebsite 

Contoso SharePoint-Administratoren haben zunächst eine neue Teamwebsite mit dem Namen **Research**erstellt. Anschließend haben Sie Folgendes konfiguriert:

- Die Berechtigungsstufe "Vollzugriff" für die Verwendung der SharePoint-Gruppe "Research Owners" mit der Sicherheitsgruppe " **Research-Admins** " als Mitglied
- Die Berechtigungsstufe "Bearbeiten" für die Verwendung der SharePoint-Gruppe "Research Members" mit der Sicherheitsgruppe " **Forschungs Mitglieder** " als Mitglied
- Die Lese Berechtigungsstufe zum Verwenden der SharePoint-Gruppe "Research Visitors" mit der Sicherheitsgruppe " **Research-Viewers** " als Mitglied

Hier sind die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Als nächstes haben Sie zusätzliche Einschränkungen für die Website konfiguriert.

Die Konfigurationsdetails finden Sie unter [Deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>Schritt 3: Konfigurieren der Website für eine restriktive DLP-Richtlinie

Zunächst wendeten Contoso-Administratoren die **streng vertrauliche** Office 365-Aufbewahrungs Bezeichnung auf die **Forschungs** Website an.

Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie namens " **Forschung** " erstellt, die:

- Verwendet die **vertrauliche** Office 365-Aufbewahrungs Bezeichnung. 
- Wird auf die **Forschungs** Website angewendet.
- Verhindert, dass Benutzer Dokumente freigeben.

Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Schritt 4: Erstellen einer Azure Information Protection-unter Bezeichnung für die Website

Contoso-Administratoren haben eine neue Azure Information Protection-unter Bezeichnung mit dem Namen **Research** der standardmäßigen, **streng vertraulichen** Bezeichnung in einer bereichsbezogenen Richtlinie erstellt, die:

- Verschlüsselung erforderlich.
- Ermöglicht den vollständigen Zugriff durch Mitglieder der Sicherheitsgruppe " **Research-Members** ".
- Ermöglicht den Lesezugriff durch Mitglieder der Sicherheitsgruppe " **Research-Viewers** ".

Als nächstes haben Sie den Azure Information Protection-Client für die Geräte von Mitgliedern des Forschungsteams bereitgestellt.

Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Hier ist die resultierende Konfiguration der **Forschungs** Website für hoch vertrauliche Ressourcen.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Dateien in Ordnern der **Recherche** Website werden geschützt durch:

- Die **** unter Bezeichnung Azure Information Protection, die Verschlüsselung und permssions für jede Datei anwendet, die mit der Datei reist, wenn Sie von der **Recherche** Website verschoben oder kopiert wird.
- Die **** DLP-richtLinie "Recherchieren" verwendet die **hochsensible** Aufbewahrungs Bezeichnung und Einstellungen, die verhindern, dass die Datei die Website verlässt.
- Die Gruppe von Websiteberechtigungen, die nur den Mitgliedern der Sicherheitsgruppen für **** Recherche-und Forschungs **** Benutzer sowie der Verwaltung von Mitgliedern der sicherheitsGruppe "Recherche- **Administratoren** " den Zugriff ermöglichen.

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Schritt 5: Migrieren der lokalen SharePoint-Forschungsdaten

Contoso-Administratoren haben alle lokalen Recherche Dateien in der lokalen SharePoint Server 2016-Website in Ordner in der neuen **Research** SharePoint Online-Website verschoben.

## <a name="step-6-trained-their-users"></a>Schritt 6: Schulung der Benutzer 

Das Sicherheitsteam von Contoso hat die Forschungsteams in einem obligatorischen Kurs geschult, der Sie durchlaufen hat:

- Zugriff auf die neue **Research** SharePoint Online-Website und die vorhandenen Dateien
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.
- Verwenden des Azure Information Protection-Clients zum Beschriften von Recherche Dateien mit der **Recherche** -unter Bezeichnung.
- Eine Demonstration, wie die untergeordnete Bezeichnung " **Research** " eine Datei schützt, auch wenn Sie von der Website geleckt wird.

Das Endergebnis ist eine sichere Umgebung, in der die Forscher innerhalb der gesamten Organisation in einer sicheren Umgebung zusammenarbeiten können. 

Wenn ein Forschungsdokument mit der unter Bezeichnung **Recherche** aus der **Forschungs** Website ausgelaufen ist, wird es verschlüsselt und kann nur Mitgliedern der sicherheitsGruppen "Research- **Members** " und " **Research-Viewers** " mit gültigen Anmeldeinformationen zugänglich gemacht werden.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.

