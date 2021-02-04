---
title: 'Thema "Erfahrungssuche und -curation" (Vorschau) '
description: Übersicht über die Art und Weise, wie Themen ermittelt werden.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b9f4d0e33cb7a74b921681709e3ef68780dd76c4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094843"
---
# <a name="topic-discovery-and-curation-preview"></a>Themenerkennung und -curation (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex Private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Themenerfahrungen wandeln Wissensinformationen in Wissen in Ihrer Microsoft 365-Umgebung um. Wir haben alle erfahren durch Dokumente und Websiteseiten gelesen, auf denen Begriffe auftreten, mit denen wir nicht vertraut sind. Wir beenden oft, was wir tun, um viel Zeit mit der Suche nach weiteren Informationen zu verbringen.

Themenerfahrungen verwenden Microsoft Graph und KI, um **Themen** in Ihrer Organisation zu identifizieren.  Ein Thema ist ein Ausdruck oder Ausdruck, der eine bestimmte Bedeutung für die Organisation hat und ressourcenbezogene Ressourcen enthält, mit deren Hilfe Benutzer den Begriff verstehen und weitere Informationen zu diesem Thema finden können. Es gibt viele verschiedene Thementypen, die für Ihre Organisation wichtig sind. Zunächst können die folgenden Thementypen identifiziert werden:
- Project
- Ereignis
- Organisation
- Ort
- Produkt
- Kreatives Arbeiten
- Studienbereich

Ki identifiziert Personen und Inhalte, die mit dem Thema verbunden sind, und wenn genügend gefunden wird, wird sie zu einem vorgeschlagenen Thema. Die folgenden Eigenschaften werden identifiziert und auf einer **Themenseite angezeigt:**
- Alternative Namen und/oder Akronyme.
- Eine kurze Beschreibung des Themas.
- Personen, die möglicherweise mit dem Thema bekannt sind.
- Dateien, Seiten und Websites im Zusammenhang mit dem Thema.

Die Eigenschaften werden anhand der Dateien und Seiten identifiziert, die Teil des Nachweises für die Identifizierung des Themas sind. Alternative Namen und Akronyme werden aus diesen Dateien und Seiten stammen. Die kurze Beschreibung stammt aus diesen Dateien und Seiten oder aus dem Internet über Wikipedia. Auf die Quelldatei, die Seite oder den Wikipedia-Artikel wird zusammen mit den vorgeschlagenen Eigenschaften verwiesen. Personen werden basierend auf ihren aktiven Beiträgen (z. B. Bearbeitungen) an den Dateien und Seiten vorgeschlagen. Ein Verweis auf die Höhe der Beiträge einer bestimmten Person gibt einen Hinweis darauf, warum die Person identifiziert wurde. Dateien, Seiten und Websites werden basierend darauf bewertet, ob sie im Mittelpunkt des Themas stehen, ob sie einen Überblick oder eine Einführung in das Thema bieten können. 

Nicht jedes identifizierte Thema ist für Ihre Organisation nützlich oder hat einen oder die richtigen alternativen Namen oder eine Beschreibung, die entsprechenden Personen oder Inhalte identifiziert. Daher ist die Möglichkeit, nicht identifizierte Themen hinzuzufügen, vorgeschlagene Themen zu halten und Themen zu erstellen, entscheidend, um die Qualität der Themen zu verbessern, die in Ihrer Organisation gefunden werden können.

Die Themenerfahrung schlägt dann, wenn der Kontext angemessen ist, vor, dass diese Themen auf allen modernen SharePoint-Websiteseiten in Ihrem Mandanten hervorgehoben werden. Auf das Thema kann auch direkt von einem Seitenautor auf der Seite der modernen SharePoint-Website verwiesen werden. Wenn ein Benutzer mehr über ein Thema erfahren möchte, kann er  das hervorgehobene Thema auswählen, um eine Zusammenfassungskarte für Themen mit einer kurzen Beschreibung zu erhalten. Und wenn sie mehr erfahren möchten, können sie einen **Link** "Themendetails" in der Zusammenfassung auswählen, um die detaillierte Themenseite zu öffnen.

![Themenhighlights](../media/knowledge-management/saturn.png) </br>

Darüber hinaus können Benutzer auch Themen über Microsoft Search finden.

## <a name="topic-curation-and-feedback"></a>Themenkrümmung und Feedback

Themenerfahrungen begrüssen den menschlichen Beitrag zur Verbesserung der Qualität Ihrer Themen. Während AI zunächst Themen identifiziert und vorschlägt, sind manuelle Änderungen an Inhalten von Mitwirkenden, manuell hinzugefügte Themen, die Bestätigung von Benutzern für von AI ermittelte Eigenschaften und Inhalte sowie Feedback zur Nützlichkeit von Themen unerlässlich.

- Themen können von **Wissensmanagern** in Ihrer Organisation überprüft werden. Der Knowledge Manager kann Themen überprüfen, für die er über Berechtigungen verfügt. Auf der Seite "Themen verwalten" im Themencenter können sie auswählen, dass themengenerierte Themen ("vorgeschlagene Themen") gültig sind, Themen ablehnen, um zu verhindern, dass der Inhalt als Thema angezeigt wird, Themen erstellen, die nicht von AI erkannt wurden, oder Themen identifizieren, die von einigen Bearbeitungen von Experten profitieren könnten, um hilfreicher oder präziser zu sein. Weitere [Informationen finden Sie unter "Verwalten von Themen"](manage-topics.md) im Themencenter.

- Sie können allen *lizenzierten* Benutzern Berechtigungen zum Erstellen und Bearbeiten von Themen zuweisen, damit diese Änderungen an vorhandenen Themen vornehmen oder neue Themen erstellen können. Auf diese Weise können Benutzer, die über das Thema informiert sind, die Themenseite direkt aktualisieren, um Korrekturen vornehmen oder zusätzliche Informationen hinzufügen. Sie können auch neue Themen hinzufügen, die ai nicht identifizieren konnte. Wenn genügend Informationen zu diesen manuell hinzugefügten Themen zur Verfügung stehen und AI diese Art von Thema identifizieren kann, können zusätzliche Vorschläge von KI diese manuell hinzugefügten Themen verbessern. Gemeinsam können Menschen und KI wissen im Laufe der Zeit präzise halten und diese Ruhe nicht auf einer einzelnen Person ruhen lassen. Weitere [Informationen finden Sie unter "Erstellen eines neuen](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) Themas" und ["Bearbeiten](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic) eines Themas".

- Selbst Benutzer, die nur Lesezugriff auf das Thema haben (Themenanzeiger), werden aufgefordert, die Nützlichkeit bestimmter Themen zu überprüfen. Feedbackfragen werden auf der Zusammenfassungskarte **"Thema"** gestellt, um den Wert des Themas und seine Informationen zu verbessern. Fragen zur Qualität und nützlichkeit der Ki-Vorschläge werden den Benutzern nach und nach präsentiert. Zu den Fragen gehören:
1. Ob das Identifizieren des Themas auf der SharePoint-Seite hilfreich war. Es gibt die Möglichkeit, die Hervorhebung zu entfernen, wenn sie nicht korrekt oder hilfreich ist. Wenn genügend Personen angeben, dass ein Thema auf einer bestimmten Seite nicht richtig identifiziert wurde, wird dieses Highlight schließlich für alle Benutzer entfernt. 

2. Gibt an, ob das vorgeschlagene Thema für die Organisation von Wert ist. Wenn genügend Personen angeben, dass das vorgeschlagene Thema hilfreich ist, wird das Thema automatisch bestätigt. Alternativ wird das Thema automatisch abgelehnt, wenn das vorgeschlagene Thema nicht hilfreich ist. Der Knowledge Manager kann diese Aktivität in der Ansicht "Themen verwalten" beobachten.

3. Gibt an, ob die Personen- und Ressourcenvorschläge hilfreich sind.

4. Auf der Startseite des Themencenters werden die Themen in Ihrer Organisation angezeigt, mit denen Sie eine Verbindung herstellen. Sie können wählen, ob Sie im Thema aufgeführt bleiben oder sich selbst entfernen möchten. Dieses Feedback wird allen Personen widersentsprechen, die dieses Thema entdecken. Weitere [Informationen zur Startseite des](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) Themencenters finden Sie in der Übersicht über das Thema Center.

Auch bei menschlichen Bearbeitungen sucht KI ständig nach weiteren Informationen zu Themen und sucht nach einer menschlichen Überprüfung. Wenn AI z. B. der Meinung ist, dass Sie eine Person sind, die als Experte für ein Thema aufgeführt werden sollte, werden Sie zur Bestätigung ders bitten. 


## <a name="see-also"></a>Weitere Informationen:
