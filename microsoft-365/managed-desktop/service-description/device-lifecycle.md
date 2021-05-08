---
title: Microsoft Managed Desktop Produktlebenszyklus
description: In diesem Artikel werden die Gerätespezifikationen aufgeführt, die in der Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245312"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop Produktlebenszyklus

Microsoft Managed Desktop bietet Benutzern die Sicherheit, dass sie immer Geräte verwenden, die die beste Leistung, Zuverlässigkeit, Design und Sicherheit bieten (z. B. Unterstützung für Features wie Windows Hello). Zu diesem Zweck Microsoft Managed Desktop einen kurzen Katalog mit ständig aktualisierten genehmigten Geräten. Sie können genehmigte Geräte anzeigen, indem Sie Microsoft Managed Desktop auf der Website [Geschäft Windows 10 Pro Geschäftsgeräte](https://www.microsoft.com/windowsforbusiness/view-all-devices) filtern.
 
In diesem Artikel wird der Lebenszyklus von Geräten beim Hinzufügen und Entfernen aus dem genehmigten Katalog beschrieben. 

> [!NOTE]
> In diesem Thema unterscheiden wir zwischen einem "Gerät" und einem "Produkt". Mit "Gerät" meinen wir einen einzelnen, bestimmten Computer. Beispielsweise beziehen sich "Seriennummer 1234", "Bills Laptop", "Freigegebene VM XYZ" auf bestimmte Geräte. Ein "Produkt" bezieht sich jedoch auf eine Sammlung oder Familie von Geräten. Beispiel: "Fabrikam Laptop", "Adatum ZX450 Laptop" usw. Dies ist wichtig, da Produkte unserer genehmigten Liste oder unserem Katalog hinzugefügt werden, und Geräte sind die Geräte, die für die Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Produktlebenszyklus

 Im Allgemeinen durchleben Produkte die folgenden Lebenszyklusphasen:

- [Produktfreigabe und -auswertung](#product-release-and-evaluation)
- [Primärer Verfügbarkeitszeitraum des Produkts](#product-primary-availability-period)
- [Produktkultzeit](#product-grace-period)
- [Produktverrentung](#product-retirement)


Diese Abbildung zeigt die gesamte Sequenz:

![Lebenszykluszeitachse: Beginnend mit der allgemeinen Produktverfügbarkeit dauert die "primäre Verfügbarkeit" zwei Jahre. In dieser Zeit endet das Zertifizierungsfenster, und irgendwann wird das Gerät onboardiert. Am Ende der primären Verfügbarkeit wird das Produkt archiviert, und die "Nachfrist" von drei Jahren beginnt. Ab dem Onboarding des Geräts hat es einen Zeitraum von drei Jahren, bis es aus der Verwaltung entfernt wird. Am Ende der Nachfrist entfernen wir das Produkt aus dem Katalog.](../../media/non-dark1-edits.PNG)

Produkte verbleiben bis zu 24 Monate <em></em> im Katalog, geräte verbleiben jedoch basierend auf ihren individuellen Registrierungsterminen drei Jahre lang unter Verwaltung. Tatsächlich verfügt jedes Produkt über drei wichtige Datumsangaben, aber jedes Gerät hat nur eins. Für Produkte werden alle drei Datumsangaben basierend auf dem Genehmigungsdatum <em>berechnet.</em>Daher veröffentlichen wir diese Datumsangaben bei der Genehmigung, damit Sie immer nach vorne schauen und den gesamten Lebenszyklus des Produkts entsprechend planen können.

In dieser Tabelle sind Beispieldaten für ein theoretisches Produkt aufgeführt:


|Produkt  |Genehmigtes Datum  |Ende der primären Verfügbarkeit  |Ende der Berechtigung  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

In dieser Tabelle sind Beispieldaten für theoretische Geräte *aufgeführt:*


|Geräte-ID  |Registrierungsdatum  |Fälligkeitsdatum  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Desktop#321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produktfreigabe und -auswertung

Der Produktlebenszyklus beginnt, wenn ein Hersteller das Produkt öffentlich veröffentlicht:

![Lebenszykluszeitachse mit Veröffentlichungs- und Evaluierungszeitraum](../../media/non-dark3-edits.PNG)

Während dieser Phase führt das Microsoft Managed Desktop die Bewertung und Zertifizierung eines Produkts durch. Das Team wertet dinge wie Zuverlässigkeit und Leistung unter anderem mit Windows, Einhaltung einer Hardwaregrundlinie, Marktstimmung sowie Inventar- und Kanalbereitschaft aus. Dieser Vorgang dauert in der Regel ungefähr sechs Wochen.
  
Microsoft Managed Desktop werden geräte nur innerhalb der ersten sechs Monate nach Verfügbarkeit zur Zertifizierung ausgewertet. Diese Richtlinie stellt sicher, dass wir uns immer auf die neueste Hardwaregeneration konzentrieren.
 
Am Ende dieser Phase fügt Microsoft Managed Desktop das Produkt der genehmigten Liste hinzu [und](device-list.md)veröffentlicht das Produkt effektiv für Kundenregistrierungen. Unabhängig vom Datum, an dem ein  Gerät zertifiziert ist, wird das genehmigte Datum auf das eigene datum der allgemeinen Verfügbarkeit des Produkts datiert. 


## <a name="product-primary-availability-period"></a>Primärer Verfügbarkeitszeitraum des Produkts

Dieser Zeitraum ist der Kern der Produktverfügbarkeit:

![Lebenszykluszeitachse mit primärer Verfügbarkeit](../../media/non-dark4-edits.PNG)

Jedes gerät, das während dieses Zeitraums registriert ist, erhält die volle Drei-Jahre-Unterstützung von Microsoft Managed Desktop (wie die blaue Zeitachse zeigt). Dieser Zeitraum dauert bis zu einem Enddatum, das auf 24 Monate ab dem allgemeinen Verfügbarkeitsdatum festgelegt ist.

Sie können sich diesen Zeitraum als effektiv "offene Registrierung" einfallen lassen. Um den Wert von Microsoft Managed Desktop zu maximieren, sollten Sie ihre Beschaffungsmodelle und ausgewählten Produkte so gestalten, dass sie innerhalb dieses Zeitraums fallen. Als kleines Beispiel sollten Sie vermeiden, sich auf einen Zwei-Jahres-Roll-out-Zeitraum zu einigen, indem Sie ein Produkt verwenden, das sich im [](#product-grace-period) letzten Monat der primären Verfügbarkeit befindet – die meisten dieser Geräte erhalten nicht die vollständigen drei Jahre der Microsoft Managed Desktop-Verwaltung (weitere Informationen finden Sie unter Nachfrist).  

## <a name="product-grace-period"></a>Produktkultzeit

Der Kulanzzeitraum des Produkts ist ein Zeitraum von drei Jahren nach der primären Verfügbarkeit. In dieser Phase können Sie Geräte registrieren, die aus einer unterstützten Produktfamilie gehören, halten jedoch weiterhin an den versprechenden Microsoft Managed Desktop hinsichtlich moderner Hardware- und Geräteleistung fest. Diese Phase eignet sich ideal für Kunden, die Beschaffungsentscheidungen getroffen haben, bevor sie mehr über Microsoft Managed Desktop. 

Wenn Sie vor der Registrierung bei Microsoft Managed Desktop vor kurzem genehmigte Geräte erworben haben, können Sie sie weiterhin registrieren, aber Sie erhalten keine vollständigen drei Jahre Verwaltung. Stattdessen fallen sie am Fälligkeitsdatum aus der Compliance aus, unabhängig davon, wann sie registriert wurden. Im Hintergrund behandeln Microsoft Managed Desktop diese Geräte so, als wären sie am letzten Tag der primären Verfügbarkeit registriert. In dieser Abbildung sehen Sie dieses Szenario, indem Sie sehen, dass sowohl das blaue als auch das grüne Gerät am selben Tag enden, trotz der einjährigen Unterschiede bei der Registrierung:


![Lebenszykluszeitachse mit Nachfrist](../../media/non-dark2-edits.PNG)

Das Fabrikam Laptop-Beispiel aus der vorherigen Tabelle veranschaulicht diese Situation: 

|Produkt  |Genehmigtes Datum  |Ende der primären Verfügbarkeit  |Ende der Berechtigung  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Als Kunde können Sie Fabrikam Laptops bis zum 1.6.2022 registrieren – sie werden jedoch alle so behandelt, als hätten Sie sie am 1.6.2019 registriert. Wenn Sie einen Fabrikam Laptop am 1.6.2021 registrieren, erhalten Sie nur ein Jahr Management. Mit dieser Richtlinie können Sie Teillebenszyklen aus Produkten extrahieren, die zuvor unterstützt wurden, anstatt neue Geräte vorzeitig zu beschaffen. 

Schließlich wird das Gerät in dieser [](device-list.md) Phase aus der Geräteliste entfernt und in die [Archivierte Geräteliste verschoben.](archived-device-list.md)


## <a name="product-retirement"></a>Produktverrentung

Die Produktverrentung ist die letzte Phase des Lebenszyklus. In dieser Phase können keine neuen Geräte dieses Produkttyps in Microsoft Managed Desktop registriert werden, und definitionsgemäß sind alle vorhandenen Geräte jetzt außerhalb ihrer zulässigen Drei-Jahres-Laufzeit. Während dieser Zeit Microsoft Managed Desktop das Gerät vollständig aus der öffentlichen Liste entfernt. Es ist auch während dieser Phase, in der Sie, wenn Sie noch keine Ersetzungen beschaffen haben, beginnen, verringerte Dienste zu sehen, da Microsoft Managed Desktop beginnt, auf den Geräten zu starten, die nicht kompatibel sind. 

## <a name="devices-that-are-out-of-compliance"></a>Geräte, die nicht kompatibel sind

Ein Gerät ist nicht mehr compliancekonform, wenn das zulässige Fenster für die Microsoft Managed Desktop verstrichen ist. Diese Situation tritt auf, wenn das Gerät drei Jahre management erreicht hat oder wenn dieser Produkttyp aus dem Gerätekatalog entfernt wird, unabhängig davon, welcher Fall zuerst auftritt. Sie sollten ihre Beschaffungszyklen immer so ans Ziel setzen, dass neue Geräte bereitgestellt werden, bevor aktuelle Geräte nicht mehr kompatibel sind.

Das Microsoft Managed Desktop-Team weiß, dass beschaffungszyklen lang sind und um langfristige Budgets herum geplant sind. Um sicherzustellen, dass Sie den Status Ihrer Gerätegesamtheit [](https://aka.ms/mmdportal) immer kennen, stellen wir eine Website bereit, auf der jedes Gerät unter Verwaltung, das Alter und ein Status aufgeführt sind, der die Kompatibilität angibt. Die Website hilft Ihnen, immer über die neuesten Informationen zum Gerätealter zu verfügen und den Bericht in jedem Beschaffungsplanungszyklus zu verwenden. 







