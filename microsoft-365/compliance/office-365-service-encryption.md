---
title: Dienst Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Grundlegendes zur Ausfallsicherheit von Daten in Microsoft Office 365.'
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632240"
---
# <a name="service-encryption"></a>Dienst Verschlüsselung

Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten. Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:

- Microsoft verwaltet alle kryptografischen Schlüssel. (Diese Option ist derzeit in SharePoint Online, OneDrive für Unternehmen und Skype for Business verfügbar.)

- Ihre Organisation stellt die Stammschlüssel zur Verfügung. Sie verwalten diese Schlüssel mithilfe von Azure Key Vault. Diese Option wird als Kundenschlüssel bezeichnet. Der Kundenschlüssel steht derzeit für Exchange Online-, SharePoint Online-, OneDrive für Unternehmen-, Skype for Business-und Microsoft Teams-Dateien zur Verfügung. Wenn Sie den Kundenschlüssel verwenden, ersetzen diese Tasten die von Microsoft verwalteten Schlüssel, um Ihre Daten zu verschlüsseln.

Die Dienst Verschlüsselung bietet mehrere Vorteile. Beispiel: Kundenschlüssel:

- Bietet Rechtsschutz-und Verwaltungsfunktionen über einen starken Verschlüsselungsschutz hinaus.

- Enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.

- Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.

- Verbessert die Fähigkeit von Microsoft 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.

## <a name="customer-key"></a>Kundenschlüssel

Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel generieren, indem Sie entweder ein lokales Hardware-Service Modul (HSM) oder ein Azure Key Vault (AKV) verwenden. Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten. Nachdem Ihre Schlüssel in AKV gespeichert wurden, können Sie als Stamm einer der keychains verwendet werden, die ihre Postfachdaten oder-Dateien verschlüsseln.

Ein weiterer Vorteil von Customer Key ist die Kontrolle, die Sie über die Fähigkeit von Microsoft haben, Ihre Daten zu verarbeiten. Wenn Sie Daten aus Office 365 entfernen möchten, beispielsweise wenn Sie den Dienst mit Microsoft beenden oder einen Teil der in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden. Dadurch wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann. Kundenschlüssel wird zusätzlich zu den Kunden-Lockbox ergänzt, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.

Informationen zum Einrichten des Kunden Schlüssels für Microsoft 365 für Exchange Online, Skype for Business, SharePoint Online, einschließlich Team Websites und OneDrive für Unternehmen, finden Sie in den folgenden Artikeln:

- [Dienst Verschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Einrichten des Kunden Schlüssels](customer-key-set-up.md)

- [Verwalten des Kunden Schlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md)

- [Grundlegendes zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)
 
