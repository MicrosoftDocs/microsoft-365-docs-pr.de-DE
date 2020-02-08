---
title: Bereitstellen von SharePoint Online-Websites für drei Schutzebenen
f1.keywords:
- NOCSH
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
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Zusammenfassung: Erstellen und Konfigurieren von SharePoint Online-Teamwebsites für verschiedene Ebenen des Informationsschutzes.'
ms.openlocfilehash: 1f67dd1956059162902aefdb194e5e514d063778
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855254"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Bereitstellen von SharePoint Online-Websites für drei Schutzebenen

Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für grundlegende, vertrauliche und streng vertrauliche SharePoint Online-Teamwebsites zu entwerfen. Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Grundlegende SharePoint Online-Teamwebsites

Der grundlegende Schutz enthält jeweils öffentliche und private Teamwebsites. Öffentliche Teamwebsites können von allen Benutzern in der Organisation ermittelt werden und alle haben Zugriff auf diese. Nur Mitglieder der Office 365-Gruppe, die mit der Teamwebsite verknüpft sind, können die privaten Websites ermitteln und auf diese zugreifen. Diese beiden Arten von Teamwebsites erlauben Mitgliedern, die Website für andere Personen freizugeben.
  
### <a name="public"></a>Public (Öffentlich)

Um eine grundlegende SharePoint Online-Teamwebsite mit öffentlichem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Grundschutz für eine öffentliche SharePoint Online-Teamwebsite.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Privat

Um eine grundlegende SharePoint Online-Teamwebsite mit privatem Zugriff und Berechtigungen zu erstellen, befolgen Sie bitte [diese Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).
  
Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Grundschutz für eine private SharePoint Online-Teamwebsite.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Vertrauliche SharePoint Online-Teamwebsites

Eine sensible SharePoint Online-Teamwebsite wird zunächst als private Teamwebsite erstellt.
  
Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.

1.  Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
2.  Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
3.  Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.

Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:

- Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.
- Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist aktiviert.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Schutzebene „Vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Streng vertrauliche SharePoint Online-Teamwebsites

Bei einer streng vertraulichen SharePoint Online-Teamwebsite handelt es sich um eine private Teamwebsite mit zusätzlichen Berechtigungseinstellungen.

Erstellen Sie zuerst die private SharePoint Online-Teamwebsite laut den [folgenden Anweisungen](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Konfigurieren Sie als daraufhin auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen anhand der folgenden Schritte.

1.  Klicken Sie in der Symbolleiste der SharePoint-Teamwebsite auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
2.  Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
3.  Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.
4. Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.

Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:

- Die Möglichkeit, dass Mitglieder Inhalte mit anderen Mitgliedern teilen, ist deaktiviert.
- Die Möglichkeit, dass Nicht-Mitglieder Zugriff anfordern, ist deaktiviert.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Schutzebene „Streng vertraulich“ für eine isolierte SharePoint Online-Teamwebsite.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
Die Mitglieder der Website können nun über Gruppenmitgliedschaft in einer der Zugriffsgruppen sicher an den Ressourcen der Website zusammenarbeiten.
  
## <a name="next-step"></a>Nächster Schritt

[Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Siehe auch

[Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
