---
title: Office 365-Dienstverschlüsselung
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Grundlegendes zur Ausfallsicherheit von Daten in Microsoft Office 365.'
ms.openlocfilehash: 7fec40db9ce12b52d37f2003d7ee8db68739aa41
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38690440"
---
# <a name="office-365-service-encryption"></a>Office 365-Dienstverschlüsselung

Zusätzlich zur Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten. Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:
- Microsoft verwaltet alle kryptografischen Schlüssel. (Diese Option ist derzeit in SharePoint Online, OneDrive für Unternehmen und Skype for Business verfügbar. Es befindet sich derzeit in der Roadmap für Exchange Online.)
- Der Kunde stellt Stammschlüssel bereit, die mit der Dienst Verschlüsselung verwendet werden, und der Kunde verwaltet diese Schlüssel mithilfe von Azure Key Vault. Microsoft verwaltet alle anderen Schlüssel. Diese Option wird als Kundenschlüssel bezeichnet und steht derzeit für Exchange Online, SharePoint Online und OneDrive für Unternehmen zur Verfügung. (Zuvor als erweiterte Verschlüsselung mit BYOK bezeichnet. Weitere Informationen finden Sie unter [Enhancing transparency and Control for Office 365 Customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the Original Announcement.)

Die Dienst Verschlüsselung bietet mehrere Vorteile. Beispielsweise:
- bietet Rechtsschutz-und Verwaltungsfunktionen über einen starken Verschlüsselungsschutz hinaus.
- enthält eine Option für Kundenschlüssel, mit der mehrere mandantenfähige Dienste für eine mandantenorientierte Schlüsselverwaltung bereitstellen können.
- ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.
- erhöht die Fähigkeit von Office 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.

## <a name="customer-key"></a>Kundenschlüssel
Mit dem Kundenschlüssel können Sie eigene kryptografische Schlüssel mithilfe eines lokalen HSM oder eines Azure-Schlüssel Tresors generieren. Unabhängig davon, wie der Schlüssel generiert wird, verwenden Kunden Azure Key Vault, um die von Office 365 verwendeten kryptografischen Schlüssel zu steuern und zu verwalten. Nachdem Ihre Schlüssel in Azure Key Vault gespeichert wurden, können Sie Arbeitsauslastungen wie Exchange Online und SharePoint Online zugewiesen und als Stamm des Schlüsselbunds verwendet werden, der zum Verschlüsseln der Postfachdaten und-Dateien verwendet wird.
Einer der anderen Vorteile der Verwendung des Kunden Schlüssels besteht darin, die Fähigkeit von Microsoft zu steuern, Kundendaten zu verarbeiten. Diese Funktion besteht darin, dass ein Kunde, der Daten aus Office 365 entfernen möchte (beispielsweise wenn ein Kunde den Dienst mit Microsoft beendet oder einen Teil der in der Cloud gespeicherten Daten entfernt), dies tun kann und den Kundenschlüssel als technische Kontrolle verwendet, um sicherzustellen, dass niemand , einschließlich Microsoft, kann auf die Daten zugreifen oder diese verarbeiten. Dies ist zusätzlich (und eine Ergänzung) zur Customer Lockbox-Funktion, die zum Steuern des Zugriffs auf Kundendaten durch Microsoft-Mitarbeiter verwendet werden kann.

Informationen zum Einrichten des Kunden Schlüssels für Office 365 für Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen finden Sie unter [Steuern der Daten in Office 365 mithilfe des Kunden Schlüssels](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Weitere Informationen finden Sie im [Kundenschlüssel für Office 365 FAQ](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)und [Verwalten und Steuern ihrer Daten, um die Anforderungen an die Compliance mit dem Kundenschlüssel erfüllen zu können](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).
