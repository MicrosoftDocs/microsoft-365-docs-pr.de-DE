---
title: Exchange Online-E-Mailverschlüsselung mit AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Exchange Online IRM für die Verwendung des lokalen Active Directory Rights Management Service (AD RMS) konfigurieren, um Ihre Organisationsanforderungen zu erfüllen.
ms.openlocfilehash: d98cf5c762cd4dac0cbad6d25a3cc766d5c5310a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876274"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Exchange Online-E-Mailverschlüsselung mit AD RMS

Um Informationsverluste zu verhindern, enthält Exchange Online eine IRM-Funktion (Verwaltung von Informationsrechten), die Online- und Offlineschutz für E-Mails und Anlagen bereitstellt. Sie können irm Exchange Online, um bei Bedarf den lokalen Active Directory Rights Management Service (AD RMS) zu verwenden, um Die Anforderungen Ihrer Organisation zu erfüllen. Dies ist nicht die Regel. Wenn Sie keine Anforderung zur Verwendung von AD RMS haben, verwenden Sie [stattdessen Office 365-Nachrichtenverschlüsselung.](ome.md) 

IRM-Schutz kann von Benutzern in Microsoft Outlook oder Outlook im Web und zudem von Administratoren mithilfe von Transportschutzregeln oder Outlook-Schutzregeln angewendet werden. Mithilfe von IRM können Sie und Ihre Benutzer steuern, wer auf vertrauliche Daten in einer E-Mail zugreifen und E-Mails weiterleiten, drucken oder kopieren kann.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Änderungen an der Funktionsweise von IRM mit Office 365-Nachrichtenverschlüsselung (OME) und Azure Active Directory

Ab September 2017: Wenn Sie die neuen Funktionen von Office 365-Nachrichtenverschlüsselung für Ihre Organisation einrichten, richten Sie auch IRM für die Verwendung mit Azure Rights Management (Azure RMS) ein. Sie richten IRM nicht mehr separat mit Azure RMS ein. Stattdessen arbeiten OME und Rights Management nahtlos zusammen. Ausführliche Informationen über die neuen Funktionen finden Sie in den [Häufig gestellten Fragen zur Office 365-Nachrichtenverschlüsselung](./ome-faq.yml). Wenn Sie die neuen OME-Funktionen in Ihrer Organisation verwenden möchten, finden Sie unter [Einrichten von neuen Funktionen für die Office 365-Nachrichtenverschlüsselung, die auf Azure Information Protection aufbauen](./set-up-new-message-encryption-capabilities.md) weitere Informationen dazu.
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Funktionsweise von IRM in Exchange Online und Active Directory Rights Management Services

Für IRM in Exchange Online werden die lokalen Active Directory-Rechteverwaltungsdienste (AD RMS) verwendet, eine Informationsschutztechnologie in Windows Server 2008 und höher. IRM-Schutz wird auf E-Mails angewendet, indem eine AD RMS-Berechtigungsrichtlinienvorlage auf eine E-Mail angewendet wird. Rechte werden der Nachricht selbst zugeordnet, sodass der Schutz sowohl online und offline als auch innerhalb und außerhalb der Firewall der Organisation stattfindet.
  
Benutzer können eine Vorlage auf eine E-Mail anwenden, um zu steuern, welche Berechtigungen Empfänger für die E-Mail erhalten. Aktionen wie das Extrahieren von Informationen aus einer Nachricht, Weiterleiten, Speichern oder Drucken einer Nachricht können durch Anwenden einer AD RMS-Rechterichtlinie auf die Nachricht gesteuert werden.
  
Sie können IRM für die Verwendung eines AD RMS-Servers mit Windows Server 2008 oder höher konfigurieren. Dieser AD RMS-Server wird zum Verwalten der AD RMS-Rechterichtlinienvorlagen für die cloudbasierte Organisation verwendet. Der AD RMS-Server wird von Outlook auch verwendet, um Benutzern das Anwenden von IRM-Schutz auf die von ihnen gesendeten Nachrichten zu ermöglichen. Weitere Informationen finden Sie [unter Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Nach der Aktivierung kann IRM-Schutz auf Nachrichten wie folgt angewendet werden:
  
- **Benutzer können eine Vorlage manuell mit Outlook und Outlook im Web anwenden** Benutzer können eine AD RMS-Rechterichtlinienvorlage auf eine E-Mail-Nachricht anwenden, indem sie die Vorlage aus der Liste **Berechtigungen festlegen** auswählen. Wenn Benutzer eine IRM-geschützte Nachricht senden, erhalten alle an die Nachricht angefügten Dateien in einem unterstützten Format den gleichen IRM-Schutz wie die Nachricht. IRM-Schutz wird auf Dateien aus Microsoft Office Word, Excel und PowerPoint sowie XPS-Dateien und angefügte E-Mails angewendet. 
    
- **Administratoren können mithilfe von Transportregeln automatisch IRM-Schutz auf Outlook und Outlook im Web anwenden** Sie können Transportregeln erstellen, um IRM-Schutz für Nachrichten bereitzustellen. Konfigurieren Sie die Transportschutzregelaktion, um eine AD RMS-Rechterichtlinienvorlage auf Nachrichten anzuwenden, die die Regelbedingung erfüllen. Nach dem Aktivieren von IRM sind die AD RMS-Rechterichtlinienvorlagen zur Verwendung mit der Transportschutzregelaktion **Rechteschutz auf Nachricht anwenden mit** verfügbar.
    
- **Administratoren können Outlook-Schutzregeln erstellen.** Durch Outlook-Schutzregeln wird basierend auf Nachrichtenbedingungen wie der Abteilung des Absenders, dem Empfänger und dem Empfängerbereich (innerhalb oder außerhalb der Organisation) automatisch IRM-Schutz auf Nachrichten in Outlook 2010 angewendet (nicht in Outlook im Web). Weitere Informationen finden Sie unter [Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help).
