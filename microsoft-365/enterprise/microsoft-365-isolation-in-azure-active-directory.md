---
title: Microsoft 365-Isolierung und Zugriffssteuerung in Azure Active Directory
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
description: In diesem Artikel erfahren Sie, wie Sie mit Isolation und Zugriffssteuerung Daten für mehrere Mandanten in Azure Active Directory voneinander isoliert aufbewahren können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332412"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365-Isolierung und Zugriffssteuerung in Azure Active Directory

Azure Active Directory (Azure AD) wurde entwickelt, um mehrere Mandanten auf hochsichere Weise durch die logische Datenisolierung zu hosten. Der Zugriff auf Azure AD ist von einer Autorisierungsebene abgegrenzt. Azure AD isolieren Kunden, die Mandanten Container als Sicherheitsgrenzen verwenden, um den Inhalt eines Kunden zu schützen, damit der Zugriff auf Inhalte nicht möglich ist oder von anderen Kollegen beeinträchtigt wird. Drei Prüfungen werden von der Autorisierungs Schicht von Azure AD ausgeführt:

- Ist der Prinzipal für den Zugriff auf Azure AD Mandanten aktiviert?
- Ist der Prinzipal für den Zugriff auf Daten in diesem Mandanten aktiviert?
- Ist die Rolle des Prinzipals in diesem Mandanten für den Typ des angeforderten Datenzugriffs autorisiert?

Keine Anwendung, kein Benutzer, kein Server oder kein Dienst kann auf Azure AD ohne entsprechende Authentifizierung und Token oder Zertifikat zugreifen. Anforderungen werden zurückgewiesen, wenn Sie nicht von ordnungsgemäßen Anmeldeinformationen begleitet werden.

Effektiv Azure AD hostet jeden Mandanten in seinem eigenen geschützten Container, mit Richtlinien und Berechtigungen für und innerhalb des Containers, der ausschließlich vom Mandanten besessen und verwaltet wird.
 
![Azure-Container](../media/office-365-isolation-azure-container.png)

Das Konzept von Mandanten Containern ist tief im Verzeichnisdienst auf allen Ebenen verankert, von Portalen bis hin zu persistentem Speicher. Selbst wenn mehrere Azure AD Mandanten Metadaten auf demselben physikalischen Datenträger gespeichert werden, gibt es keine Beziehung zwischen den Containern, die nicht durch den Verzeichnisdienst definiert sind, was wiederum vom mandantenadministrator diktiert wird. Es kann keine direkte Verbindung zu Azure AD Speicher von einer anfordernden Anwendung oder einem Dienst ohne vorheriges durchlaufen der Autorisierungs Schicht geben.

Im Beispiel unten verfügen Contoso und Fabrikam über separate, dedizierte Container, und obwohl diese Container möglicherweise einige der gleichen zugrunde liegenden Infrastruktur wie Server und Speicher freigeben, bleiben Sie getrennt und voneinander isoliert und von Ebenen der Autorisierung und Zugriffssteuerung abgegrenzt.
 
![Dedizierte Azure-Container](../media/office-365-isolation-azure-dedicated-containers.png)

Darüber hinaus gibt es keine Anwendungskomponenten, die in Azure AD ausgeführt werden können, und es ist für einen Mandanten nicht möglich, die Integrität eines anderen Mandanten gewaltsam zu verletzen, auf die Verschlüsselungsschlüssel eines anderen Mandanten zuzugreifen oder unformatierte Daten vom Server zu lesen.

Standardmäßig werden von Azure AD alle Vorgänge, die von Identitäten in anderen Mandanten ausgestellt werden, nicht zugelassen. Jeder Mandant ist in Azure AD durch anspruchsbasierte Zugriffssteuerungen logisch isoliert. Lese-und Schreibvorgänge von Verzeichnisdaten werden auf Mandanten Container beschränkt und von einer internen Abstraktionsschicht und einer rollenbasierten Zugriffs Steuerungsschicht (Role-Based Access Control, RBAC) gesteuert, die den Mandanten zusammen als Sicherheitsgrenze erzwingen. Jede Verzeichnisdaten Zugriffsanforderung wird von diesen Schichten verarbeitet, und jede Zugriffsanforderung in Microsoft 365 wird durch die obige Logik überwacht.

Azure AD hat die Partitionen Nordamerika, US-Regierung, Europäische Union, Deutschland und World Wide. Ein Mandant ist in einer einzelnen Partition vorhanden, und Partitionen können mehrere Mandanten enthalten. Partitionsinformationen werden von Benutzern abstrahiert. Eine bestimmte Partition (einschließlich aller Mandanten in Ihr) wird in mehrere Rechenzentren repliziert. Die Partition für einen Mandanten wird basierend auf den Eigenschaften des Mandanten ausgewählt (beispielsweise der Ländercode). Geheimnisse und andere vertrauliche Informationen in jeder Partition werden mit einem dedizierten Schlüssel verschlüsselt. Die Schlüssel werden automatisch generiert, wenn eine neue Partition erstellt wird.

Azure AD Systemfunktionen sind eine eindeutige Instanz für jede Benutzersitzung. Darüber hinaus verwendet Azure AD Verschlüsselungstechnologien, um freigegebene Systemressourcen auf Netzwerkebene zu isolieren, um eine unbefugte und unbeabsichtigte Weitergabe von Informationen zu verhindern.
