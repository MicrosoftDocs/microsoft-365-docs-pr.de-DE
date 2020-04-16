---
title: Schützen von Informationen
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Startseite für den Schutz von Informationen
ms.openlocfilehash: f5153373d73ec542f2a21561ce32c37368ff02e4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601672"
---
# <a name="protect-information"></a>Schützen von Informationen

Microsoft 365 und Office 365 umfassen Funktionen, die auf bestimmte Datentypen angewendet werden können, um Informationen zu schützen.


|**Funktion**|**Weitere Informationen**|
|:-----|:-----|
|[Vertraulichkeitskennzeichnungen](sensitivity-labels.md) <br/> |Mit Vertraulichkeitskennzeichnungen können Die vertrauliche Inhalte klassifizieren und schützen. Schutzoptionen umfassen Bezeichnungen, Wasserzeichen und Verschlüsselungen. Vertraulichkeitskennzeichnungen verwenden Azure Information Protection. Wenn Sie Azure Information Protection-Bezeichnungen verwenden, wird empfohlen, dass Sie vorerst keine neuen Bezeichnungen in anderen Admin Centern erstellen, bis Sie die Migration abgeschlossen haben. Informationen hierzu finden Sie unter [Azure Information Protection – Migration](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels). <br/> [Aufbewahrungskennzeichnungen](retention-policies.md) unterscheiden sich von Vertraulichkeitskennzeichnungen. Aufbewahrungskennzeichnungen helfen Ihnen beim Aufbewahren oder Löschen von Inhalten basierend auf den von Ihnen festgelegten Richtlinien. Diese helfen Organisationen dabei, branchenspezifische Vorschriften und interne Richtlinien einzuhalten.|
|[Verhinderung von Datenverlusten](data-loss-prevention-policies.md) (Data Loss Prevention, DLP)  <br/> |Mit DLP-Richtlinien können Sie in Office 365 vertrauliche Informationen automatisch identifizieren, überwachen und schützen. Richtlinien zur Verhinderung von Datenverlust (DLP-Richtlinien) können Vertraulichkeitskennzeichnungen und Typenzuordnungen vertraulicher Informationen verwenden, um vertrauliche Informationen zu identifizieren. <br/> |
|[Typen vertraulicher Informationen](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 beinhaltet zahlreiche Typen vertraulicher Informationen, die Sie unmittelbar in DLP-Richtlinien verwendet werden können sowie für die automatische Klassifizierung mit Vertraulichkeitskennzeichnungen und Aufbewahrungskennzeichnungen. Typenzuordnungen vertraulicher Informationen können auch mit dem [Azure Information Protection-Scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) verwendet werden, um Dateien vor Ort zu klassifizieren und zu schützen. Die Typenzuordnung vertraulicher Informationen legt fest, wie bestimmte Informationstypen (z. B. Krankenversicherungsnummern und Kreditkartennummern) von einem automatisierten Prozess erkannt werden.   <br/> |
|[Office 365-Nachrichtenverschlüsselung](ome.md) (OME)  <br/> |Mit der Office 365-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten von bzw. zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können. <br/> |
|[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/)<br/> |Azure Information Protection (manchmal auch als AIP bezeichnet) unterstützt Ihre Organisation dabei, Dokumente und E-Mails zu klassifizieren, zu kennzeichnen und – optional – zu schützen. Administratoren können Kennzeichnungen automatisch anwenden, indem Sie Regeln und Bedingungen definieren. Benutzer können Kennzeichnungen manuell auf Dateien und E-Mails anwenden. Darüber hinaus können Sie Benutzern empfehlen, wann Kennzeichnungen angewendet werden sollten.<br/> Wenn Sie Vertraulichkeitskennzeichnungen oder die Office-Nachrichtenverschlüsselung verwenden, nutzen Sie bereits Klassifizierungs- und Schutzfunktionen. Wenn Sie noch keine Azure Information Protection-Kennzeichnungen für Office 365 migriert haben, fahren Sie mit der Verwaltung der entsprechenden Daten in Azure Information Protection fort.  <br/>Mit dem [Azure Information Protection-Scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) können Sie Dateien auf Windows-Servern, in Netzwerkfreigaben und auf SharePoint-Server-Websites und -Bibliotheken lokal klassifizieren und schützen. Dies kann ein erster Schritt zur Ermittlung von Daten, die zu Office 365 migriert werden sollen, sein.
|Azure Information Protection mit vom Kunden verwalteten Verschlüsselungsschlüssel <br/> |Einige Organisationen müssen aufgrund geschäftlicher Erfordernisse oder Compliance-Anforderungen die Kontrolle über einen Verschlüsselungsschlüssel beibehalten. Dies ist nicht die Regel. Azure Information Protection ermöglicht es Organisationen, Ihren eigenen Schlüssel (BYOK) in den Dienst einzubringen. Weitere Informationen finden Sie unter [Ihren eigenen Schlüssel einbringen (Bring your own key, BYOK) für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/byok-price-restrictions). Eine weitere, komplexere Option wird für Kunden geboten, die der Anforderung entsprechend müssen, einen Verschlüsselungsschlüssel vor Ort aufzubewahren, was auch als „Hold your own key“ (HYOK) bezeichnet wird.  Weitere Informationen finden Sie unter [Hold your own key (HYOK) für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions). <br/> |
    

