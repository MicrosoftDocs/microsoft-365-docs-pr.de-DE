---
title: Exchange Multi-Geo
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Erfahren Sie mehr über multi-geo-Funktionen in Exchange Online, z. B. Funktionseinschränkungen und Postfachplatzierung.
ms.openlocfilehash: 4c8f873039cd14251931125f5af2c04b7cbfe719
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694305"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Multi-Geo-Funktionen in Exchange Online

In einer Multi-Geo-Umgebung können Sie den Speicherort des Exchange Online-Postfachinhalts (Daten im Ruhezustand) benutzerabhängig auswählen.

Sie können Postfächer an Satelliten-Geo-Speicherorten platzieren, indem Sie:

- Ein neues Exchange Online-Postfach direkt an einem Satelliten-Geo-Speicherort erstellen.

- Ein vorhandenes Exchange Online-Postfach auf einen Satelliten-Geo-Speicherort verschieben, indem Sie den bevorzugten Datenspeicherort des Benutzers ändern.

- Ein Postfach von einer lokalen Exchange-Organisation direkt in einen Satelliten-Geo-Speicherort einbinden.

## <a name="mailbox-placement-and-moves"></a>Platzieren und Verschieben von Postfächern

Nachdem Microsoft die erforderlichen Konfigurationsschritte für die Multi-Geo-Konfiguration abgeschlossen hat, wird Exchange Online das Attribut **PreferredDataLocation** für Benutzerobjekte in Azure AD berücksichtigen.

Exchange Online synchronisiert die Eigenschaft **PreferredDataLocation** von Azure AD mit der Eigenschaft **MailboxRegion** im Exchange Online-Verzeichnisdienst. Der Wert von **MailboxRegion** bestimmt den Geo-Speicherort, an dem Benutzerpostfächer und alle zugehörigen Archivpostfächer platziert werden. Es ist nicht möglich, den primären Postfach eines Benutzers zu konfigurieren und Postfächer so zu archivieren, dass sie sich an verschiedenen Geo-Speicherorten befinden. Pro Benutzerobjekt kann nur ein Geo-Speicherort konfiguriert werden.

- Wenn **PreferredDataLocation** auf einem Benutzer mit einem bestehenden Postfach konfiguriert ist, wird das Postfach in eine Verlagerungswarteschlange gestellt und automatisch an den angegebenen Geo-Speicherort verschoben.

- Wenn **PreferredDataLocation** für einen Benutzer ohne bestehendes Postfach konfiguriert ist, wird es bei der Bereitstellung des Postfachs an dem angegebenen Geo-Speicherort bereitgestellt.

- Wenn **PreferredDataLocation** nicht für einen Benutzer angegeben ist, wird es bei der Bereitstellung des Postfachs in dem zentralen Geo-Speicherort bereitgestellt.

- Wenn der **PreferredDataLocation-Code** falsch ist (z. B. ein Tippfehler von NAN anstelle von NAM), wird das Postfach am zentralen geografischen Standort bereitgestellt.

**Hinweis**: Multi-Geo-Funktionen und regional gehostete Besprechungen von Skype for Business Online verwenden beide die Eigenschaft **PreferredDataLocation** auf Benutzerobjekten, um Dienste zu finden. Wenn Sie die **PreferredDataLocation**-Werte für Benutzerobjekte für regional gehostete Besprechungen konfigurieren, wird das Postfach für diese Benutzer automatisch an den angegebenen Geo-Speicherort verschoben, nachdem Multi-Geo auf dem Microsoft 365-Mandanten aktiviert wurde.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Funktionseinschränkungen für Multi-Geo in Exchange Online

- Sicherheits- und Compliance-Funktionen (z. B. Auditing und eDiscovery), die im Exchange Admin Center (EAC) verfügbar sind, sind in Multi-Geo-Organisationen nicht verfügbar. Stattdessen müssen Sie das [Microsoft 365 Security & Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) verwenden, um Sicherheits- und Compliance-Funktionen zu konfigurieren.

- Outlook für Mac-Benutzer können einen vorübergehenden Verlust des Zugriffs auf ihren Online-Archivordner erleiden, während Sie ihr Postfach an einen neuen Geo-Speicherort verschieben. Diese Situation tritt auf, wenn sich die Primär- und Archivpostfächer des Benutzers an verschiedenen Geo-Speicherorten befinden, da Geo-übergreifende Postfachverschiebungen zu unterschiedlichen Zeiten durchgeführt werden können.

- Benutzer können *Postfachordner* nicht über Geo-Speicherorte hinweg in Outlook im Web freigeben (früher bekannt als Outlook Web App oder OWA). Beispielsweise kann ein Benutzer in der Europäischen Union Outlook im Web nicht verwenden, um einen freigegebenen Ordner in einem Postfach zu öffnen, das sich in den Vereinigten Staaten befindet. Outlook im Web-Benutzer können jedoch *andere Postfächer* an verschiedenen Geo-Speicherorten über ein separates Browserfenster öffnen, wie unter [Öffnen des Postfachs einer anderen Person in einem separaten Browserfenster in Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362) beschrieben wird.

  **Hinweis**: Die Geo-übergreifende Freigabe von Postfachordnern wird in Outlook on Windows unterstützt.

- Öffentliche Ordner werden in Multi-Geo-Organisationen unterstützt. Die öffentlichen Ordner müssen jedoch in dem zentralen Geo-Speicherort verbleiben. Sie können öffentliche Ordner nicht an Satelliten-Geo-Speicherorten verschieben.

- In einer Multi-Geo-Umgebung wird die Geo-übergreifende Postfachüberwachung nicht unterstützt. Wenn beispielsweise einem Benutzer Berechtigungen für den Zugriff auf ein freigegebenes Postfach an einem anderen Geo-Speicherort zugewiesen wurden, werden die von diesem Benutzer ausgeführten Postfachaktionen im Postfachüberwachungsprotokoll des freigegebenen Postfachs nicht protokolliert. Weitere Informationen finden Sie unter [Postfachüberwachungen verwalten](../compliance/enable-mailbox-auditing.md?view=o365-worldwide).
