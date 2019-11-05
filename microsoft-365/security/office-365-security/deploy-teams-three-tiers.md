---
title: Bereitstellen von Teams für drei Schutzebenen für Dateien
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Erstellen und Konfigurieren von Teams mit Microsoft Teams für verschiedene Ebenen des Informationsschutzes für Dateien.
ms.openlocfilehash: 263a787eb7f1fa8289a127816c6f8df60960feda
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925792"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>Bereitstellen von Teams für drei Schutzebenen für Dateien

Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für grundlegende, vertrauliche und streng vertrauliche Teams zu entwerfen. Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md).
  
## <a name="baseline-teams"></a>Grundlegende Teams

Der grundlegende Schutz enthält jeweils öffentliche und private Teams. Öffentliche Teams können von allen Benutzern in der Organisation ermittelt werden und alle haben Zugriff auf diese. Nur Mitglieder der Office 365-Gruppe, die mit dem Team verknüpft sind, können die privaten Websites ermitteln und auf diese zugreifen. Bei diesen beiden Typen von Teams können Mitglieder die Website mit anderen Benutzern teilen.
  
### <a name="public"></a>Öffentlich

Befolgen Sie die Anweisungen in [diesem Artikel](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), um ein grundlegendes Team mit öffentlichem Zugriff und öffentlichen Berechtigungen zu erstellen.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Grundlegender Schutz für ein öffentliches Team.](../media/baseline-public-team.png)
  
### <a name="private"></a>Privat

Befolgen Sie die Anweisungen in [diesem Artikel](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), um ein grundlegendes Team mit privatem Zugriff und privaten Berechtigungen zu erstellen.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.

![Grundlegender Schutz für ein privates Team.](../media/baseline-private-team.png)
  
## <a name="sensitive-teams"></a>Vertrauliche Teams

Für ein vertrauliches Team beginnen Sie mit dem [Erstellen eines privaten Teams](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).

Als Nächstes konfigurieren Sie die zugrunde liegende SharePoint-Website, um die Freigabe durch Teammitglieder zu verhindern.

1.  Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
2.  Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.
3.  Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
4.  Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
5.  Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Schutz vertraulicher Daten für ein Team.](../media/sensitive-team.png)
 

## <a name="highly-confidential-teams"></a>Streng vertrauliche Teams

Für ein streng vertrauliches Team beginnen Sie mit dem [Erstellen eines privaten Teams](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).

Als Nächstes konfigurieren Sie die zugrunde liegende SharePoint-Website, um die Freigabe durch Teammitglieder und das Anfordern von Zugriff von Nicht-Mitgliedern des Teams zu verhindern.

1.  Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
2.  Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.
3.  Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
4.  Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
5.  Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.
6.  Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.

Nachfolgend sehen Sie die daraus resultierende Konfiguration.
  
![Schutz von streng vertraulichen Daten für ein Team.](../media/highly-confidential-team.png)  
  
## <a name="next-step"></a>Nächster Schritt

[Schützen von Dateien in Teams mit Aufbewahrungsbezeichnungen und Schutz vor Datenverlust (DLP)](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>Siehe auch

[Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md)
  
[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
