---
title: US-Export Verwaltungsvorschriften (EAR)
description: Microsoft-Cloud-Dienste helfen Kunden, die den US-Export Verwaltungsvorschriften (EAR) unterliegen, Ihre Compliance-Anforderungen zu erfüllen und das Export Kontroll Risiko zu managen.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 1adf0bab35c921dd416028747b0309e5ad5f3055
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601962"
---
# <a name="us-export-administration-regulations-ear"></a>US-Export Verwaltungsvorschriften (EAR)

## <a name="about-the-ear"></a>Über das Ohr

Das US Department of Commerce erzwingt die Export Verwaltungsvorschriften (EAR) über das [Bureau of Industry and Security (bis)](https://www.bis.doc.gov/). Das Ohr regelt und auferlegt Steuerelemente für den Export und den Wiederexport der meisten kommerziellen Güter, Software und Technologien, einschließlich "Dual-Use"-Elemente, die sowohl für kommerzielle und militärische Zwecke als auch für bestimmte Verteidigungs Elemente verwendet werden können.

Die bis-Anleitung besagt, dass, wenn Daten oder Software in die Cloud hochgeladen oder zwischen Benutzer Knoten übertragen werden, der Kunde, nicht der Cloud-Anbieter, der "Exporteur" ist, der dafür verantwortlich ist, sicherzustellen, dass die Übertragung, Speicherung und der Zugriff auf diese Daten oder Software entspricht dem Ohr.

[Gemäß der BIZ](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file)bezieht sich der *Export* auf die Übertragung geschützter Technologien oder technischer Daten an ein fremdes Ziel oder dessen Veröffentlichung an eine ausländische Person in den Vereinigten Staaten (wird auch als *Export*bezeichnet). Das Ohr steuert im großen und ganzen:

- Exporte aus den Vereinigten Staaten.
- Erneute Exporte oder erneute Übertragungen von US-Origin-Elementen und bestimmten Produkten mit Ursprung in Drittländern mit mehr als einem *de-minimis* -Anteil von US-Origin-Inhalten.
- Übermittlungen oder Offenlegungen an Personen aus anderen Ländern.

Elemente, die dem Ohr unterliegen, finden Sie in der Commerce Control List (CCL), für die jedem Element eine eindeutige [Export Kontroll Klassifizierungs Nummer (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)zugewiesen ist. Elemente, die nicht in der CCL aufgeführt sind, sind als EAR99 festgelegt, und für die meisten EAR99-kommerziellen Produkte wird keine Lizenz zum Exportieren benötigt. Je nach Ziel, Endbenutzer oder Endverwendung des Elements kann selbst für ein EAR99-Element jedoch eine bis-Exportlizenz erforderlich sein.

Die [letzte Regel](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations), veröffentlicht im Juni 2016, verdeutlicht, dass die Ear-Lizenzierungsanforderungen auch nicht für die Übertragung und Speicherung von nicht klassifizierten technischen Daten und Software gelten würden, wenn Sie über eine verschlüsselte End-to-End-Verschlüsselung mit FIPS 140-2 validierte kryptografische Module verlegt wurden und nicht absichtlich in einem Militär Embargoland oder in der Russischen Föderation gespeichert wurden.

## <a name="microsoft-and-the-ear"></a>Microsoft und das Ohr

Microsoft-Technologien,-Produkte und-Dienste unterliegen den US-Export Verwaltungsvorschriften (EAR). Zwar gibt es keine Konformitätszertifizierung für das Ohr, Microsoft Azure, Microsoft Azure Regierung und Microsoft Office 365 Government (GCCHigh-und DoD-Umgebungen) bieten wichtige Features und Tools, die berechtigten Kunden helfen, die dem Ear Manage Export unterstützen. Steuern von Risiken und erfüllen der Compliance-Anforderungen

Die US-Commerce-Abteilung, die das Ohr erzwingt, hat die Position übernommen, dass Kunden, nicht Cloud-Dienstanbieter wie Microsoft, als Exporteure eigener Kundendaten betrachtet werden. Während die meisten Kundendaten nicht als "Technologie" oder "Technische Daten" gelten, die den Ear-Exportkontrollen unterliegen, sind die Microsoft-bereichsübergreifenden Cloud-Dienste so strukturiert, dass Kunden die potenziellen Export Steuerungs Risiken besser managen und deutlich abschwächen. Microsoft empfiehlt die Verwendung von Government Cloud Services für berechtigte Kunden in der Regel, jedoch nicht ausschließlich. Mit der entsprechenden Planung können Kunden die folgenden Tools und ihre eigenen internen Verfahren verwenden, um die vollständige Einhaltung der US-Exportkontrollen zu gewährleisten.

- **Steuerelemente für den Datenspeicherort**. Kunden haben Einblick in die Speicherung Ihrer Daten und den Zugriff auf robuste Tools, um den Speicherplatz einzuschränken. Sie können daher sicherstellen, dass Ihre Daten in den USA gespeichert werden und die Übertragung kontrollierter Technologien oder technischer Daten außerhalb der Vereinigten Staaten minimiert wird. Darüber hinaus werden Kundendaten nicht an einem nicht konformen Standort gespeichert, und zwar im Einklang mit den Ear-verboten, in denen Daten "absichtlich gespeichert" werden: kein Azure-Rechenzentrum befindet sich in einem der 25 Gruppen D:5 Länder oder der Russischen Föderation.
- **End-to-End-Verschlüsselung**. Durch die Nutzung der End-to-End-Verschlüsselung Safe Harbor für physikalische Speicherorte, die im Ohr angegeben sind, bieten Microsoft-bezogene Cloud-Dienste Verschlüsselungsfunktionen, die zum Schutz vor Export Steuerungs Risiken beitragen können. Sie bieten Kunden außerdem eine [Breite Palette von Optionen zum Verschlüsseln von Daten](https://aka.ms/Azure-Encryption-Overview) in der Übertragung und im Ruhezustand sowie die Flexibilität, zwischen Verschlüsselungsoptionen auszuwählen.
- **Tools und Protokolle zur Verhinderung nicht autorisierter Exporte**. Die Verwendung von Verschlüsselung hilft auch vor potenziellen Exporten (oder als Wiederexport) unter dem Ohr zu schützen, da selbst wenn eine nicht-US-Person Zugriff auf verschlüsselte Daten hat, nichts offenbart wird, wenn Sie die Daten nicht lesen oder verstehen können, während Sie verschlüsselt werden; Daher gibt es keine "Freigabe" von kontrollierten Daten.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft-Clouddienste im Leistungsumfang

- [Azure und Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 Government (gcc-High und DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>Implementierung

Übersicht über US-Exportkontrollen und Anleitungen für Kunden, die ihre Verpflichtungen unter dem Ohr bewerten.

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Was muss ich tun, um Exportkontrollen bei der Verwendung von Microsoft Cloud Services einzuhalten?**

Unter dem Ohr gilt: Wenn Daten auf einen cloudserver wie die Microsoft-Cloud hochgeladen werden, wird der Kunde, der die Daten besitzt – nicht der Anbieter für Cloud-Dienste – als Exporteur betrachtet. Aus diesem Grund muss der Besitzer der Daten – d. h. der Microsoft-Kunde – sorgfältig prüfen, wie die Verwendung der Microsoft-Cloud dazu führen kann, dass US-Steuerelemente exportiert werden, und bestimmen, ob die Daten, die Sie verwenden oder dort speichern möchten, möglicherweise Ear-Kontrollen unterliegen. , und wenn ja, welche Steuerelemente angewendet werden. Erfahren Sie mehr darüber, wie [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) und [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) Cloud-Dienste Kunden dabei unterstützen können, Ihre vollständige Compliance mit den US-Exportkontrollen sicherzustellen.

**Unterliegen Microsoft-Technologien,-Produkte und-Dienste dem Ohr?**

Die meisten Microsoft-Technologien,-Produkte und-Dienste bieten entweder:

- Sind nicht dem Ohr unterworfen und befinden sich daher nicht in der Commerce-Steuerelementliste und haben keine ECCN;
- Oder es handelt sich um EAR99 oder 5D992-Massenmarkt, der von Microsoft selbst klassifiziert werden kann und möglicherweise ohne Lizenz in nicht Embargoländer exportiert wird (NLR).

Allerdings wurden einigen Microsoft-Produkten ein ECCN zugewiesen, das möglicherweise eine Lizenz erfordert oder auch nicht. Konsultieren Sie das Ohr oder den Rechtsbeistand, um den entsprechenden Lizenztyp und die berechtigten Länder für Exportzwecke zu ermitteln.

**Worin besteht der Unterschied zwischen dem Ohr und dem internationalen Verkehr mit Rüstungs Vorschriften (ITAR)?**

Die primären US-Exportsteuerelemente mit der umfassendsten Anwendung sind das Ohr, das vom US-Handelsministerium verwaltet wird. Das Ohr gilt für Elemente mit doppeltem Verwendungszweck, die sowohl kommerzielle als auch militärische Anwendungen aufweisen, sowie Elemente mit rein kommerziellen Anwendungen.

Die Vereinigten Staaten verfügen außerdem über separate und speziellere Exportkontrollbestimmungen wie ITAR, die die sensibelsten Elemente und Technologien Regeln. Sie werden vom US-amerikanischen Außenministerium verwaltet und unterliegen dem Export, dem temporären Import, dem Wiederexport und der Übertragung von zahlreichen militärischen, Verteidigungs-und Nachrichtendienst Elementen (auch bekannt als "Defense articles"), einschließlich der dazugehörigen technischen Daten.

## <a name="resources"></a>Ressourcen

- [Exportieren von Microsoft-Produkten: Übersicht](https://www.microsoft.com/exporting/overview.aspx)
- [Exportieren von Microsoft-Produkten: FAQ](https://www.microsoft.com/exporting/faq.aspx)
- [Exportieren von Microsoft-Produkten: Produktsuche](https://www.microsoft.com/exporting/exporting-information.aspx)
- [Export Einschränkungen für Kryptografie](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft und FIPS 140-2](offering-fips-140-2.md)
- [Microsoft und ITAR](offering-itar.md)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
