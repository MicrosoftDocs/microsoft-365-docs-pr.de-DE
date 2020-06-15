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
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717346"
---
# <a name="service-encryption"></a>Dienst Verschlüsselung

Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten. Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:

## <a name="microsoft-managed-keys"></a>Von Microsoft verwaltete Schlüssel: 
Microsoft verwaltet alle kryptografischen Schlüssel einschließlich der Stammschlüssel für die Dienst Verschlüsselung. Diese Option ist derzeit in SharePoint Online und OneDrive für Unternehmen verfügbar. Diese Option wird derzeit für Exchange Online eingeführt. Microsoft-verwaltete Schlüssel bieten standardmäßige Dienst Verschlüsselung, es sei denn, Sie möchten mit dem Kundenschlüssel an Bord wählen. Wenn Sie zu einem späteren Zeitpunkt beschließen, die Verwendung des Kunden Schlüssels zu beenden, ohne den Pfad der Datenbereinigung zu befolgen, bleiben Ihre Daten mit den verwalteten Microsoft-Schlüsseln verschlüsselt. Ihre Daten werden immer mindestens auf dieser Standardstufe verschlüsselt. 

## <a name="customer-key"></a>Kundenschlüssel: 
Sie geben die mit der Dienst Verschlüsselung verwendeten Stammschlüssel an und verwalten diese Schlüssel mithilfe von Azure Key Vault. Microsoft verwaltet alle anderen Schlüssel. Diese Option wird als Kundenschlüssel bezeichnet und steht derzeit für Exchange Online, SharePoint Online und OneDrive für Unternehmen zur Verfügung. (Zuvor als erweiterte Verschlüsselung mit BYOK bezeichnet. Weitere Informationen finden Sie unter [Enhancing transparency and Control for Office 365 Customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the Original Announcement.)

Die Dienst Verschlüsselung bietet mehrere Vorteile. Beispiel: Kundenschlüssel:

- Bietet Rechtsschutz-und Verwaltungsfunktionen über einen starken Verschlüsselungsschutz hinaus.

- Enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.

- Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.

- Verbessert die Fähigkeit von Microsoft 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.

Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel generieren, indem Sie entweder ein lokales Hardware-Service Modul (HSM) oder ein Azure Key Vault (AKV) verwenden. Unabhängig davon, wie Sie den Schlüssel generieren, verwenden Sie AKV, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten. Nachdem Ihre Schlüssel in AKV gespeichert wurden, können Sie als Stamm einer der keychains verwendet werden, die ihre Postfachdaten oder-Dateien verschlüsseln.

Ein weiterer Vorteil von Customer Key ist die Kontrolle, die Sie über die Fähigkeit von Microsoft haben, Ihre Daten zu verarbeiten. Wenn Sie Daten aus Office 365 entfernen möchten, beispielsweise wenn Sie den Dienst mit Microsoft beenden oder einen Teil der in der Cloud gespeicherten Daten entfernen möchten, können Sie dies tun und den Kundenschlüssel als technische Steuerung verwenden. Dadurch wird sichergestellt, dass niemand, einschließlich Microsoft, auf die Daten zugreifen oder diese verarbeiten kann. Kundenschlüssel wird zusätzlich zu den Kunden-Lockbox ergänzt, die Sie zum Steuern des Zugriffs auf Ihre Daten durch Microsoft-Mitarbeiter verwenden.

Informationen zum Einrichten des Kunden Schlüssels für Microsoft 365 für Exchange Online, Skype for Business, SharePoint Online, einschließlich Team Websites und OneDrive für Unternehmen, finden Sie in den folgenden Artikeln:

- [Dienst Verschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Einrichten des Kunden Schlüssels](customer-key-set-up.md)

- [Verwalten des Kunden Schlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md)

- [Grundlegendes zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)

