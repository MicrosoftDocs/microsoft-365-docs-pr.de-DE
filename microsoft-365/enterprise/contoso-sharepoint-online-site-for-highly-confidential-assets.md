---
title: SharePoint-Website für hoch vertrauliche digitale Objekte der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: wie Contoso eine SharePoint-Website für hochregulierte Daten zur einfacheren Zusammenarbeit zwischen den Forschungsteams implementiert hat.'
ms.openlocfilehash: c0b9e36f90e64e1d1c7f7ea2c4b1b4b65e60b95c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601132"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint-Website für hoch vertrauliche digitale Objekte der Contoso Corporation

Die wertvollsten Ressourcen von Contoso sind das geistige Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigungstechniken und Designspezifikationen für Produkte, die sich in der Entwicklung befinden. Diese Objekte wurden in digitaler Form gespeichert und ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert. Bei der Bereitstellung von Microsoft 365 Enterprise durch Contoso wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit zwischen den Forschungsteams in Paris, Moskau, New York, Beijing und Bangalore umstellen. 
  
Aufgrund Ihrer sensiblen Natur muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:

- Beschränkt auf die Gruppe von Personen, denen der Zugriff gewährt werden kann. 
- Durch eine DLP-Richtlinie (Data Loss Prevention) geschützt, um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.
- Verschlüsselt und mit Berechtigungen geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt werden.

Sicherheits-und SharePoint-Administratoren in der IT-Abteilung von Contoso haben sich für die Verwendung einer [SharePoint-Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)entschieden.
  
Contoso hat diese Schritte zum Erstellen und Sichern von SharePoint-Teamwebsites für Ihre Forschungsteams verwendet.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Schritt 1: Erstellen einer privaten SharePoint-Teamwebsite

Um den Zugriff auf die SharePoint-Website zu schützen, hat Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md)konfiguriert.

Als nächstes kompilierte Contoso IT-Administratoren eine Liste der Benutzerkonten für die Forscher in ihren Büros in Paris, Moskau, New York, Beijing und Bangalore. 

Anschließend hat ein IT-Administrator von Contoso eine neue private Teamwebsite mit dem Namen **Research** erstellt und alle Benutzerkonten für die Forscher hinzugefügt.

Anschließend wurden zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Forscher Zugriff auf die Website freigeben, und um zu verhindern, dass nicht-Forscher Zugriff auf die Website anfordern.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Schritt 2: Konfigurieren der Website für eine restriktive DLP-Richtlinie

Zunächst wendeten Contoso-Administratoren die vorhandene **streng vertrauliche** Office 365 Aufbewahrungs Bezeichnung auf den Ordner "Dokumente" der **Forschungs** Website an.

Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie mit dem Namen " **Forschung** " erstellt:

- Verwendet die Office 365 Aufbewahrungs Bezeichnung mit **hoher Vertraulichkeit** . 
- Blockiert Benutzer, wenn Sie versuchen, ein digitales Objekt auf der **Forschungs** Website außerhalb von Contoso freizugeben.

Informationen zu den Konfigurationsdetails finden Sie unter [Schützen von SharePoint-Dateien mit Aufbewahrungs Bezeichnungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a>Schritt 3: Erstellen einer sublabelgruppe für Office 365 Sensitivität für die Website

Contoso-Administratoren haben eine neue unter Bezeichnung für Office 365 Sensitivität namens " **Research Teams** of the **streng Confidential** Label" erstellt, die:

- Verschlüsselung erforderlich.
- Erlaubt gemeinsame Author-Berechtigungen für die Gruppe " **Research** Office 365".
- Gilt für die Gruppe " **Research** Office 365"

Hier ist die resultierende Konfiguration der **Forschungs** Teamwebsite für streng vertrauliche Ressourcen.

![Die resultierende Konfiguration der Forschungsteam Website für streng vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Dateien in Ordnern der **Forschungs** Website sind geschützt durch:

- Die Websiteberechtigungen, die nur den Zugriff auf Mitglieder der Gruppe " **Research** Office 365" ermöglichen.
- Die DLP-Richtlinie für **Forschung** , die die **streng vertrauliche** Aufbewahrungs Bezeichnung und Einstellungen verwendet, die verhindern, dass die Datei für externe Benutzer freigegeben wird.
- Die Sensitivitäts-Sublabel für **Forschungs Teams** mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der **Forschungs** Website verschoben oder kopiert wird.

Hier ist ein Beispiel für eine Datei, die auf der **Forschungs** Website gespeichert ist, wobei die Sensitivitäts-unter Bezeichnung **Research Teams** zugewiesen ist.

![Die resultierende Konfiguration der Forschungsteam Website für streng vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Schritt 4: Migrieren der lokalen SharePoint-Forschungsdaten

Contoso-Administratoren haben alle lokalen Forschungs Dateien in der lokalen SharePoint Server 2016-Website in Ordner in der neuen **Research** -SharePoint-Website verschoben.

## <a name="step-5-trained-their-researchers"></a>Schritt 5: Ausbildung ihrer Forscher

Contoso-Sicherheitsmitarbeiter haben die Mitglieder der Gruppe " **Research** Office 365" in einem obligatorischen Kurs geschult, der Sie schrittweise durchlaufen hat:

- So greifen Sie auf die neue **Forschungs** Website und die vorhandenen Dateien zu.
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Eine Demonstration der Art und Weise, **wie die DLP** -Richtlinie verhindert, dass Dateien extern freigegeben werden.
- Vorgehensweise Beschriften von Dateien mit der Sensitivitäts-unter Bezeichnung **Research Teams** .
- Eine Demonstration der Art und Weise, wie die unter Bezeichnung " **Research Teams** " eine Datei schützt, auch wenn Sie von der Website durchgesickert ist.

Das Endergebnis ist eine sichere Umgebung, in der die Forscher über Contoso hinweg in einer sicheren Umgebung mit Dateien zusammenarbeiten können, die Forschungsinformationen enthalten. 

Wenn ein Forschungsdokument mit der unter Bezeichnung " **Research Teams** " den **Forschungs** Standort verlässt, ist es verschlüsselt und nur für Mitglieder der Gruppe " **Research** Office 365" mit gültigen Anmeldeinformationen für das Benutzerkonto zugänglich.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.

## <a name="see-also"></a>Siehe auch

[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
