---
title: Microsoft Managed Desktop-Produktlebenszyklus
description: In diesem Artikel werden die Gerätespezifikationen aufgeführt, die in Microsoft Managed Desktop verwendet werden.
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
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop-Produktlebenszyklus

Microsoft Managed Desktop bietet Benutzern die Sicherheit, dass sie immer Geräte verwenden, die die beste Leistung, Zuverlässigkeit, Design und Sicherheit bieten (z. B. Unterstützung für Features wie Windows Hello). Zu diesem Zweck verwaltet Microsoft Managed Desktop einen kurzen Katalog mit ständig aktualisierten genehmigten Geräten. Sie können genehmigte Geräte anzeigen, indem Sie auf der Windows [10](https://www.microsoft.com/windowsforbusiness/view-all-devices) Pro-Geschäftsgeräte-Website nach Microsoft Managed Desktop filtern.
 
In diesem Artikel wird der Lebenszyklus von Geräten beim Hinzufügen und Entfernen aus dem genehmigten Katalog beschrieben. 

> [!NOTE]
> In diesem Thema unterscheiden wir zwischen einem "Gerät" und einem "Produkt". Mit "Gerät" meinen wir einen einzelnen, bestimmten Computer. Beispielsweise beziehen sich "Seriennummer 1234", "Bills Laptop", "Freigegebene VM XYZ" auf bestimmte Geräte. Ein "Produkt" bezieht sich jedoch auf eine Sammlung oder Familie von Geräten. Beispiel: "Fabrikam Laptop", "Adatum ZX450 Laptop" usw. Dies ist wichtig, da Produkte unserer genehmigten Liste oder unserem Katalog hinzugefügt werden und Geräte die Geräte sind, die bei Microsoft Managed Desktop registriert werden.

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

In dieser Phase führt das Microsoft Managed Desktop Engineering-Team die Bewertung und Zertifizierung eines Produkts durch. Das Team bewertet unter anderem Zuverlässigkeit und Leistung mit Windows, Die Einhaltung einer Hardwaregrundlinie, Marktstimmung sowie Inventar- und Kanalbereitschaft. Dieser Vorgang dauert in der Regel ungefähr sechs Wochen.
  
Microsoft Managed Desktop wertet Geräte nur innerhalb der ersten sechs Monate nach Verfügbarkeit zur Zertifizierung aus. Diese Richtlinie stellt sicher, dass wir uns immer auf die neueste Hardwaregeneration konzentrieren.
 
Am Ende dieser Phase fügt Microsoft Managed Desktop das Produkt der genehmigten Liste hinzu [und](device-list.md)veröffentlicht das Produkt effektiv für Kundenregistrierungen. Unabhängig vom Datum, an dem ein  Gerät zertifiziert ist, wird das genehmigte Datum auf das eigene datum der allgemeinen Verfügbarkeit des Produkts datiert. 


## <a name="product-primary-availability-period"></a>Primärer Verfügbarkeitszeitraum des Produkts

Dieser Zeitraum ist der Kern der Produktverfügbarkeit:

![Lebenszykluszeitachse mit primärer Verfügbarkeit](../../media/non-dark4-edits.PNG)

Jedes gerät, das während dieses Zeitraums registriert ist, erhält die vollständigen drei Jahre Support von Microsoft Managed Desktop (wie in der blauen Zeitachse dargestellt). Dieser Zeitraum dauert bis zu einem Enddatum, das auf 24 Monate ab dem allgemeinen Verfügbarkeitsdatum festgelegt ist.

Sie können sich diesen Zeitraum als effektive "offene Registrierung" einfallen lassen. Um den Wert von Microsoft Managed Desktop zu maximieren, sollten Sie ihre Beschaffungsmodelle und ausgewählten Produkte so gestalten, dass sie innerhalb dieses Zeitraums fallen. Als kleines Beispiel sollten Sie vermeiden, sich mit einem Produkt, das sich im letzten Monat der primären Verfügbarkeit befindet, auf einen Zwei-Jahres-Roll-Out-Zeitraum zurückweichen – die meisten dieser Geräte erhalten nicht die vollständigen drei Jahre der Verwaltung von Microsoft Managed Desktop (weitere Informationen finden Sie unter Nachfrist). [](#product-grace-period)  

## <a name="product-grace-period"></a>Produktkultzeit

Der Kulanzzeitraum des Produkts ist ein Zeitraum von drei Jahren nach der primären Verfügbarkeit. In dieser Phase können Sie Geräte registrieren, die aus einer unterstützten Produktfamilie gehören, aber weiterhin die Zusagen von Microsoft Managed Desktop hinsichtlich moderner Hardware- und Geräteleistung einhalten. Diese Phase eignet sich ideal für Kunden, die Beschaffungsentscheidungen getroffen haben, bevor sie von Microsoft Managed Desktop erfahren. 

Wenn Sie vor der Registrierung bei Microsoft Managed Desktop vor kurzem genehmigte Geräte erworben haben, können Sie sie weiterhin registrieren, aber Sie erhalten keine vollständigen drei Jahre Verwaltung. Stattdessen fallen sie am Fälligkeitsdatum aus der Compliance aus, unabhängig davon, wann sie registriert wurden. Im Hintergrund behandelt Microsoft Managed Desktop diese Geräte so, als wären sie am letzten Tag der primären Verfügbarkeit registriert. In dieser Abbildung sehen Sie dieses Szenario, indem Sie sehen, dass sowohl das blaue als auch das grüne Gerät am selben Tag enden, trotz der einjährigen Unterschiede bei der Registrierung:


![Lebenszykluszeitachse mit Nachfrist](../../media/non-dark2-edits.PNG)

Das Fabrikam Laptop-Beispiel aus der vorherigen Tabelle veranschaulicht diese Situation: 

|Produkt  |Genehmigtes Datum  |Ende der primären Verfügbarkeit  |Ende der Berechtigung  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Als Kunde können Sie Fabrikam Laptops bis zum 1.6.2022 registrieren – sie werden jedoch alle so behandelt, als hätten Sie sie am 1.6.2019 registriert. Wenn Sie einen Fabrikam Laptop am 1.6.2021 registrieren, erhalten Sie nur ein Jahr Management. Mit dieser Richtlinie können Sie Teillebenszyklen aus Produkten extrahieren, die zuvor unterstützt wurden, anstatt neue Geräte vorzeitig zu beschaffen. 

Schließlich wird das Gerät in dieser [](device-list.md) Phase aus der Geräteliste entfernt und in die [Archivierte Geräteliste verschoben.](archived-device-list.md)


## <a name="product-retirement"></a>Produktverrentung

Die Produktverrentung ist die letzte Phase des Lebenszyklus. In dieser Phase können keine neuen Geräte dieses Produkttyps bei Microsoft Managed Desktop registriert werden, und definitionsgemäß sind alle vorhandenen Geräte jetzt außerhalb ihrer zulässigen Drei-Jahres-Laufzeit. In dieser Zeit entfernt Microsoft Managed Desktop das Gerät vollständig aus der öffentlichen Liste. Es ist auch in dieser Phase, in der Sie, wenn Sie noch keine Ersetzungen bezogen haben, mit der Setzung von Diensten beginnen, wenn Microsoft Managed Desktop beginnt, die Nicht-Compliance-Geräte herunterfahren zu lassen. 

## <a name="devices-that-are-out-of-compliance"></a>Geräte, die nicht kompatibel sind

Ein Gerät ist nicht mehr compliancekonform, wenn das zulässige Fenster für die Verwaltung von Microsoft Managed Desktop abgelaufen ist. Diese Situation tritt auf, wenn das Gerät drei Jahre management erreicht hat oder wenn dieser Produkttyp aus dem Gerätekatalog entfernt wird, unabhängig davon, welcher Fall zuerst auftritt. Sie sollten ihre Beschaffungszyklen immer so ans Ziel setzen, dass neue Geräte bereitgestellt werden, bevor aktuelle Geräte nicht mehr kompatibel sind.

Das Microsoft Managed Desktop-Team weiß, dass die Beschaffungszyklen lang sind und um lange laufende Budgets herum geplant sind. Um sicherzustellen, dass Sie den Status Ihrer Gerätegesamtheit [](https://aka.ms/mmdportal) immer kennen, stellen wir eine Website bereit, auf der jedes Gerät unter Verwaltung, das Alter und ein Status aufgeführt sind, der die Kompatibilität angibt. Die Website hilft Ihnen, immer über die neuesten Informationen zum Gerätealter zu verfügen und den Bericht in jedem Beschaffungsplanungszyklus zu verwenden. 







