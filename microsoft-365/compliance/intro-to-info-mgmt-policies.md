---
title: Einführung in Informationsverwaltungsrichtlinien
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
description: Eine Informationsverwaltungsrichtlinie ist ein Satz von Regeln, der für eine bestimmte Art von Inhalten gilt. Mithilfe von Informationsverwaltungsrichtlinien können Organisationen steuern und nachverfolgen, wie lange Inhalt beibehalten wird oder welche Aktionen die Benutzer für diesen Inhalt ausführen können. Informationsverwaltungsrichtlinien können Organisationen helfen, gesetzliche oder behördliche Bestimmungen einzuhalten oder einfach interne Geschäftsprozesse erzwingen.
ms.openlocfilehash: a5cf571b22b7d698daf8a70f8565b250e2388a1a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081533"
---
# <a name="introduction-to-information-management-policies"></a>Einführung in Informationsverwaltungsrichtlinien

Eine Informationsverwaltungsrichtlinie ist ein Satz von Regeln, der für eine bestimmte Art von Inhalten gilt. Mithilfe von Informationsverwaltungsrichtlinien können Organisationen steuern und nachverfolgen, wie lange Inhalt beibehalten wird oder welche Aktionen die Benutzer für diesen Inhalt ausführen können. Informationsverwaltungsrichtlinien können Organisationen helfen, gesetzliche oder behördliche Bestimmungen einzuhalten oder einfach interne Geschäftsprozesse erzwingen. 
  
Beispielsweise kann eine Organisation, die die behördlichen Vorschriften befolgt, in denen die "angemessenen Steuerelemente" ihrer Abschlüsse vorgeführt werden müssen, eine oder mehrere Informationsverwaltungsrichtlinien erstellen, die bestimmte Aktionen in der Erstellung überwachen und Genehmigungsprozess für alle Dokumente im Zusammenhang mit Finanz Anmeldungen.
  
Informationen zu Vorgehensweise finden Sie unter [Erstellen und Anwenden von Informationsverwaltungsrichtlinien](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Features von Informationsverwaltungsrichtlinien
<a name="__top"> </a>

Es gibt vier grundlegende Kategorien von vordefinierten Richtlinienfeatures, die Organisationen einzeln oder in Kombination verwenden können, um Inhalte und Prozesse zu verwalten. 
  
![Arten von Inhaltsrichtlinien](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
Mit dem Überwachungsrichtlinienfeature können Organisationen analysieren, wie Ihre Inhaltsverwaltungssysteme durch Protokollierung von Ereignissen und Vorgängen, die für Dokumente und Listenelemente ausgeführt werden, verwendet werden. Sie können das Überwachungsrichtlinienfeature so konfigurieren, dass Ereignisse protokolliert werden, beispielsweise wenn ein Dokument oder Element bearbeitet, angezeigt, eingecheckt, ausgecheckt, gelöscht oder die Berechtigungen geändert wurden. Alle Überwachungsinformationen werden in einem einzigen Überwachungsprotokoll auf dem Server gespeichert, und Websiteadministratoren können Berichte dazu ausführen. 
  
Das Feature für Ablaufrichtlinien hilft Organisationen dabei, veraltete Inhalte aus ihren Websites auf konsistente, nach verfolgbare Weise zu löschen oder zu entfernen. Auf diese Weise können Sie Kosten und Risiken im Zusammenhang mit der Beibehaltung veralteter Inhalte verwalten. Sie können eine Ablaufrichtlinie konfigurieren, um anzugeben, dass bestimmte Inhaltstypen an einem bestimmten Datum oder innerhalb eines Zeitraums ablaufen, nachdem das Dokument erstellt oder zuletzt geändert wurde.
  
In Organisationen können auch benutzerdefinierte Richtlinienfeatures für spezielle Anforderungen erstellt und bereitgestellt werden. Beispielsweise kann eine Produktionsorganisation eine Informationsverwaltungsrichtlinie für alle Entwürfe von Dokument Entwurfsspezifikationen definieren, die Benutzern das Drucken von Kopien dieser Dokumente auf nicht sicheren Druckern verbieten. Zum Definieren dieser Art von Informationsverwaltungsrichtlinie können Sie ein Richtlinienfeature für Druck Einschränkung erstellen und bereitstellen, das der entsprechenden Informationsverwaltungsrichtlinie für den Inhaltstyp Produktdesign Spezifikation hinzugefügt werden kann.
  
## <a name="locations-to-use-an-information-management-policy"></a>Standorte für die Verwendung einer Informationsverwaltungsrichtlinie
<a name="__toc340213528"> </a>

Um eine Informationsverwaltungsrichtlinie zu implementieren, müssen Sie Sie einer Liste, einer Bibliothek oder einem Inhaltstyp in einer Website hinzufügen. Der Ort, an dem Sie eine Informationsverwaltungsrichtlinie erstellen oder hinzufügen, wirkt sich darauf aus, wie weit die Richtlinie angewendet wird oder wie weit Sie verwendet werden kann. Sie können:
  
 **Erstellen Sie eine Websitesammlungsrichtlinie, und fügen Sie diese Richtlinie dann einem Inhaltstyp, einer Liste oder einer Bibliothek hinzu** . Sie können eine Websitesammlungsrichtlinie in der Liste Richtlinien auf der Website auf oberster Ebene einer Websitesammlung erstellen. Nachdem Sie eine Websitesammlungsrichtlinie erstellt haben, können Sie Sie exportieren, damit Administratoren anderer Websitesammlungen Sie in Ihre Richtlinienliste importieren können. Durch das Erstellen einer exportierbaren Websitesammlungsrichtlinie können Sie die Informationsverwaltungsrichtlinien auf den Websites in Ihrer Organisation standardisieren. 
  
Wenn Sie eine Websitesammlungsrichtlinie zu einem Websiteinhaltstyp hinzufügen und eine Instanz dieses Websiteinhaltstyps zu einer Liste oder Bibliothek hinzugefügt wird, kann der Besitzer dieser Liste oder Bibliothek die Websitesammlungsrichtlinie für die Liste oder Bibliothek nicht ändern. Das Hinzufügen einer Websitesammlungsrichtlinie zu einem Websiteinhaltstyp ist eine gute Möglichkeit, um sicherzustellen, dass Websitesammlungsrichtlinien auf jeder Ebene ihrer Websitehierarchie erzwungen werden.
  
![Link zur Richtlinienvorlage "Inhaltstyp" auf der Seite "Websiteeinstellungen"](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Erstellen Sie eine Informationsverwaltungsrichtlinie für einen Websiteinhaltstyp im Websiteinhaltstyp Katalog der obersten Ebene, und fügen Sie diesen Inhaltstyp dann einer oder mehreren Listen oder Bibliotheken hinzu.** Sie können auch eine Informationsverwaltungsrichtlinie direkt für einen Websiteinhaltstyp erstellen und dann eine Instanz dieses Websiteinhaltstyps mehreren Listen oder Bibliotheken zuordnen. Wenn Sie auf diese Weise eine Informationsverwaltungsrichtlinie erstellen, verfügt jedes Element in der Websitesammlung dieses Inhaltstyps oder eines Inhaltstyps, der von diesem Inhaltstyp erbt, über die Richtlinie. Wenn Sie jedoch eine Informationsverwaltungsrichtlinie direkt für einen Websiteinhaltstyp erstellen, ist es schwieriger, diese Informationsverwaltungsrichtlinie in anderen Websitesammlungen wiederzuverwenden, da Richtlinien, die auf diese Weise erstellt werden, nicht exportiert werden können. 
  
![Link "Websiteinhaltstypen" auf der Seite "Websiteeinstellungen"](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Link "Informationsverwaltungsrichtlinie" auf der Seite "Einstellungen" für einen Websiteinhaltstyp](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Hinweis um zu steuern, welche Richtlinien in einer Websitesammlung verwendet werden, können Websitesammlungsadministratoren die Möglichkeit deaktivieren, Richtlinienfeatures direkt für einen Inhaltstyp festzulegen. Wenn diese Einschränkung wirksam ist, können Benutzer, die Inhaltstypen erstellen, nur Richtlinien aus der Liste der Websitesammlungsrichtlinien auswählen.
  
 **Erstellen einer Informationsverwaltungsrichtlinie für eine Liste oder Bibliothek** Wenn Ihre Organisation eine bestimmte Informationsverwaltungsrichtlinie auf eine sehr beschränkte Menge an Inhalten anwenden muss, können Sie eine Informationsverwaltungsrichtlinie erstellen, die nur für eine einzelne Liste oder Bibliothek gilt. Diese Methode zum Erstellen einer Informationsverwaltungsrichtlinie ist die am wenigsten flexible, da die Richtlinie nur für einen Standort gilt und nicht für andere Speicherorte exportiert oder wieder verwendet werden kann. Manchmal müssen Sie jedoch möglicherweise eindeutige Informationsverwaltungsrichtlinien mit einer begrenzten Anwendbarkeit zur Behebung bestimmter Situationen erstellen. 
  
![Link "Informationsverwaltungsrichtlinien" auf der Seite "Einstellungen" für Dokumentbibliothek](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Hinweise 
  
Sie können eine Informationsverwaltungsrichtlinie für eine Liste oder Bibliothek nur dann erstellen, wenn diese Liste oder Bibliothek mehrere Inhaltstypen nicht unterstützt. Wenn eine Liste oder Bibliothek mehrere Inhaltstypen unterstützt, müssen Sie eine Informationsverwaltungsrichtlinie für jeden einzelnen Listeninhaltstyp definieren, der dieser Liste oder Bibliothek zugeordnet ist. (Instanzen eines Websiteinhaltstyps, die einer bestimmten Liste oder Bibliothek zugeordnet sind, werden als Listeninhaltstypen bezeichnet.)
  
Um zu steuern, welche Richtlinien in einer Websitesammlung verwendet werden, können Websitesammlungsadministratoren die Möglichkeit deaktivieren, Richtlinienfeatures direkt für eine Liste oder Bibliothek festzulegen. Wenn diese Einschränkung wirksam ist, können Benutzer, die Listen oder Bibliotheken verwalten, nur Richtlinien aus der Liste der Websitesammlungsrichtlinien auswählen.
  
[Eine Informationsverwaltungsrichtlinie ist ein Satz von Regeln für einen Inhaltstyp. Mithilfe von Informationsverwaltungsrichtlinien können Organisationen Elemente steuern und nachverfolgen, beispielsweise wie lange Inhalte aufbewahrt werden oder welche Aktionen Benutzer mit diesen Inhalten durchführen können. Informationsverwaltungsrichtlinien können Organisationen dabei helfen, gesetzliche oder behördliche Bestimmungen einzuhalten oder einfach interne Geschäftsprozesse zu erzwingen. Beispielsweise kann eine Organisation, die die behördlichen Vorschriften befolgt, in denen die "angemessenen Steuerelemente" ihrer Abschlüsse vorgeführt werden müssen, eine oder mehrere Informationsverwaltungsrichtlinien erstellen, die bestimmte Aktionen in der Erstellung überwachen und Genehmigungsprozess für alle Dokumente im Zusammenhang mit Finanz Anmeldungen. Informationen zu Vorgehensweise finden Sie unter Erstellen und Anwenden von Informationsverwaltungsrichtlinien.](intro-to-info-mgmt-policies.md#__top)
  

