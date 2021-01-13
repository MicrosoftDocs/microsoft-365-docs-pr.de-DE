---
title: Microsoft Managed Desktop – Produktlebenszyklus
description: In diesem Artikel werden die Gerätespezifikationen aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841199"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop – Produktlebenszyklus

Microsoft Managed Desktop bietet Benutzern den Vorteil, dass sie immer Geräte verwenden, die die beste Leistung, Zuverlässigkeit, den besten Entwurf und die beste Sicherheit bieten (z. B. Unterstützung für Features wie Windows Hello). Zu diesem Zweck verwaltet Microsoft Managed Desktop einen kurzen Katalog mit kontinuierlich aktualisierten [genehmigten Geräten.](device-list.md) 
 
In diesem Artikel wird der Lebenszyklus von Geräten beim Hinzufügen und Entfernen aus dem genehmigten Katalog beschrieben. 

> [!NOTE]
> In diesem Thema wird zwischen einem "Gerät" und einem "Produkt" unterschieden. "Gerät" bedeutet einen einzelnen, bestimmten Computer. Beispielsweise beziehen sich "Seriennummer 1234", "Bills Laptop", "Freigegebene VM XYZ" auf bestimmte Geräte. Ein "Produkt" bezieht sich jedoch auf eine Sammlung oder Gerätefamilie. Beispiel: "Fabrikam Laptop", "Adatum ZX450 Laptop" usw. Dies ist wichtig, da [](device-list.md)Produkte unserer genehmigten Liste oder unserem Katalog hinzugefügt werden und Geräte für Microsoft Managed Desktop registriert werden.

## <a name="product-lifecycle"></a>Produktlebenszyklus

 Im Allgemeinen durchleben Produkte diese Lebenszyklusphasen:

- [Produktversion und -evaluierung](#product-release-and-evaluation)
- [Zeitraum für primäre Produktverfügbarkeit](#product-primary-availability-period)
- [Kulanzfrist für Produkte](#product-grace-period)
- [Produktverrentung](#product-retirement)


Diese Abbildung zeigt die gesamte Sequenz:

![Lebenszykluszeitachse: Beginnend mit der allgemeinen Produktverfügbarkeit dauert die "primäre Verfügbarkeit" zwei Jahre. Während dieser Zeit endet das Zertifizierungsfenster, und zu einem bestimmten Zeitpunkt wird das Gerät in das Onboarding ein- und aus- Am Ende der primären Verfügbarkeit wird das Produkt archiviert, und die "Nachfrist" von drei Jahren beginnt. Ab dem Onboarding des Geräts gilt eine Drei-Jahres-Nutzungsdauer, bis es aus der Verwaltung entfernt wird. Am Ende der Kulanzfrist entfernen wir das Produkt aus dem Katalog.](../../media/non-dark1-edits.PNG)

Produkte verbleiben bis zu 24 Monate im Katalog, geräte <em>bleiben</em> jedoch basierend auf ihren individuellen Registrierungsterminen drei Jahre lang im Management. Effektiv verfügt jedes Produkt über drei wichtige Datumsangaben, aber jedes Gerät verfügt nur über ein Datum. Für Produkte werden alle drei Datumsangaben basierend auf dem Genehmigungsdatum <em>berechnet.</em>Daher veröffentlichen wir diese Datumsangaben bei der Genehmigung, damit Sie immer nach vorne schauen und den gesamten Lebenszyklus des Produkts entsprechend planen können.

Diese Tabelle enthält Beispieldaten für ein theoretisches Produkt:


|Produkt  |Genehmigtes Datum  |Ende der primären Verfügbarkeit  |Ende der Berechtigung  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Diese Tabelle enthält Beispieldaten für theoretischer *Geräte:*


|Geräte-ID  |Registrierungsdatum  |Auspensionsdatum  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Desktop #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produktversion und -evaluierung

Der Produktlebenszyklus beginnt, wenn ein Hersteller das Produkt öffentlich veröffentlicht:

![Lebenszykluszeitachse mit Veröffentlichungs- und Evaluierungszeitraum](../../media/non-dark3-edits.PNG)

In dieser Phase führt das Microsoft Managed Desktop Engineering-Team die Evaluierung und Zertifizierung eines Produkts durch. Das Team wertet unter anderem Zuverlässigkeit und Leistung mit Windows, die Einhaltung einer Hardwarebasis, die Marktstimmung sowie Inventar- und Kanalbereitschaft aus. Dieser Vorgang dauert in der Regel etwa sechs Wochen.
  
Microsoft Managed Desktop wertet Geräte nur innerhalb der ersten sechs Monate nach Verfügbarkeit zur Zertifizierung aus. Diese Richtlinie stellt sicher, dass wir uns immer auf die neueste Hardwaregenerierung konzentrieren.
 
Am Ende dieser Phase fügt Microsoft Managed Desktop das Produkt der genehmigten Liste hinzu [und](device-list.md)veröffentlicht das Produkt effektiv für Kundenregistrierungen. Unabhängig vom Datum, an dem ein  Gerät zertifiziert wurde, wird sein genehmigtes Datum auf das datum der allgemeinen Verfügbarkeit des Produkts zurückgedeterminiert. 


## <a name="product-primary-availability-period"></a>Zeitraum für primäre Produktverfügbarkeit

Dieser Zeitraum ist der Kern der Produktverfügbarkeit:

![Lebenszykluszeitachse mit primärer Verfügbarkeit](../../media/non-dark4-edits.PNG)

Jedes Gerät, das während dieses Zeitraums registriert wurde, erhält die vollständigen drei Jahre Support von Microsoft Managed Desktop (wie in der blauen Zeitachse dargestellt). Dieser Zeitraum gilt bis zu einem Enddatum, das auf 24 Monate ab dem Datum der allgemeinen Verfügbarkeit festgelegt ist.

Sie können sich diesen Zeitraum als effektive "offene Registrierung" einfallen lassen. Um den Wert von Microsoft Managed Desktop zu maximieren, sollten Sie ihre Beschaffungsmodelle und ausgewählten Produkte so gestalten, dass sie innerhalb dieses Zeitraums fallen. Als kleines Beispiel sollten Sie vermeiden, sich über einen Zwei-Jahres-Einführungszeitraum mit einem Produkt zu informieren, das sich im letzten Monat der [](#product-grace-period) primären Verfügbarkeit befindet – die meisten dieser Geräte erhalten nicht die vollständigen drei Jahre der Verwaltung von Microsoft Managed Desktop (weitere Informationen finden Sie unter Karenzeit).  

## <a name="product-grace-period"></a>Kulanzfrist für Produkte

Der Kulanzzeitraum des Produkts beträgt drei Jahre nach der primären Verfügbarkeit. In dieser Phase können Sie Geräte registrieren, die aus einer unterstützten Produktfamilie kommen, sich jedoch weiterhin an die Zusagen von Microsoft Managed Desktop hinsichtlich moderner Hardware und Geräteleistung halten. Diese Phase eignet sich ideal für Kunden, die Beschaffungsentscheidungen getroffen haben, bevor Sie sich mit Microsoft Managed Desktop aus der Kenntnis machen. 

Wenn Sie vor der Registrierung bei Microsoft Managed Desktop vor kurzem genehmigte Geräte gekauft haben, können Sie sie weiterhin registrieren, erhalten aber keine vollständigen drei Jahre Verwaltung. Stattdessen fallen sie beim Auspensionsdatum aus der Compliance heraus, unabhängig davon, wann sie registriert wurden. Im Hintergrund behandelt Microsoft Managed Desktop diese Geräte so, als wären sie am letzten Tag der primären Verfügbarkeit registriert worden. In dieser Abbildung sehen Sie dieses Szenario, indem Sie erkennen, dass sowohl das blaue als auch das grüne Gerät am selben Tag enden, obwohl sich die Registrierung um ein Jahr unterschied:


![Lebenszykluszeitachse mit Kulanzfrist](../../media/non-dark2-edits.PNG)

Das Beispiel "Fabrikam Laptop" aus der vorherigen Tabelle veranschaulicht diese Situation: 

|Produkt  |Genehmigtes Datum  |Ende der primären Verfügbarkeit  |Ende der Berechtigung  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Als Kunde können Sie Fabrikam Laptops bis zum 01.06.2022 registrieren– sie werden jedoch alle so behandelt, als ob Sie sie am 1.6.2019 registriert hätten. Wenn Sie einen Fabrikam Laptop am 01.06.2021 registrieren, erhalten Sie nur ein Jahr Management. Mit dieser Richtlinie können Sie Teillebenszyklen aus Produkten extrahieren, die zuvor unterstützt wurden, anstatt neue Geräte vorzeitig beschaffen zu müssen. 

Schließlich wird das Gerät während dieser [](device-list.md) Phase aus der Geräteliste entfernt und in die Liste der [archivierten Geräte verschoben.](archived-device-list.md)


## <a name="product-retirement"></a>Produktverrentung

Die Produktverrentung ist die letzte Phase des Lebenszyklus. In dieser Phase können keine neuen Geräte dieses Produkttyps bei Microsoft Managed Desktop registriert werden, und definitionsgemäß liegen alle vorhandenen Geräte jetzt außerhalb der zulässigen Drei-Jahres-Laufzeit. Während dieser Zeit entfernt Microsoft Managed Desktop das Gerät vollständig aus der öffentlichen Liste. In dieser Phase sehen Sie auch, wenn Sie noch keine Ersetzungen beschaffen haben, verringerte Dienste, wenn Microsoft Managed Desktop auf den Geräten, die nicht kompatibel sind, anfängt, zu einem Abwärtsstart zu kommen. 

## <a name="devices-that-are-out-of-compliance"></a>Geräte, die nicht kompatibel sind

Wenn das zulässige Fenster für die Verwaltung von Microsoft Managed Desktop abgelaufen ist, ist die Kompatibilität eines Geräts nicht mehr zulässig. Diese Situation tritt auf, wenn das Gerät die dreijährige Verwaltung erreicht hat oder wenn dieser Produkttyp aus dem Gerätekatalog entfernt wird, unabhängig davon, was zuerst auftritt. Sie sollten ihre Beschaffungszyklen immer so anzielen, dass neue Geräte bereitgestellt werden, bevor aktuelle Geräte nicht mehr kompatibel sind.

Das Microsoft Managed Desktop-Team weiß, dass beschaffungszyklen lang sind und um lang dauernde Budgets herum geplant sind. Um sicherzustellen, dass Sie den Zustand der Gerätegesamtheit [](https://aka.ms/mmdportal) immer kennen, stellen wir eine Website bereit, auf der jedes gerät, das sich in der Verwaltung, in seinem Alter und in einem Status zur Einhaltung der Vorschriften auflistet. Die Website hilft Ihnen dabei, immer über die neuesten Informationen zum Gerätealter zu verfügen und den Bericht in jedem Beschaffungsplanungszyklus zu verwenden. 







