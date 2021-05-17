---
title: Einführung in Informationsverwaltungsrichtlinien
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Mithilfe von Informationsverwaltungsrichtlinien Dinge steuern und nachverfolgen können, z. B. wie lange Inhalte aufbewahrt werden oder welche Aktionen Benutzer mit diesen Inhalten ausführen können.
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815512"
---
# <a name="introduction-to-information-management-policies"></a>Einführung in Informationsverwaltungsrichtlinien

Eine Informationsverwaltungsrichtlinie ist ein Satz von Regeln, der für eine bestimmte Art von Inhalten gilt. Mithilfe von Informationsverwaltungsrichtlinien können Organisationen steuern und nachverfolgen, wie lange Inhalt beibehalten wird oder welche Aktionen die Benutzer für diesen Inhalt ausführen können. Informationsverwaltungsrichtlinien können Organisationen helfen, gesetzliche oder behördliche Bestimmungen einzuhalten oder einfach interne Geschäftsprozesse erzwingen. 
  
Beispielsweise kann eine Organisation, die den gesetzlichen Bestimmungen folgen muss, die erfordern, dass sie "angemessene Kontrollen" ihrer Abschlüsse nachweisen muss, eine oder mehrere Informationsverwaltungsrichtlinien erstellen, die bestimmte Aktionen im Erstellungs- und Genehmigungsprozess für alle Dokumente im Zusammenhang mit Finanzanmeldungen überwachen.
  
Informationen zur Funktionsweise finden Sie unter Erstellen und Anwenden [von Informationsverwaltungsrichtlinien](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Features von Informationsverwaltungsrichtlinien
<a name="__top"> </a>

Es gibt vier grundlegende Kategorien vordefinierter Richtlinienfeatures, die Organisationen einzeln oder in Kombination zum Verwalten von Inhalten und Prozessen verwenden können. 
  
![Typen von Inhaltsrichtlinien](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
Mit dem Überwachungsrichtlinienfeature können Organisationen analysieren, wie ihre Inhaltsverwaltungssysteme durch Protokollierung von Ereignissen und Vorgängen verwendet werden, die für Dokumente und Listenelemente ausgeführt werden. Sie können das Überwachungsrichtlinienfeature so konfigurieren, dass Ereignisse protokolliert werden, z. B. wenn ein Dokument oder Element bearbeitet, angezeigt, eingecheckt, ausgecheckt, gelöscht oder seine Berechtigungen geändert wurden. Alle Überwachungsinformationen werden in einem einzigen Überwachungsprotokoll auf dem Server gespeichert, und Websiteadministratoren können Berichte dazu ausführen. 
  
Das Ablaufrichtlinienfeature hilft Organisationen dabei, veraltete Inhalte auf konsistente, nachverfolgbare Weise von ihren Websites zu löschen oder zu entfernen. Auf diese Weise können Sie sowohl die Kosten als auch das Risiko verwalten, die mit der Aufbewahrung veralteter Inhalte verbunden sind. Sie können eine Ablaufrichtlinie konfigurieren, um anzugeben, dass bestimmte Inhaltstypen an einem bestimmten Datum oder innerhalb eines Zeitraums ablaufen, nachdem das Dokument erstellt oder zuletzt geändert wurde.
  
In Organisationen können auch benutzerdefinierte Richtlinienfeatures für spezielle Anforderungen erstellt und bereitgestellt werden. Beispielsweise kann eine Produktionsorganisation eine Informationsverwaltungsrichtlinie für alle Entwurfsdokumente für Produktdesignspezifikationen definieren, die benutzern das Drucken von Kopien dieser Dokumente auf nicht unsicheren Druckern verbieten. Um diese Art von Informationsverwaltungsrichtlinie zu definieren, können Sie ein Richtlinienfeature für Druckeinschränkungen erstellen und bereitstellen, das der relevanten Informationsverwaltungsrichtlinie für den Inhaltstyp der Produktentwurfsspezifikation hinzugefügt werden kann.
  
## <a name="locations-to-use-an-information-management-policy"></a>Speicherorte für die Verwendung einer Informationsverwaltungsrichtlinie
<a name="__toc340213528"> </a>

Um eine Informationsverwaltungsrichtlinie zu implementieren, müssen Sie sie einer Liste, Bibliothek oder einem Inhaltstyp auf einer Website hinzufügen. Der Speicherort, an dem Sie eine Informationsverwaltungsrichtlinie erstellen oder hinzufügen, wirkt sich darauf aus, wie allgemein die Richtlinie angewendet oder wie allgemein sie verwendet werden kann. Sie können:
  
 **Erstellen einer Websitesammlungsrichtlinie und anschließendes** Hinzufügen dieser Richtlinie zu einem Inhaltstyp, einer Liste oder Bibliothek Sie können eine Websitesammlungsrichtlinie in der Liste Richtlinien auf der Website auf oberster Ebene einer Websitesammlung erstellen. Nachdem Sie eine Websitesammlungsrichtlinie erstellt haben, können Sie sie exportieren, sodass Administratoren anderer Websitesammlungen sie in ihre Richtlinienliste importieren können. Durch das Erstellen einer exportierbaren Websitesammlungsrichtlinie können Sie die Informationsverwaltungsrichtlinien auf den Websites in Ihrer Organisation standardisieren. 
  
Wenn Sie einem Websiteinhaltstyp eine Websitesammlungsrichtlinie hinzufügen und einer Liste oder Bibliothek eine Instanz dieses Websiteinhaltstyps hinzugefügt wird, kann der Besitzer dieser Liste oder Bibliothek die Websitesammlungsrichtlinie für die Liste oder Bibliothek nicht ändern. Das Hinzufügen einer Websitesammlungsrichtlinie zu einem Websiteinhaltstyp ist eine gute Möglichkeit, um sicherzustellen, dass Websitesammlungsrichtlinien auf jeder Ebene der Websitehierarchie erzwungen werden.
  
![Link zur Inhaltstyprichtlinie auf Einstellungen Seite](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 Erstellen sie eine Informationsverwaltungsrichtlinie für einen Websiteinhaltstyp im Websiteinhaltstypkatalog der obersten Ebene, und fügen Sie diesen Inhaltstyp dann einer **oder mehreren** Listen oder Bibliotheken hinzu. Sie können auch eine Informationsverwaltungsrichtlinie direkt für einen Websiteinhaltstyp erstellen und dann eine Instanz dieses Websiteinhaltstyps mehreren Listen oder Bibliotheken zuordnen. Wenn Sie eine Informationsverwaltungsrichtlinie auf diese Weise erstellen, verfügt jedes Element in der Websitesammlung dieses Inhaltstyps oder ein Inhaltstyp, der von diesem Inhaltstyp erbt, über die Richtlinie. Wenn Sie jedoch eine Informationsverwaltungsrichtlinie direkt für einen Websiteinhaltstyp erstellen, ist es schwieriger, diese Informationsverwaltungsrichtlinie in anderen Websitesammlungen wiederzuverwenden, da Richtlinien, die auf diese Weise erstellt werden, nicht exportiert werden können. 
  
![Link zu Websiteinhaltstypen auf Einstellungen Seite](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Link zur Informationsverwaltungsrichtlinie auf der Einstellungsseite für einen Websiteinhaltstyp](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Hinweis Um zu steuern, welche Richtlinien in einer Websitesammlung verwendet werden, können Websitesammlungsadministratoren die Möglichkeit deaktivieren, Richtlinienfeatures direkt für einen Inhaltstyp festlegen. Wenn diese Einschränkung wirksam ist, sind Benutzer, die Inhaltstypen erstellen, auf die Auswahl von Richtlinien aus der Liste Websitesammlungsrichtlinien beschränkt.
  
 **Erstellen einer Informationsverwaltungsrichtlinie für eine Liste oder Bibliothek** Wenn Ihre Organisation eine bestimmte Informationsverwaltungsrichtlinie auf einen sehr begrenzten Satz von Inhalten anwenden muss, können Sie eine Informationsverwaltungsrichtlinie erstellen, die nur für eine einzelne Liste oder Bibliothek gilt. Diese Methode zum Erstellen einer Informationsverwaltungsrichtlinie ist am wenigsten flexibel, da die Richtlinie nur für einen Speicherort gilt und nicht für andere Speicherorte exportiert oder wiederverwendet werden kann. Manchmal müssen Sie jedoch möglicherweise eindeutige Informationsverwaltungsrichtlinien mit eingeschränkter Anwendbarkeit erstellen, um bestimmte Situationen zu bewältigen. 
  
![Link zu Informationsverwaltungsrichtlinien auf der Einstellungsseite für die Dokumentbibliothek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Hinweise 
  
Sie können eine Informationsverwaltungsrichtlinie für eine Liste oder Bibliothek nur erstellen, wenn diese Liste oder Bibliothek nicht mehrere Inhaltstypen unterstützt. Wenn eine Liste oder Bibliothek mehrere Inhaltstypen unterstützt, müssen Sie eine Informationsverwaltungsrichtlinie für jeden einzelnen Listeninhaltstyp definieren, der dieser Liste oder Bibliothek zugeordnet ist. (Instanzen eines Websiteinhaltstyps, die einer bestimmten Liste oder Bibliothek zugeordnet sind, werden als Listeninhaltstypen bezeichnet.)
  
Um zu steuern, welche Richtlinien in einer Websitesammlung verwendet werden, können Websitesammlungsadministratoren die Möglichkeit deaktivieren, Richtlinienfeatures direkt in einer Liste oder Bibliothek festlegen. Wenn diese Einschränkung wirksam ist, sind Benutzer, die Listen oder Bibliotheken verwalten, auf die Auswahl von Richtlinien aus der Liste Websitesammlungsrichtlinien beschränkt.
  
[Eine Informationsverwaltungsrichtlinie ist ein Satz von Regeln für einen Inhaltstyp. Informationsverwaltungsrichtlinien ermöglichen Es Organisationen, Dinge zu steuern und nachverfolgt zu haben, z. B. wie lange Inhalte aufbewahrt werden oder welche Aktionen Benutzer mit diesen Inhalten ausführen können. Informationsverwaltungsrichtlinien können Organisationen bei der Einhaltung gesetzlicher oder behördlicher Bestimmungen unterstützen oder interne Geschäftsprozesse einfach erzwingen. Beispielsweise kann eine Organisation, die den gesetzlichen Bestimmungen folgen muss, die erfordern, dass sie "angemessene Kontrollen" ihrer Abschlüsse nachweisen muss, eine oder mehrere Informationsverwaltungsrichtlinien erstellen, die bestimmte Aktionen im Erstellungs- und Genehmigungsprozess für alle Dokumente im Zusammenhang mit Finanzanmeldungen überwachen. Informationen zur Funktionsweise finden Sie unter Erstellen und Anwenden von Informationsverwaltungsrichtlinien.](intro-to-info-mgmt-policies.md#__top)
  

