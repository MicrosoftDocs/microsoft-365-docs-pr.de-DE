---
title: Sicherheitshürden, die Sie überwinden können – ein Architektur Standpunkt
description: Eine Beschreibung.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: eb8019efb13a13b27a67d541ae69ca6f30b35ed0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160051"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Sicherheitshürden, die Sie überwinden können – ein Architektur Standpunkt

In diesem Artikel werden von [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cyber Architect bei Microsoft, die wichtigsten Sicherheitsherausforderungen beschrieben, die Sie bei Unternehmensorganisationen trifft, und es werden Ansätze zum Segeln über diese Hürden empfohlen. 

## <a name="about-the-author"></a>Über den Autor

![Kozeta Garrett Foto](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

In meiner Rolle als Cloud-Sicherheitsarchitekt habe ich mit mehreren Organisationen zusammengearbeitet, um strategische und technische Anleitungen für das Entwerfen und Implementieren der Sicherheitsarchitektur für Kunden bereitzustellen, die zu Microsoft 365 und Azure migrieren, Sicherheitslösungen für Unternehmen entwickeln und die Sicherheitsarchitektur und-Kultur für die Ausfallsicherheit des Unternehmens transformieren helfen. Zu meinen Erfahrungen zählen Vorfallerkennung und-Antwort, Malware Analyse, Penetrationstests und Empfehlungen für Verbesserungen an IT-Sicherheit und Verteidigungshaltung. Ich bin sehr leidenschaftlich für führende Transformationen, die zu Sicherheit als Enabler für das Unternehmen führen, einschließlich Modernisierungsbemühungen.

Es hat sich als äußerst befriedigend erwiesen, zu sehen, wie Organisationen, die sich in den letzten Jahren in einer Sicherheits Modernisierungs Denkweise befanden, eine hervorragende Position haben, die es Ihnen ermöglicht, weiterhin Remote auf sichere Weise zu arbeiten, trotz der aktuellen COVID-19-Situation. Leider sind diese Umstände auch als Weckruf für einige Kunden gedient, die nicht bereit waren, diesen unmittelbaren Bedarf zu wecken. Viele Organisationen erkennen, dass Sie schnell modernisieren, ihre kumulierten IT-Sicherheits Schulden zurückziehen und ihre Sicherheitslage über Nacht verbessern müssen, damit Sie unter diesen außergewöhnlichen Umständen agieren können.

Die gute Nachricht ist, dass Microsoft einige große Ressourcen kuratiert hat, um Organisationen dabei zu helfen, ihre Sicherheitsposition schnell hochzufahren. Zusätzlich zu diesen Ressourcen möchte ich die wichtigsten Herausforderungen, die ich mit Kunden täglich getroffen habe, in der Hoffnung teilen, dass Sie über diese Hürden Segeln können.

Ich lebe derzeit in Northern Virginia, in der Nähe der Hauptstadt unseres Landes, Washington DC. Ich liebe fast jede Form von Outdoor-Aktivitäten und Bewegung, wie das Ausführen, Radfahren, Wandern und Schwimmen. Um diesen entgegenzuwirken, genieße ich genauso viel Kochen, Gourmet Essen und Reisen. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Partner mit dem Sicherheitsteam ab Beginn der Cloud-Einführung

Zunächst kann ich nicht genug betonen, wie wichtig es für Teams in Ihrer Organisation ist, von Anfang an zu koordinieren. Sicherheitsteams müssen in den frühen Phasen der Cloud-Einführung und des Designs als wichtige Partner akzeptiert werden. Dies bezieht sich auf die Bereitstellung von Sicherheitsteams bei der Einführung von Cloud-Lösungen für die Cloud, nicht nur für die hinzugefügten Funktionen für das Unternehmen (beispielsweise eine großartige Benutzererfahrung von sicheren mobilen Geräten, Anwendungen mit voller Funktionalität oder das Erstellen von Mehrwert für Unternehmensdaten über die eingeschränkte Funktionalität von e-Mail-und Produktivitätsanwendungen hinaus), sondern auch Sicherheitsteams müssen in die Verwaltung aller Aspekte dieser Schicht einbezogen werden, einschließlich Personen (Kultur), Prozesse (Schulung) und Technologie, um erfolgreich zu sein. Es bedeutet auch Investitionen in die Modernisierung und kontinuierliche Verbesserung des Security Operations Centers (SoC). Arbeiten Sie zusammen, um Ihre Sicherheitsstrategie mit ihren Geschäftsstrategien und Umgebungs Trends auszurichten, um sicherzustellen, dass die digitale Transformation sicher ausgeführt wird. Wenn dies gut durchgeführt wird, entwickeln Organisationen die Möglichkeit, sich schneller an Änderungen anzupassen, einschließlich Änderungen an Geschäfts-, IT-und Sicherheitsfunktionen. 

Wo sehe ich Kunden stolpern über Hürden am meisten ist, wenn es keine wirkliche Partnerschaft zwischen den Vorgängen und den SoC-Teams. Während das Betriebsteam unter Druck gesetzt wird und mit knappen Terminen für die Übernahme der Cloud beauftragt wird, sind die Sicherheitsteams nicht immer frühzeitig in den Prozess einbezogen, um eine umfassende Sicherheitsstrategie zu überarbeiten und zu planen. Dies umfasst die Integration unterschiedlicher Cloud-Komponenten und Komponenten auf-Prem. Dieser Mangel an Partnerschaft rieselt weiter unten zu verschiedenen Teams, die scheinbar in Silos arbeiten, um Steuerelemente für Ihre spezifischen Komponenten zu implementieren, was zu der zusätzlichen Komplexität der Implementierung, Problembehandlung und Integration führt.

Kunden, die diese Hürden überwinden, verfügen über gute Partnerschaften zwischen den Teams Operations and Governance und Security and Risk Management, um die Sicherheitsstrategie und-Anforderungen für den Schutz von Hybriden Cloud-Arbeitsauslastungen zu erneuern. Sie konzentrieren sich auf die ultimativen Sicherheitsziele und-Ergebnisse – Datenschutz und Verfügbarkeit von Systemen und Diensten gemäß Cyber Governance-, Risiko-und Compliance-Anforderungen. Diese Organisationen entwickeln früh stufige Partnerschaften zwischen Ihren Betriebs-und steuerungsteams und SOC, was für den Sicherheitsentwurfs Ansatz entscheidend ist und den Wert Ihrer Investitionen maximieren wird. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Erstellen eines modernen Sicherheits Perimeters (Identitäts basiert)

Nehmen Sie als nächstes einen Zero Trust Architecture-Ansatz an. Dies beginnt mit dem Erstellen eines modernen, identitätsbasierten Sicherheits Perimeters. Entwerfen Sie die Sicherheitsarchitektur, bei der jeder Zugriffsversuch (ob on-Prem oder Cloud) als nicht vertrauenswürdig behandelt wird, bis er überprüft wird: "niemals Vertrauen, immer überprüfen". Dieser Entwurfsansatz erhöht nicht nur die Sicherheit und Produktivität, sondern ermöglicht es Benutzern auch, von jedem beliebigen Gerätetyp aus zu arbeiten. Die in Microsoft 365 enthaltenen ausgeklügelten Cloud-Steuerelemente helfen Ihnen, die Identitäten von Benutzern zu schützen und gleichzeitig den Zugriff auf wertvolle Ressourcen basierend auf der Benutzer Risikostufe zu steuern.

Eine empfohlene Konfiguration finden Sie unter [Identity and Device Access](../enterprise/microsoft-365-policies-configurations.md)Configurations. 

## <a name="transition-security-controls-to-the-cloud"></a>Übergangs Sicherheitssteuerelemente zur Cloud

Viele Sicherheitsteams verwenden immer noch die bewährten bewährten Sicherheitsmethoden, die für eine lokale Welt entwickelt wurden, einschließlich der Beibehaltung einer "Netzwerkperimeter-Sicherheit" und der "Erzwingung" der Sicherheitstools und-Steuerelemente für Cloud-Lösungen. Solche Steuerelemente wurden nicht für die Cloud entwickelt, sind wirkungslos und behindern die Einführung moderner cloudfunktionen. Prozesse und Tools, die für einen Netzwerkperimeter-Sicherheitsansatz funktionieren, haben sich als ineffizient, als störend für cloudfunktionen erwiesen und erlauben nicht die Nutzung moderner und automatisierter Sicherheitsfeatures.

Sie können diese Hürde überwinden, indem Sie die Verteidigungsstrategien auf Cloud-Managed Protection, automatisierte Untersuchungen und Korrekturen, automatisierte Stift Tests, Advanced Threat Protection und Incident Analysis umstellen. Kunden, die moderne Geräte Verwaltungslösungen verwenden, haben automatisiertes Management, standardisiertes Patching, Antivirus, Richtlinienerzwingung und Anwendungsschutz für alle Geräte (ob Smartphone, PC, Laptop oder Tablet) implementiert. Dadurch entfällt die Notwendigkeit einer VPN-, Microsoft System Center Configuration Manager (SCCM) und Active Directory Gruppenrichtlinien. In Kombination mit bedingten Zugriffsrichtlinien bietet dies eine leistungsstarke Steuerung und Sichtbarkeit sowie einen optimierten Zugriff auf Ressourcen, unabhängig davon, wo Ihre Benutzer in Betrieb sind.

## <a name="strive-for-best-together-security-tools"></a>Streben nach "Best Together"-Sicherheitstools

Eine weitere Hürde, die ich sehe Kunden stolpern ist unter einer "Best of Breed"-Ansatz für Sicherheitstools. Durch ständiges aufschichten von "Best of Breed"-Lösungen zur Bewältigung entstehender Sicherheitsanforderungen wird die Unternehmenssicherheit zum Zusammenbruch veranlasst. Selbst mit den besten Absichten werden Tools in den meisten Umgebungen nicht integriert, da es zu kostspielig und Komplex wird. Dies wiederum schafft Lücken in der Sichtbarkeit, da mehr Warnungen zur Selektierung vorhanden sind, als das Team verarbeiten kann. Das Umschulungs Team für neue Tools wird auch eine ständige Herausforderung.

Der Ansatz "Simple is better" funktioniert auch für die Sicherheit. Statt nach "Best of Breed"-Tools zu wechseln, sollten Sie diese Hürde überwinden, indem Sie eine "Best-Together"-Strategie mit Tools festlegen, die standardmäßig zusammenarbeiten. Microsoft-Sicherheitsfunktionen schützen Ihre gesamte Organisation mit integriertem Bedrohungsschutz, der sich über Anwendungen, Benutzer und Clouds erstreckt. Durch die Integration kann eine Organisation widerstandsfähiger sein und das Risiko reduzieren, indem Angreifer bei Eingabe-und schnell Remediation-Angriffen geschützt werden.

## <a name="balance-security-with-functionality"></a>Balance Security with Funktionalität

Da ich aus einem langen Cyber Hintergrund und Erfahrung stamme, bevorzuge ich es lieber mit der sichersten Konfiguration aus dem Feld zu beginnen und es Organisationen zu ermöglichen, Sicherheitskonfigurationen basierend auf Ihren Betriebs-und Sicherheitsanforderungen zu entspannen. Dies kann jedoch zu einem hohen Preis von verlorenen Funktionen und einer schlechten Benutzererfahrung kommen. Wie viele Organisationen gelernt haben, können Sie, wenn die Sicherheit für die Benutzer zu schwierig ist, einen Weg finden, um Sie zu umgehen, einschließlich der Verwendung von nicht verwalteten Cloud-Diensten. So hart es für mich ist, zu akzeptieren, bin ich mir bewusst geworden, dass die heikle Funktionalität-das Sicherheitsgleichgewicht erreicht werden muss.

Organisationen, die Benutzer erkennen, werden alles tun, um Ihre Aufgaben zu erledigen. bestätigen Sie, dass der "Shadow IT Battle" keine Kämpfe Wert ist. Sie erkennen, dass IT-Mitarbeiter die größten Täter sind, wenn es darum geht, es zu shadowen und die Verwendung von nicht genehmigten SaaS-Anwendungen für Ihren Job. Sie haben ihre Strategie verschoben, um die Verwendung (statt Unterdrückung) zu fördern und sich auf die Verringerung der Risiken zu konzentrieren, die Sie verursachen könnte. Die Sicherheitsteams dieser Organisation bestehen nicht darauf, dass alles blockiert, protokolliert und über einen Reverse-Proxy oder ein VPN gesendet wird. Vielmehr verdoppeln diese Sicherheitsteams ihre Bemühungen, wertvolle und vertrauliche Daten davor zu schützen, den falschen Parteien oder böswilligen apps ausgesetzt zu sein. Sie arbeiten, um die Integrität der Daten zu schützen. Sie nutzen erweiterte Cloud Information Protection-Funktionen wie Verschlüsselung, sichere mehrstufige Authentifizierung, automatisierte Risiken und Compliance sowie Cloud App Security Broker (CASB), während Sie die geschützte Freigabe auf mehreren Plattformen ermöglichen und sogar fördern. Sie verwandeln Shadow IT in inspirierende Kreativität, Produktivität und Zusammenarbeit, sodass Ihr Unternehmen auf dem Wettbewerbsvorteil bleiben kann.


## <a name="adopt-a-methodical-approach"></a>Übernehmen eines methodischen Ansatzes 

Die meisten der Herausforderungen, die ich mit der Implementierung von Cloud-Sicherheit in unterschiedlichen Organisationen, unabhängig von der Branche, erlebte, waren sehr ähnlich. Zunächst einmal gibt es zwar umfangreiche Dokumentationen zu bestimmten Funktionen und Features, aber auf Organisationsebene gibt es eine gewisse Verwirrung darüber, was für Sie gilt, wo sich Sicherheitsfeatures überschneiden und wie Funktionen integriert werden sollten. Es gibt auch eine gewisse Unsicherheit darüber, welche Sicherheitsfeatures vorab konfiguriert sind und welche Konfiguration durch die Organisation erforderlich sind. Darüber hinaus hatten die SoC-Teams leider noch nicht die vollständige Belichtung, Schulung oder die erforderliche Budgetzuteilung, um sich auf die schnelle Cloud-Einführung und die digitale Transformation vorzubereiten, die ihre Organisationen bereits durchlaufen.

Um diese Hürden zu beseitigen, hat Microsoft mehrere Ressourcen kuratiert, die Sie dabei unterstützen, einen methodischen Ansatz für Ihre Sicherheitsstrategie und-Implementierung zu finden. 


|Ressource   |Weitere Informationen  |
|---------|---------|
|[Wichtige Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](../security/top-security-tasks-for-remote-work.md)      | Wenn Sie sich plötzlich für eine hauptsächlich Work-at-Home-Belegschaft unterstützen, hilft Ihnen dieser Artikel, die Sicherheit schnell hochzufahren. Sie enthält die wichtigsten empfohlenen Aufgaben basierend auf Ihrem Lizenzierungs Plan.    |
|[Microsoft 365 Sicherheit für geschäftliche Entscheidungsträger](../security/Microsoft-365-security-for-bdm.md)    | Wenn Sie Zeit für einen umfassenderen Plan haben, enthält dieser Artikel Empfehlungen, die sich über Microsoft 365, priorisiert nach Angriffsfläche, erstrecken. Es kommt sogar mit einer Tabelle, die Sie verwenden können, um Nachlizenzierung und Bereich zu sortieren (wie Identität, Bedrohungsschutz und Überwachung).  |
|[Empfehlungen zur Microsoft-Sicherheitsarchitektur](https://docs.microsoft.com/security/compass/compass)    | Wenn Sie ein Sicherheitsarchitekt sind, sollten Sie die von der Disziplin organisierten Sicherheitsempfehlungen sehen, einschließlich Identitäts-, Netzwerk-und Sicherheitsmaßnahmen.   |
|[Empfehlungen für Microsoft-Sicherheitsvorgänge](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Informationen zu Microsoft-Empfehlungen zum Einrichten und Ausführen eines Security Operations Centers (SoC) |
|[Workshop-Schulung für Chief Information Security Officer (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Wenn Sie neu in der Cloud-Sicherheit sind, verpassen Sie nicht diese Reihe von Videos.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Technische Anleitungen von Across Microsoft für Sicherheitsstrategie und-Architektur.        |
| | |

Alle diese Ressourcen sind für die Verwendung als Ausgangspunkt und für die Anpassung an die Anforderungen Ihrer Organisation konzipiert. 

