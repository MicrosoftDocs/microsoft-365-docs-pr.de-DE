---
title: Schritt 1. Ihre Microsoft 365 Enterprise-Mandanten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Bereitstellen und Verwalten einzelner oder mehrerer Microsoft 365-Mandanten mit Optionen für Multi-Geo- und Verschieben von Standorten.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908591"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Schritt 1. Ihre Microsoft 365 Enterprise-Mandanten

Eine Ihrer ersten Mandantenentscheidungen ist, wie viele sie haben müssen. Jeder Microsoft 365-Mandant ist unterschiedlich, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt. Der entsprechende Azure AD-Mandant ist auch anders, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt.

## <a name="single-tenant"></a>Einzelner Mandant
Die Verwendung eines einzelnen Mandanten vereinfacht viele Aspekte der Nutzung von Microsoft 365 in Ihrer Organisation. Ein einzelner Mandant bedeutet einen einzelnen Azure AD-Mandanten mit einem einzigen Satz von Konten, Gruppen und Richtlinien. Berechtigungen und die Freigabe von Ressourcen in Ihrer Organisation können über diesen zentralen Identitätsanbieter durchgeführt werden.

Ein einzelner Mandant bietet ihren Benutzern die funktionsreichste und vereinfachte Zusammenarbeit und Produktivität.

Hier ist ein Beispiel für den Standardspeicherort und den Azure AD-Mandanten eines Microsoft 365-Mandanten.

![Ein einzelner Microsoft 365-Mandant mit seinem Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Mehrere Mandanten

Es gibt viele Gründe, warum Ihre Organisation mehrere Mandanten haben könnte:

- Administrative Isolation
- Dezentralisierte IT
- Historische Entscheidungen
- Fusionen, Übernahmen oder Übernahmen
- Klare Trennung des Brandings für Mischkonzernorganisationen
- Präproduktions-, Test- oder Sandkasten-Mandanten

Hier ist ein Beispiel für eine Organisation mit zwei Mandanten (Mandant A und Mandant B) in derselben Standard-Rechenzentrums-Geo. Jeder Mandant als separater Azure AD-Mandant.

![Mehrere Microsoft 365-Mandanten mit ihren eigenen Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Wenn Sie über mehrere Mandanten verfügen, gibt es Einschränkungen und zusätzliche Überlegungen bei der Verwaltung und Bereitstellung von Diensten für Ihre Benutzer.

### <a name="inter-tenant-collaboration"></a>Zusammenarbeit zwischen Mandanten

Wenn Sie möchten, dass Ihre Benutzer in verschiedenen Microsoft 365-Mandanten auf sichere Weise effektiver zusammenarbeiten, umfassen die Optionen für die mandantenübergreifende Zusammenarbeit die Verwendung eines zentralen Speicherorts für Dateien und Unterhaltungen, das Freigeben von Kalendern, die Verwendung von Chats, Audio-/Videoanrufe für die Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen.

Weitere Informationen finden Sie unter Zusammenarbeit zwischen Mandanten in [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Mandantenübergreifende Postfachmigration (Vorschau)

Vor der mandantenübergreifenden Postfachmigration (in der Vorschau) müssen Sie beim Verschieben von Exchange Online-Postfächern zwischen Mandanten ein Benutzerpostfach vollständig von ihrem aktuellen Mandanten (dem Quell-Mandanten) in einen lokalen Mandanten auswechseln und dann in einen neuen Mandanten (den Ziel-Mandanten) integrieren. Mit dem neuen feature für die mandantenübergreifende Postfachmigration können Mandantenadministratoren sowohl in Quell- als auch in Ziel-Mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben. Dadurch müssen keine Off-Board- und Onboardingpostfächer mehr verwendet werden.

Hier sind zwei Beispiel-Mandanten und ihre Postfächer vor der mandantenübergreifenden Postfachmigration.

![Mehrere Microsoft 365-Mandanten und ihre Postfächer](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

In dieser Abbildung verfügen zwei separate Mandanten über eigene Domänen und einen Satz von Exchange-Postfächern.

Hier ist der Ziel mandant (Mandant A) nach der mandantenübergreifenden Postfachmigration.

![Der Ziel mandant nach der mandantenübergreifenden Postfachmigration](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

In dieser Abbildung verfügt ein einzelner Mandant sowohl über Domänen als auch über beide Gruppen von Exchange-Postfächern.

Weitere Informationen finden Sie unter ["Mandantenübergreifende Postfachmigration".](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Migrationen zwischen Mandanten

Es gibt mehrere Architekturansätze für Fusionen, Übernahmen, Abgänge und andere Szenarien, die sie dazu führen können, einen vorhandenen Microsoft 365-Mandanten zu einem neuen Mandanten zu migrieren. 

Ausführliche Anleitungen finden Sie unter [Microsoft 365-Migrationen](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)zwischen Mandanten.

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo für einen Mandanten

Mit Microsoft 365 Multi-Geo können Sie Ruhedaten an den anderen geografischen Standorten des Rechenzentrums bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenspeicherung zu erfüllen, und gleichzeitig Ihre globale Einführung moderner Produktivitätserfahrungen für Ihre Mitarbeiter freischalten.

In einer Multi-Geo-Umgebung besteht Ihr Microsoft 365-Mandant aus einem Standard- oder zentralen Standort, an dem Ihr Microsoft 365-Abonnement ursprünglich erstellt wurde, und einem oder mehreren Satellitenstandorten. In einem Multi-Geo-Mandanten werden die Informationen zu geografischen Standorten, Gruppen und Benutzerinformationen in einem globalen Azure AD-Mandanten gemastert. Da Ihre Mandanteninformationen zentral gemastert und an jedem geografischen Standort synchronisiert werden, werden Die Zusammenarbeitserfahrungen, an denen alle Personen aus Ihrem Unternehmen beteiligt sind, über die Standorte hinweg freigegeben.

Hier ist ein Beispiel für eine Organisation mit ihrem Standardstandort in Europa und einem Satellitenstandort in Nordamerika. Beide Standorte verwenden denselben globalen Azure AD-Mandanten für den einzelnen Microsoft 365-Mandanten.

![Beispiel für einen Multi-Geo-Microsoft 365-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Mehr dazu unter [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Verschieben von Kerndaten in eine neue Rechenzentrums-Geo

Microsoft öffnet weiterhin neue Rechenzentrums-Geos für Microsoft 365-Dienste. Diese neuen Rechenzentrumsregionen erweitern Kapazitäten und Rechenleistung zur Unterstützung unserer laufenden Kundennachfrage und des Nutzungswachstums. Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.

Obwohl das Öffnen einer neuen Rechenzentrums-Geo keine Auswirkungen auf Sie und Ihre Kerndaten hat, die in einer bereits vorhandenen Rechenzentrums-Geo gespeichert sind, können Sie mit Microsoft eine frühzeitige Migration der ruhenden Kundenkerndaten Ihrer Organisation zu einer neuen Rechenzentrums-Geo anfordern.

Hier ist ein Beispiel, bei dem ein Microsoft 365-Mandant aus dem Geografischen des Rechenzentrums der Europäischen Union (EU) in das Rechenzentrum im Vereinigten Königreich verschoben wurde.

![Beispiel für das Verschieben eines Microsoft 365-Mandanten zwischen den geografischen Datencentern](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Weitere Informationen finden Sie unter [Verschieben von Kerndaten in neue Geografische Datencenter von Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Produkte und Lizenzen für einen Mandanten

Ihr Microsoft 365-Mandant wird erstellt, wenn Sie Ihr erstes Produkt erwerben, z. B. Microsoft 365 E3. Zusammen mit dem Produkt gibt es Lizenzen, denen eine monatliche oder jährliche Gebühr in Rechnung gestellt wird. Ein Administrator weist dann einem Benutzerkonto eine verfügbare Lizenz aus einem Ihrer Produkte zu, entweder direkt oder über die Gruppenmitgliedschaft. Je nach den Geschäftsanforderungen Ihrer Organisation verfügen Sie möglicherweise über eine Reihe von Produkten, die jeweils über einen eigenen Pool von Lizenzen verfügen. 

Das Bestimmen der Produkt- und Anzahl der Lizenzen für die einzelnen Produkte erfordert eine gewisse Planung:

- Stellen Sie sicher, dass Sie über genügend Lizenzen für die Benutzerkonten verfügen, die erweiterte Features benötigen.
- Verhindern Sie, dass Lizenzen auslaufen oder sie zu viele nicht zugewiesene Lizenzen haben, basierend auf Änderungen bei der Personalbepersonalung in Ihrer Organisation.


## <a name="results-of-step-1"></a>Ergebnisse von Schritt 1

Für Ihre Microsoft 365 Enterprise-Mandanten haben Sie ermittelt:

- Wie viele Mandanten Sie haben oder benötigen.
- Für jeden Mandanten, welche Produkte und Lizenzen erworben werden müssen.
- Gibt an, ob ein Mandant Multi-Geo sein muss, um die Anforderungen an den Datenspeicher zu erfüllen.
- Gibt an, ob Sie die mandantenübergreifende Zusammenarbeit einrichten müssen.
- Gibt an, ob Sie einen Mandanten zu einem anderen migrieren müssen.
- Gibt an, ob Sie Kerndaten von einer Rechenzentrums-Geo in eine neue verschieben müssen.

Hier ist ein Beispiel für einen neuen Mandanten.

![Beispiel für einen neuen Mandanten](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

In dieser Abbildung hat der Mandant:

- Ein Standardspeicherort, der einem geografischen Standort des Microsoft 365-Rechenzentrums entspricht.
- Eine Reihe von Produkten und Lizenzen.
- Der Satz von Cloud-Produktivitäts-Apps, von denen einige für Produkte spezifisch sind.
- Ein Azure AD-Mandant, der globale Administratorkonten und einen anfänglichen DNS-Domänennamen enthält.

Während wir die zusätzlichen Schritte dieser Lösung durchziehen, erstellen wir diese Abbildung.

## <a name="ongoing-maintenance-for-tenants"></a>Laufende Wartung für Mandanten

Es kann sein, dass Sie regelmäßig:

- Fügen Sie einen neuen Mandanten hinzu.
- Hinzufügen neuer Produkte zu einem Mandanten mit einer anfänglichen Anzahl von Lizenzen.
- Ändern Sie den Satz von Lizenzen für ein Produkt in einem Mandanten, um sich an sich ändernde Mitarbeiteranforderungen anzupassen.
- Verschieben Sie Ihre Kerndaten von einem Mandanten an einen neuen geografischen Standort des Rechenzentrums.
- Hinzufügen von Multi-Geo für Daten-Residency-Anforderungen.
- Einrichten der mandantenübergreifenden Zusammenarbeit.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 2. Optimieren Ihres Mandanten für das Netzwerk für den Zugriff](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Fahren Sie mit [dem Netzwerk](tenant-management-networking.md) fort, um optimale Netzwerke von Ihren Mitarbeitern zu Microsoft 365-Clouddiensten zu ermöglichen.
