---
title: Microsoft Viva Topics – Übersicht
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Übersicht über Viva-Themen.
ms.openlocfilehash: 91442ba12b3d5df1d9934022751f4bc381cd40e8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453969"
---
# <a name="microsoft-viva-topics-overview"></a>Microsoft Viva Topics – Übersicht 

Viva Topics verwendet Microsoft KI-Technologie, Microsoft 365, Microsoft Graph, Search und andere Komponenten und Dienste, um Ihren Benutzern Wissen in Microsoft 365-Apps zu vermitteln, die sie täglich verwenden, beginnend mit modernen SharePoint-Seiten und Microsoft Search.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva Topics hilft bei der Lösung eines wichtigen Geschäftsproblems in vielen Unternehmen – indem Sie die Informationen für Benutzer bereitstellen, wenn diese benötigt werden. Beispielsweise müssen neue Mitarbeiter schnell viele neue Informationen lernen und beim Lesen von Unternehmensinformationen auf Begriffe stoßen, über die sie nichts wissen. Um mehr zu erfahren, muss der Benutzer möglicherweise seine Aktivitäten unterbrechen und wertvolle Zeit damit verbringen, nach Details zu suchen, z. B. nach Informationen über den Begriff, wer in der Organisation Fachexperte ist, und möglicherweise nach Websites und Dokumenten im Zusammenhang mit dem Begriff.

Viva Topics verwendet KI, um automatisch nach **Themen** in Ihrer Organisation zu suchen und diese zu identifizieren. Es werden Informationen über sie zusammengestellt, z. B. eine kurze Beschreibung, Personen, die an dem Thema arbeiten, sowie Websites, Dateien und Seiten, die sich darauf beziehen. Ein Wissensmanager oder Mitwirkender kann die Themeninformationen nach Bedarf aktualisieren. Die Themen stehen Ihren Benutzern zur Verfügung. Dies bedeutet, dass für jede Instanz des Themas, die auf einer modernen SharePoint-Website in Nachrichten und Seiten angezeigt wird, der Text hervorgehoben wird. Benutzer können das Thema auswählen, um mehr darüber in den Themendetails zu erfahren. Themen finden Sie auch in der SharePoint-Suche.


## <a name="how-topics-are-displayed-to-users"></a>Wie Themen den Benutzern angezeigt werden

Wenn ein Thema in Inhalten auf SharePoint-Nachrichten und -Seiten erwähnt wird, wird es hervorgehoben. Sie können die Themenübersicht über die Markierung öffnen. Öffnen Sie die Themendetails aus dem Titel der Zusammenfassung. Das erwähnte Thema kann automatisch identifiziert werden oder wurde der Seite mit einem direkten Verweis auf das Thema durch den Seitenautor hinzugefügt. 

   ![Themenhighlights](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Wissensindizierung

Viva Topics verwendet die Microsoft KI-Technologie, um **Themen** in Ihrer Microsoft 365-Umgebung zu identifizieren.

Ein Thema ist eine Phrase oder ein Begriff, der organisatorisch bedeutsam oder wichtig ist. Es hat eine spezifische Bedeutung für die Organisation und verfügt über Ressourcen, die den Menschen helfen können, zu verstehen, was es ist, und weitere Informationen darüber zu finden. Es gibt viele verschiedene Arten von Themen, die für Ihr Unternehmen wichtig sind. Zunächst konzentriert sich die Microsoft KI-Technologie auf die folgenden Typen:
- Project
- Event
- Organisation
- Speicherort
- Produkt
- Kreative Arbeit
- Forschungsgebiet


Wenn ein Thema identifiziert wird und KI feststellt, dass es über genügend Informationen verfügt, um ein vorgeschlagenes Thema zu sein, werden auf einer **Themenseite** die Informationen angezeigt, die durch Themenindizierung gesammelt wurden, z.B.:

- Alternative Namen und Akronyme.
- Eine kurze Beschreibung des Themas.
- Personen, die sich mit dem Thema auskennen.
- Dateien, Seiten und Websites, die sich auf das Thema beziehen.

Ihre Wissensmanager können wählen, ob sie alle SharePoint-Sites in Ihrem Mandanten nach Themen durchsuchen oder nur bestimmte auswählen möchten.

Siehe [Themenentdeckung und Kuration](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Rollen

Wenn Sie Viva Topics in Ihrer Microsoft 365-Umgebung verwenden, haben Ihre Benutzer die folgenden Rollen:

- Themenbetrachter: Benutzer, die Themenhighlights auf modernen SharePoint-Sites sehen können, auf die sie mindestens *Lesezugriff* haben, und in Microsoft Search. Sie können Themenhighlights auswählen, um Themendetails auf Themenseiten anzuzeigen. Themenbetrachter können Feedback geben, wie nützlich ein Thema für sie ist.

- Mitwirkende: Benutzer, die das Recht haben, vorhandene Themen zu bearbeiten oder neue zu erstellen. Wissensadministratoren weisen Benutzern über die Viva Topics-Einstellungen im Microsoft 365 Admin Center Berechtigungen für Mitwirkende zu. Beachten Sie, dass Sie auch festlegen können, dass alle Themenbetrachter die Berechtigung zum Bearbeiten und Erstellen von Themen erhalten, damit jeder zu den Themen beitragen kann, die er sieht.

- Wissensmanager: Benutzer, die Themen durch den Themenlebenszyklus führen. Wissensmanager verwenden die Seite **Themen verwalten** im Themencenter, um von der KI vorgeschlagene Themen zu bestätigen, nicht mehr relevante Themen zu entfernen sowie vorhandene Themen zu bearbeiten oder neue zu erstellen. Sie sind die einzigen Benutzer, die Zugriff darauf haben. Wissensadministratoren weisen Benutzern über die Viva Topics-Administratoreinstellungen im Microsoft 365 Admin Center Wissensmanagerberechtigungen zu. 

- Wissensadministratoren: Wissensadministratoren richten Viva Topics ein und verwalten sie über die Administratorsteuerelemente im Microsoft 365 Admin Center. Derzeit kann ein globaler Microsoft 365- oder SharePoint-Administrator als Wissensadministrator fungieren.

Weitere Informationen finden Sie unter [Viva-Themenrollen](topic-experiences-roles.md).

## <a name="topic-management"></a>Themenverwaltung

Die Themenverwaltung erfolgt auf der Seite **Themen verwalten** im **Themenzentrum** Ihrer Organisation. Das Themenzentrum wird während der Einrichtung erstellt und dient als Wissenszentrum für Ihre Organisation. 

Während alle lizenzierten Benutzer Themen, mit denen sie verbunden sind, im Themenzentrum sehen können, können nur Benutzer mit Berechtigungen zum *Verwalten von Themen* (Wissensmanager) die Seite Themen verwalten anzeigen und verwenden.

Wissensverwalter können:

- Themen bestätigen oder entfernen, die in Ihrem Mandanten entdeckt wurden.
- Neue Themen nach Bedarf manuell erstellen (z. B. wenn nicht genügend Informationen bereitgestellt wurden, um über KI erkannt zu werden).
- Vorhandene Themenseiten bearbeiten.</br>

Weitere Informationen finden Sie unter [Verwalten von Themen im Themencenter](manage-topics.md).  


## <a name="admin-controls"></a>Administratorsteuerelemente

Mit den Administratorsteuerelementen im Microsoft 365 Admin Center können Sie Ihr Wissensnetzwerk verwalten. Mit ihnen können Microsoft 365 Global- oder SharePoint-Administrator:

- Steuern, welche Benutzer in Ihrer Organisation Themen auf modernen SharePoint-Seiten oder in SharePoint-Suchergebnissen anzeigen dürfen.
- Steuern, welche SharePoint-Websites durchsucht werden, um Themen zu identifizieren.
- Das Auffinden bestimmter Themen ausschließen.
- Steuern, welche Benutzer Themen im Themencenter verwalten können.
- Steuern, welche Benutzer Themen erstellen und bearbeiten können.
- Steuern, welcher Benutzer Themen anzeigen kann.

Weitere Informationen zu Administratorsteuerelementen finden Sie unter [Zuweisen von Benutzerberechtigungen](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions), [Verwalten der Themensichtbarkeit](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) und [Verwalten der Themenerkennung](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery).

## <a name="topic-curation--feedback"></a>Kuration und Feedback zum Thema

KI wird kontinuierlich daran arbeiten, Ihnen Vorschläge zur Verbesserung Ihrer Themen zu unterbreiten, wenn Änderungen in Ihrer Umgebung auftreten. 

Benutzer mit Berechtigungen zum Bearbeiten oder Erstellen von Themen können Aktualisierungen an Themenseiten direkt vornehmen, wenn sie Korrekturen vornehmen oder zusätzliche Informationen hinzufügen möchten. Sie können auch neue Themen hinzufügen, die die KI nicht identifizieren konnte. Wenn genügend Informationen zu diesen manuell hinzugefügten Themen vorhanden sind und KI diese Art von Thema identifizieren kann, können zusätzliche Vorschläge von KI diese manuell hinzugefügten Themen verbessern 

Benutzer, denen Sie Zugriff gewähren, um Themen in ihrer täglichen Arbeit anzuzeigen, werden möglicherweise gefragt, ob das Thema für sie nützlich war. Das System überprüft diese Antworten und verwendet sie, um die Themenhervorhebung zu verbessern und um festzustellen, was in Themenzusammenfassungen und in Themendetails angezeigt wird.

Darüber hinaus können Benutzer mit entsprechenden Berechtigungen Elemente wie die Yammer-Konversation, die für ein Thema relevant sind, mit Tags versehen und einem bestimmten Thema hinzufügen. 

Siehe [Themenentdeckung und Kuration](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Weitere Informationen:

