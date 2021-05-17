---
title: Microsoft 365 Isolation und Zugriffssteuerung in Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Isolation und Zugriffssteuerung funktionieren, um Daten für mehrere Mandanten innerhalb eines Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332412"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365 Isolation und Zugriffssteuerung in Azure Active Directory

Azure Active Directory (Azure AD) wurde entwickelt, um mehrere Mandanten durch logische Datenisolation auf äußerst sichere Weise zu hosten. Der Zugriff auf Azure AD wird durch eine Autorisierungsebene geortet. Azure AD isoliert Kunden, die Mandantencontainer als Sicherheitsgrenzen verwenden, um die Inhalte eines Kunden zu schützen, sodass der Zugriff auf die Inhalte durch Mit-Mandanten nicht möglich ist oder von diesen beeinträchtigt werden kann. Drei Prüfungen werden von der Autorisierungsebene von Azure AD durchgeführt:

- Ist der Prinzipal für den Zugriff auf Azure AD-Mandanten aktiviert?
- Ist der Prinzipal für den Zugriff auf Daten in diesem Mandanten aktiviert?
- Ist die Rolle des Prinzipal in diesem Mandanten für die Art des angeforderten Datenzugriffs autorisiert?

Keine Anwendung, kein Benutzer, kein Server oder kein Dienst kann ohne die richtige Authentifizierung und das entsprechende Token oder Zertifikat auf Azure AD zugreifen. Anforderungen werden abgelehnt, wenn sie nicht von ordnungsgemäßen Anmeldeinformationen begleitet werden.

Tatsächlich hostet Azure AD jeden Mandanten in seinem eigenen geschützten Container mit Richtlinien und Berechtigungen für und innerhalb des Containers, die ausschließlich im Besitz des Mandanten sind und vom Mandanten verwaltet werden.
 
![Azure-Container](../media/office-365-isolation-azure-container.png)

Das Konzept von Mandantencontainern ist tief in den Verzeichnisdienst auf allen Ebenen, von Portalen bis zum persistenten Speicher, tief gespalten. Selbst wenn mehrere Azure AD-Mandantenmetadaten auf demselben physischen Datenträger gespeichert werden, besteht keine andere Beziehung zwischen den Containern als dem, was vom Verzeichnisdienst definiert wird, was wiederum vom Mandantenadministrator diktiert wird. Es kann keine direkten Verbindungen mit Azure AD-Speicher von einer anfordernden Anwendung oder einem dienst ohne vorheriges Durch-die-Autorisierungsebenen gibt.

Im folgenden Beispiel verfügen Contoso und Fabrikam über separate, dedizierte Container, und auch wenn diese Container einige derselben zugrunde liegenden Infrastruktur wie Server und Speicher gemeinsam nutzen können, bleiben sie getrennt und voneinander isoliert und durch Autorisierungs- und Zugriffssteuerungsebenen umlagert.
 
![Azure dedizierte Container](../media/office-365-isolation-azure-dedicated-containers.png)

Darüber hinaus gibt es keine Anwendungskomponenten, die in Azure AD ausgeführt werden können, und es ist nicht möglich, dass ein Mandant die Integrität eines anderen Mandanten gewaltsam verletzt, auf Verschlüsselungsschlüssel eines anderen Mandanten zutritt oder Rohdaten vom Server liest.

Standardmäßig werden in Azure AD alle Vorgänge, die von Identitäten in anderen Mandanten ausgegeben werden, nicht unterstützt. Jeder Mandant ist logisch in Azure AD durch anspruchsbasierte Zugriffssteuerelemente isoliert. Lese- und Schreibvorgänge von Verzeichnisdaten sind auf Mandantencontainer begrenzt und werden durch eine interne Abstraktionsebene und eine rollenbasierte Zugriffssteuerungsebene (RBAC) begrenzt, die den Mandanten gemeinsam als Sicherheitsgrenze erzwingen. Jede Verzeichnisdatenzugriffsanforderung wird von diesen Ebenen verarbeitet, und jede Zugriffsanforderung in Microsoft 365 wird von der obigen Logik verarbeitet.

Azure AD verfügt über Nordamerika, die US-Regierung, die Europäische Union, Deutschland und die weltweiten Partitionen. Ein Mandant ist in einer einzelnen Partition vorhanden, und Partitionen können mehrere Mandanten enthalten. Partitionsinformationen werden von Benutzern abstrahiert. Eine bestimmte Partition (einschließlich aller Mandanten in ihr) wird in mehrere Rechenzentren repliziert. Die Partition für einen Mandanten wird basierend auf den Eigenschaften des Mandanten (z. B. der Ländercode) ausgewählt. Geheime Und andere vertrauliche Informationen in jeder Partition werden mit einem dedizierten Schlüssel verschlüsselt. Die Schlüssel werden automatisch generiert, wenn eine neue Partition erstellt wird.

Azure AD-Systemfunktionen sind eine eindeutige Instanz für jede Benutzersitzung. Darüber hinaus verwendet Azure AD Verschlüsselungstechnologien, um die Isolation freigegebener Systemressourcen auf Netzwerkebene zu ermöglichen, um eine nicht autorisierte und unbeabsichtigte Übertragung von Informationen zu verhindern.
