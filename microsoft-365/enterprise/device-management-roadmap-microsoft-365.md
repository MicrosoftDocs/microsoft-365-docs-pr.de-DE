---
title: Roadmap für die Geräteverwaltung für Microsoft 365
keywords: Microsoft 365, Microsoft 365 für Unternehmen, Microsoft 365-Dokumentation, Verwaltung mobiler Geräte, InTune
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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315741"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roadmap für die Geräteverwaltung für Microsoft 365


Microsoft 365 for Enterprise umfasst Features zur Unterstützung der Verwaltung von Geräten und deren apps in Ihrer Organisation. Die Verwaltung mobiler Geräte hilft Ihnen, die Ressourcen Ihrer Organisation zu sichern und zu schützen.

Es gibt zwei Optionen für die Geräteverwaltung.

## <a name="microsoft-intune"></a>Microsoft Intune

InTune bietet Ihnen Optionen zum Verwalten des Zugriffs auf Ihre Organisation mithilfe von MDM (Mobile Device Management) oder MAM (Mobile Application Management). MDM ist, wenn Benutzer ihre Geräte in InTune "registrieren". Sobald die Registrierung erfolgt ist, handelt es sich um verwaltete Geräte und kann alle Richtlinien, Regeln und Einstellungen empfangen, die von Ihrer Organisation verwendet werden. Beispielsweise können Sie bestimmte apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten möglicherweise Ihre Geräte nicht registrieren oder von InTune und ihren Richtlinien verwalten. Sie müssen jedoch dennoch die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre apps mit MAM schützen. Sie können beispielsweise eine MAM-Richtlinie verwenden, bei der ein Benutzer eine PIN beim Zugriff auf SharePoint auf dem Gerät eingeben muss.

Darüber hinaus bestimmen Sie, wie Sie persönliche oder organisationseigene Geräte verwalten werden. Sie sollten Geräte je nach Verwendung unterschiedlich behandeln. 

Beginnen Sie [hier](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).

## <a name="basic-mobility-and-security"></a>Grundlegende Mobilität und Sicherheit
 
Dieses ist in Microsoft 365 integriert und hilft Ihnen, die mobilen Geräte ihrer Benutzer wie iPhones, iPads, Androiden und Windows phones zu sichern und zu verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen. 

Beginnen Sie [hier](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).
 
## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. Verwenden Sie für den Geräte Zugriff die Empfehlungen und Einstellungen in den folgenden Artikeln:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Funktionsweise von Contoso für die Geräteverwaltung für Microsoft 365

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [Ihre Infrastruktur für Mobile Geräteverwaltung](contoso-mdm.md) mit Microsoft 365 Cloud Services bereitgestellt hat.
