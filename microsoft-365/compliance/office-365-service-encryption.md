---
title: Dienstverschlüsselung
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
description: 'Zusammenfassung: Informationen zur Datenresilienz in Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058548"
---
# <a name="service-encryption"></a>Dienstverschlüsselung

Zusätzlich zur Verwendung der Verschlüsselung auf Volumeebene verwenden Exchange Online, Microsoft Teams, SharePoint Online und OneDrive for Business auch die Dienstverschlüsselung, um Kundendaten zu verschlüsseln. Die Dienstverschlüsselung ermöglicht zwei Schlüsselverwaltungsoptionen:

## <a name="microsoft-managed-keys"></a>Von Microsoft verwaltete Schlüssel
Microsoft verwaltet alle kryptografischen Schlüssel einschließlich der Stammschlüssel für die Dienstverschlüsselung. Diese Option ist derzeit standardmäßig für Exchange Online, SharePoint Online, OneDrive for Business aktiviert. Von Microsoft verwaltete Schlüssel bieten standardmäßige Dienstverschlüsselung, es sei denn, Sie entscheiden sich für das Onboarding mit Customer Key. Wenn Sie zu einem späteren Zeitpunkt entscheiden, den Kundenschlüssel nicht mehr zu verwenden, ohne dem Pfad zur Datenbereinigung zu folgen, bleiben Ihre Daten mit den von Microsoft verwalteten Schlüsseln verschlüsselt. Ihre Daten werden auf dieser Standardstufe immer mindestens verschlüsselt. 

## <a name="customer-key"></a>Kundenschlüssel
Sie liefern Stammschlüssel, die mit der Dienstverschlüsselung verwendet werden, und verwalten diese Schlüssel mithilfe von Azure Key Vault. Microsoft verwaltet alle anderen Schlüssel. Diese Option heißt Customer Key und ist derzeit für Exchange Online, SharePoint Online und OneDrive for Business verfügbar. (Früher als erweiterte Verschlüsselung mit BYOK bezeichnet. Informationen zur ursprünglichen Ankündigung finden Sie unter Verbessern der Transparenz und Kontrolle für [Office 365-Kunden.)](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)

Die Dienstverschlüsselung bietet mehrere Vorteile:

- Bietet eine zusätzliche Schutzebene über BitLocker.

- Ermöglicht die Trennung von Windows-Betriebssystemadministratoren vom Zugriff auf Vom Betriebssystem gespeicherte oder verarbeitete Anwendungsdaten.

- Enthält eine Kundenschlüsseloption, die es mehr mandantendienstigen Diensten ermöglicht, die Schlüsselverwaltung pro Mandant zu ermöglichen.

- Verbessert die Fähigkeit von Microsoft 365, die Anforderungen von Kunden zu erfüllen, die bestimmte Complianceanforderungen hinsichtlich verschlüsselung haben.

Mithilfe von Customer Key können Sie eigene Kryptografieschlüssel mithilfe eines lokalen Hardwaredienstmoduls (Hardware Service Module, HSM) oder Azure Key Vault (AKV) generieren. Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV zum Steuern und Verwalten der kryptografischen Schlüssel, die von Office 365 verwendet werden. Nachdem Ihre Schlüssel in AKV gespeichert wurden, können sie als Stamm einer der Schlüsselbunde verwendet werden, die Ihre Postfachdaten oder -dateien verschlüsselt.

Ein weiterer Vorteil von Customer Key ist die Kontrolle über die Fähigkeit von Microsoft, Ihre Daten zu verarbeiten. Wenn Sie Daten aus Office 365 entfernen möchten, z. B. wenn Sie den Dienst bei Microsoft beenden oder einen Teil Ihrer in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und Customer Key als technische Steuerung verwenden. Durch das Entfernen von Daten wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann. Customer Key ist zusätzlich und ergänzt die Kunden-Lockbox, die Sie verwenden, um den Zugriff auf Ihre Daten durch Microsoft-Mitarbeiter zu steuern.

Informationen zum Einrichten von Customer Key für Microsoft 365 für Exchange Online, Microsoft Teams, SharePoint Online, einschließlich Teamwebsites und OneDrive for Business, finden Sie in den folgenden Artikeln:

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Verwalten von Kundenschlüsseln](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Verstehen des Verfügbarkeitsschlüssels](customer-key-availability-key-understand.md)
