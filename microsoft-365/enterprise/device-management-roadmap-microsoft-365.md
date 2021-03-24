---
title: Roadmap für die Verwaltung mobiler Geräte für Microsoft 365
keywords: Microsoft 365, Microsoft 365 for Enterprise, Microsoft 365-Dokumentation, Verwaltung mobiler Geräte, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Die Roadmap zum Einrichten der Geräteverwaltung für Microsoft 365.
ms.openlocfilehash: ec284a96fc8e7285f89e8a909b76c782b4469ce1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051460"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roadmap für die Verwaltung mobiler Geräte für Microsoft 365

Microsoft 365 for Enterprise enthält Features, mit deren Hilfe Geräte und ihre Apps innerhalb Ihrer Organisation verwaltet werden können. Durch die Verwaltung mobiler Geräte können Sie die Ressourcen Ihrer Organisation sichern und schützen.

Es gibt zwei Optionen für die Geräteverwaltung:

- [Microsoft Intune](#microsoft-intune)
- [Grundlegende Mobilität und Sicherheit](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Sie können Microsoft Intune verwenden, um den Zugriff auf Ihre Organisation mithilfe der Verwaltung mobiler Geräte oder mobiler Anwendungen zu verwalten. Die Verwaltung mobiler Geräte ist, wenn Benutzer ihre Geräte in Intune "registrieren". Nachdem ein Gerät registriert wurde, handelt es sich um ein verwaltetes Gerät. Daher kann sie die Richtlinien, Regeln und Einstellungen Ihrer Organisation empfangen. Sie können beispielsweise bestimmte Apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten ihre Geräte möglicherweise nicht registrieren oder von Intune und den Richtlinien Ihrer Organisation verwaltet werden. Sie müssen jedoch weiterhin die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre Apps mithilfe der verwaltung mobiler Anwendungen schützen. Sie können z. B. eine mobile Anwendungsverwaltungsrichtlinie verwenden, für die ein Benutzer beim Zugriff auf SharePoint Online auf dem Gerät eine PIN eingeben muss.

Außerdem bestimmen Sie, wie Sie persönliche Geräte und geräte im Besitz der Organisation verwalten. Sie können Geräte je nach Verwendung unterschiedlich behandeln.

## <a name="basic-mobility-and-security"></a>Grundlegende Mobilität und Sicherheit

Dies ist in Microsoft 365 integrierte Und hilft Ihnen, die mobilen Geräte Ihrer Benutzer wie iPhones, iPads, Androids und Windows-Telefone zu sichern und zu verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen.

## <a name="choose-between-the-two-options"></a>Wählen Sie zwischen den beiden Optionen aus.

Informationen dazu, welche Geräteverwaltungsoption für Sie am besten geeignet ist, finden Sie unter [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).

Beginnen Sie basierend auf Ihrer Bewertung mit der Verwaltung Ihrer Geräte mit:

- [Intune](/mem/intune/fundamentals/planning-guide)
- [Grundlegende Mobilität und Sicherheit](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](../security/defender-365-security/microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. Verwenden Sie für den Gerätezugriff die Empfehlungen und Einstellungen in den folgenden Artikeln:

- [Voraussetzungen](../security/defender-365-security/identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/defender-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Funktionsweise der Geräteverwaltung für Microsoft 365 durch Contoso

Informationen dazu, wie ein fiktives, aber repräsentatives multinationales Unternehmen seine Infrastruktur für die Verwaltung mobiler Geräte mit Microsoft 365-Clouddiensten bereitgestellt hat, finden Sie unter [Mobile Device Management for Contoso](contoso-mdm.md).