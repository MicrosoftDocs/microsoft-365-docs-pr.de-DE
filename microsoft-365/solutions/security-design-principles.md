---
title: Microsoft 365 Enterprise Ressourcenplanung – Cybersicherheitsarchitektur
description: Erfahren Sie, wie Sie Sicherheitsprobleme in Microsoft Enterprise von Koseta Garrett, Cybersecurity Architect bei Microsoft, überwinden können.
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
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052482"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Sicherheitshürden, die Sie überwinden können – Ansicht eines Architekten

In diesem Artikel beschreibt [Koseta Garrett,](https://www.linkedin.com/in/kozeta-garrett-53013a6/)Cybersicherheitsarchitektin bei Microsoft, die größten Sicherheitsprobleme, die sie in Unternehmensorganisationen stellt, und empfiehlt Ansätze zum Überwinden dieser Hindernisse.

## <a name="about-the-author"></a>Über den Autor

![Foto von "Koseta Garrett"](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

In meiner Rolle als Cloud Security Architect habe ich mit mehreren Organisationen zusammengearbeitet, um strategische und technische Anleitungen zu bieten, die sich auf das Entwerfen und Implementieren von Sicherheitsarchitekturen für Kunden konzentrieren, die zu Microsoft 365 und Azure migrieren, Unternehmenssicherheitslösungen entwickeln und dabei helfen, die Sicherheitsarchitektur und -kultur für die Resilienz des Unternehmens zu transformieren. Meine Erfahrung umfasst Erkennung und Reaktion von Vorfällen, Schadsoftwareanalyse, Penetrationstests und empfehlungen zur Verbesserung der It-Security- und Verteidigungshaltung. Ich bin sehr begeistert von führenden Transformationen, die zu Sicherheit als Aktivierung für das Unternehmen führen, einschließlich Modernisierungsbemühungen.

Es war sehr zufriedenstellend zu sehen, wie Organisationen, die in den letzten Jahren eine Sicherheitsmodernisierungsübereinstimmung übernommen haben, in einer großartigen Position sind, die es ihnen ermöglicht, trotz der aktuellen COVID-19-Situation weiterhin remote sicher zu arbeiten. Leider dienten diese Umstände auch als Weckruf für einige Kunden, die nicht für diese unmittelbare Notwendigkeit bereit waren. Viele Organisationen stellen sicher, dass sie schnell modernisieren, ihre angesammelten IT-Sicherheitsschulden zurückziehen und ihre Sicherheitslage über Nacht verbessern müssen, damit sie unter diesen äußerst ungewöhnlichen Umständen arbeiten können.

Die gute Nachricht ist, dass Microsoft einige großartige Ressourcen kuratiert hat, um Organisationen dabei zu unterstützen, ihre Sicherheitslage schnell zu erhöhen. Zusätzlich zu diesen Ressourcen möchte ich die größten Herausforderungen, die ich täglich mit Kunden hatte, in der Hoffnung teilen, dass Sie diese Hürden überwinden können.

Ich wohne derzeit in Nord-Virginia, in der Nähe der Hauptstadt unseres Landes, Washington DC. Ich liebe fast jede Form von Aktivitäten und Übungen im Freien, wie Laufen, Radfahren, Wandern und Schwimmen. Um diesen zu entgegenzusingen, habe ich genauso viel Spaß beim Essen, beim Feinschmeckeressen und beim Reisen.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Partner mit dem Sicherheitsteam seit Beginn der Cloud-Einführung

Zunächst kann ich nicht genug hervorheben, wie wichtig es für Teams in Ihrer Organisation ist, sich von Anfang an zu koordinieren. Sicherheitsteams müssen in den frühen Phasen der Cloud-Einführung und des Designs als wichtige Partner angenommen werden. Dies bedeutet, dass Sicherheitsteams für die Einführung der Cloud eingesetzt werden, nicht nur für die zusätzlichen Funktionen für das Unternehmen (z. B. eine großartige Benutzererfahrung von sicheren mobilen Geräten, Anwendungen mit voller Funktionalität oder das Erstellen von Mehrwert für Unternehmensdaten über die eingeschränkten Funktionen hinaus E-Mail- und Produktivitätsanwendungen), sondern auch, um die Speicher-, KI- und Computinganalysefunktionen zu nutzen, mit denen neue und alte Sicherheitsprobleme gelöst werden können. Sicherheitsteams müssen in die Verwaltung aller Aspekte dieser Schicht einbezogen werden, einschließlich Personen (Kultur), Prozessen (Schulungen) und Technologie, um erfolgreich zu sein. Es bedeutet auch, in die Modernisierung und kontinuierliche Verbesserung des Security Operations Center (SOC) zu investieren. Arbeiten Sie zusammen, um Ihre Sicherheitsstrategie an Ihren Geschäftsstrategien und Umgebungstrends auszurichten, um sicherzustellen, dass die digitale Transformation sicher erfolgt. Wenn dies gut ist, entwickeln Organisationen die Möglichkeit, sich schneller an Änderungen anzupassen, einschließlich Änderungen an Unternehmen, IT und Sicherheit.

Wo ich sehe, dass Kunden über Hürden stolzen, ist am häufigsten, wenn es keine echte Partnerschaft zwischen den Vorgängen und den SOC-Teams gibt. Während das Betriebsteam unter Druck gesetzt und mit engen Terminen zur Einführung der Cloud beauftragt wird, werden die Sicherheitsteams nicht immer frühzeitig in den Prozess zur Überarbeitung und Planung einer umfassenden Sicherheitsstrategie einbezogen. Dies umfasst die Integration verschiedener Cloudkomponenten und Komponenten vor Demein. Dieser Mangel an Partnerschaft führt weiter zu verschiedenen Teams, die scheinbar in Silos arbeiten, um Steuerelemente für ihre spezifischen Komponenten zu implementieren, was zu einer zusätzlichen Komplexität der Implementierung, Problembehandlung und Integration führt.

Kunden, die diese Hindernisse überwinden, verfügen über gute Partnerschaften zwischen den Teams "Operations and Governance" und "Security and Risk Management", um die Sicherheitsstrategie und anforderungen zum Schutz von Hybrid-Cloud-Workloads zu überarbeiten. Sie konzentrieren sich laser-auf die ultimativen Sicherheitsziele und -ergebnisse – Datenschutz und Verfügbarkeit von Systemen und Diensten in Übereinstimmung mit den Anforderungen an cybersecurity governance, risk und compliance. Diese Organisationen entwickeln frühzeitige Partnerschaften zwischen ihrem Operations and Governance-Team und SOC, was für den Sicherheitsentwurfsansatz von entscheidender Bedeutung ist und den Wert ihrer Investitionen maximiert.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Erstellen eines modernen (identitätsbasierten) Sicherheitsperimeters

Übernehmen Sie als Nächstes einen Zero Trust-Architekturansatz. Dies beginnt mit dem Erstellen eines modernen, identitätsbasierten Sicherheitsperimeters. Entwerfen Sie die Sicherheitsarchitektur, bei der jeder Zugriffsversuch, ob on-prem oder cloud, als nicht vertrauenswürdig behandelt wird, bis er überprüft wurde – "niemals vertrauen, immer überprüfen". Dieser Entwurfsansatz erhöht nicht nur die Sicherheit und Produktivität, sondern ermöglicht es Benutzern auch, von überall aus mit jedem Gerätetyp zu arbeiten. Die ausgeklügelten Cloudsteuerelemente, die in Microsoft 365 enthalten sind, helfen Ihnen, die Identitäten der Benutzer zu schützen und gleichzeitig den Zugriff auf wertvolle Ressourcen basierend auf der Risikostufe des Benutzers zu steuern.

Eine empfohlene Konfiguration finden Sie unter [Identitäts- und Gerätezugriffskonfigurationen](../security/defender-365-security/microsoft-365-policies-configurations.md).

## <a name="transition-security-controls-to-the-cloud"></a>Übergang von Sicherheitssteuerelementen in die Cloud

Viele Sicherheitsteams verwenden weiterhin die herkömmlichen bewährten Sicherheitsmethoden, die für eine lokale Umgebung entwickelt wurden, einschließlich der Aufrechterhaltung einer "Netzwerkperimetersicherheit" und dem Versuch, die lokalen Sicherheitstools und -steuerelemente für Cloudlösungen zu "erzwingen". Solche Steuerelemente wurden nicht für die Cloud entwickelt, sind ineffektiv und behindern die Einführung moderner Cloudfunktionen. Prozesse und Tools, die für einen Ansatz zur Sicherheit des Netzwerkperimeters funktionieren, haben sich als ineffizient, für die Cloudfunktionen behindernd erwiesen und ermöglichen nicht die Nutzung moderner und automatisierter Sicherheitsfeatures.

Sie können diese Hürde nutzen, indem Sie die Abwehrstrategien auf cloudver verwalteten Schutz, automatisierte Untersuchung und Korrektur, automatisierte Stifttests, Defender for Office 365 und Vorfallanalyse verschieben. Kunden, die moderne Geräteverwaltungslösungen verwenden, haben automatisierte Verwaltung, standardisiertes Patchen, Antivirus, Richtliniendurchsetzung und Anwendungsschutz auf allen Geräten (ob Smartphone, PC, Laptop oder Tablet) implementiert. Dadurch sind keine VPN-, Microsoft System Center Configuration Manager (SCCM) und Active Directory-Gruppenrichtlinien erforderlich. Dies bietet in Kombination mit Richtlinien für bedingten Zugriff eine leistungsstarke Steuerung und Sichtbarkeit sowie einen optimierten Zugriff auf Ressourcen, unabhängig davon, von wo aus die Benutzer arbeiten.

## <a name="strive-for-best-together-security-tools"></a>Streben nach "best together"-Sicherheitstools an

Eine weitere Hürde, über die Kunden stolpern, ist die Übernahme eines Best-of-Breed-Ansatzes für Sicherheitstools. Die kontinuierliche Überschichtung von "Best of Breed"-Punktlösungen zur Lösung neuer Sicherheitsanforderungen führt dazu, dass die Unternehmenssicherheit aufbricht. Selbst bei den besten Absichten werden Tools in den meisten Umgebungen nicht integriert, da sie zu teuer und zu komplex werden. Dies wiederum führt zu Lücken in der Sichtbarkeit, da es mehr Warnungen zu triagen gibt, als das Team verarbeiten kann. Das Umschulungstraining des SecOps-Teams an neue Tools wird ebenfalls zu einer ständigen Herausforderung.

Der Ansatz "Einfach ist besser" funktioniert auch für die Sicherheit. Anstatt "Best of Breed"-Tools zu verwenden, gehen Sie über diese Hürde, indem Sie eine "best together"-Strategie mit Tools verwenden, die standardmäßig zusammenarbeiten. Microsoft-Sicherheitsfunktionen schützen Ihre gesamte Organisation durch integrierten Bedrohungsschutz, der Anwendungen, Benutzer und Clouds umfasst. Die Integration ermöglicht es einer Organisation, ausfallsicherer zu sein und Risiken zu reduzieren, indem Angreifer beim Einstieg einducken und Angriffe schnell behoben werden.

## <a name="balance-security-with-functionality"></a>Balance zwischen Sicherheit und Funktionalität

Da ich aus einem langen Hintergrund und einer langen Erfahrung mit Cybersicherheit komme, bevorzuge ich es, mit der sichersten Konfiguration zu beginnen und Organisationen zu ermöglichen, Sicherheitskonfigurationen basierend auf ihren Betriebs- und Sicherheitsanforderungen zu lockern. Dies kann jedoch zu einem hohen Preis für verlorene Funktionalität und schlechte Benutzerfreundlichkeit kommen. Wie viele Organisationen erfahren haben, finden sie, wenn die Sicherheit für Benutzer zu hart ist, eine Möglichkeit, um Sie herum zu arbeiten, einschließlich der Verwendung nicht verwalteter Clouddienste. So hart es für mich zu akzeptieren ist, bin ich mir bewusst, dass das sensible Gleichgewicht zwischen Funktionalität und Sicherheit erreicht werden muss.

Organisationen, die erkennen, dass Benutzer alles tun, um ihre Aufgaben erledigen zu können, bestätigen, dass sich der "Schatten-IT-Kampf" nicht lohnt. Sie erkennen, dass IT-Mitarbeiter die größten Angreifer sind, wenn es um Die Schatten-IT und die Verwendung nicht genehmigter SaaS-Anwendungen für ihren Job geht. Sie haben ihre Strategie verschoben, um ihre Verwendung zu fördern (anstatt sie zu unterdrücken) und sich auf die Minderung der Risiken zu konzentrieren, die durch sie sich ausdämpfen lassen könnten. Die Sicherheitsteams dieser Organisation bestehen nicht darauf, dass alles über einen Reverseproxy oder ein VPN blockiert, protokolliert und gesendet wird. Diese Sicherheitsteams verdoppeln vielmehr ihre Anstrengungen, um wertvolle und vertrauliche Daten vor der Enkbarung durch falsche Parteien oder schädliche Apps zu schützen. Sie arbeiten zum Schutz der Integrität der Daten. Sie nutzen die erweiterten Funktionen zum Schutz von Cloudinformationen, einschließlich Verschlüsselung, sicherer mehrstufiger Authentifizierung, automatisierter Risiko- und Compliancefunktionen und Cloud App Security Broker (CASB)-Funktionen, während die geschützte Freigabe auf mehreren Plattformen ermöglicht und sogar unterstützt wird. Sie machen die Schatten-IT zu kreativer Kreativität, Produktivität und Zusammenarbeit, wodurch ihr Unternehmen auf dem Wettbewerbsvorteil bleiben kann.

## <a name="adopt-a-methodical-approach"></a>Verwenden eines methodischen Ansatzes

Die meisten Herausforderungen, die ich mit der Implementierung von Cloudsicherheit in verschiedenen Organisationen, unabhängig von der Branche, hatte, waren sehr ähnlich. Zunächst einmal gibt es zwar viele großartige Dokumentationen zu bestimmten Funktionen und Features, aber es gibt auf Organisationsebene verwirrung darüber, was auf sie zutrifft, wo Sicherheitsfeatures überlappen und wie Funktionen integriert werden sollten. Es besteht auch eine Unsicherheit darüber, welche Sicherheitsfeatures vorab konfiguriert werden und welche die Konfiguration durch die Organisation erfordern. Darüber hinaus verfügen die SOC-Teams leider nicht über die vollständige Belichtung, Schulung oder Budgetzuweisung, die erforderlich sind, um sich auf die schnelle Einführung der Cloud und die digitale Transformation vorzubereiten, die ihre Organisationen bereits durchlaufen.

Um Ihnen bei der Lösung dieser Hürden zu helfen, hat Microsoft mehrere Ressourcen entwickelt, mit deren Hilfe Sie einen methodischen Ansatz für Ihre Sicherheitsstrategie und -implementierung verfolgen können.

|Ressource   |Weitere Informationen  |
|---------|---------|
|[Die wichtigsten Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](../security/top-security-tasks-for-remote-work.md)      | Wenn Sie feststellen, dass sie plötzlich eine hauptsächlich arbeits-at-home-Belegschaft unterstützen, hilft Ihnen dieser Artikel, die Sicherheit schnell zu erhöhen. Es enthält die am besten empfohlenen Aufgaben basierend auf Ihrem Lizenzierungsplan.    |
|[Microsoft 365 Entscheidungsträger für Sicherheit für Unternehmen](../security/Microsoft-365-security-for-bdm.md)    | Wenn Sie Zeit für einen umfassenderen Plan haben, enthält dieser Artikel Empfehlungen, die sich auf Microsoft 365, priorisiert nach Angriffsfläche, erstreckt. Es kommt sogar mit einer Tabelle, die Sie verwenden können, um nach Lizenzierung und Bereich (z. B. Identität, Bedrohungsschutz und Überwachung) zu sortieren.  |
|[Empfehlungen für die Sicherheitsarchitektur von Microsoft](/security/compass/compass)    | Wenn Sie ein Sicherheitsarchitekt sind, sollten Sie sicherheitsempfehlungen nach Disziplin geordnet sehen, einschließlich Identität, Netzwerk und Sicherheitsvorgängen.   |
|[Empfehlungen für Microsoft Security Operations](/security/compass/security-operations-videos-and-decks)|Informationen zu Microsoft-Empfehlungen zum Einrichten und Ausführen eines Security Operations Center (SOC) |
|[#A0 (CISO)](/security/ciso-workshop/ciso-workshop)   | Wenn Sie mit der Cloudsicherheit neu sind, sollten Sie diese Videoreihe nicht verpassen.        |
|[docs.security.com/security](/security/)    | Technische Anleitungen von Microsoft für Sicherheitsstrategie und Architektur.        |
| | |

Alle diese Ressourcen sind so konzipiert, dass sie als Ausgangspunkt verwendet und an die Anforderungen Ihrer Organisation angepasst werden.