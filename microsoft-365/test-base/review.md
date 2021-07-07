---
title: Überprüfung
description: Lesen Sie den Abschnitt nach dem Onboarding.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322878"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Schritt 6: Überprüfen Sie Ihre Auswahl, um Ihr Paket zu erstellen.

1.  Auf dieser Registerkarte zeigt der Dienst Ihre Testdetails an und führt eine schnelle Überprüfung der Vollständigkeit aus. 

    Eine ```Validation passed``` oder eine Meldung zeigt ```Validation failed``` an, ob Sie mit den nächsten Schritten fortfahren können oder nicht.

2.  Überprüfen Sie Ihre Testdetails, und klicken Sie auf die Schaltfläche, wenn Sie zufrieden ```Create``` sind. 

![Überprüfung anzeigen](Media/validation.png)

3.  Dadurch wird ihr Paket in die Testbasisumgebung integriert. Wenn Ihr Paket erfolgreich erstellt wurde, wird ein automatisierter Test ausgelöst, der überprüft, ob Ihr Paket erfolgreich in Azure ausgeführt werden kann.

![Erfolgreiches Ergebnis](Media/successful.png)

> [!Note]
> Sie erhalten eine Benachrichtigung vom Azure-Portal, um Sie über den Erfolg oder Misserfolg der Paketüberprüfung zu benachrichtigen. 
>
> Bitte beachten Sie, dass der Vorgang bis zu 24 Stunden dauern kann. Daher ist es wahrscheinlich, dass ihre Webseite ein Timeout aufweist, wenn Sie nicht aktiv sind. Daher werden Sie in der Benachrichtigung nicht über den Abschluss dieser Ausführung bei Bedarf informiert. 

  - Wenn dies geschieht, können Sie den Status Ihres Pakets auf der ```Manage packages``` Registerkarte anzeigen.

![Abbildung zum Verwalten von Paketen](Media/managepackages.png)

  - Bei erfolgreichen Tests können die Ergebnisse über die ```Test Summary``` ```Security Updates Results``` Seiten in ```Feature Updates Results``` geplanten Intervallen angezeigt werden, die häufig einige Tage nach dem Upload beginnen.
  
  - Bei fehlgeschlagenen Tests müssen Sie ein neues Paket hochladen. 
  
    Sie können die ```test logs``` zur weiteren Analyse von " und den Seiten ```Security update results``` ```Feature updates results``` herunterladen.

  - Wenn wiederholte Testfehler auftreten, wenden Sie sich an testbasepreview@microsoft.com, um Details zu Ihrem Fehler zu erhalten. 

## <a name="next-steps"></a>Nächste Schritte

Entdecken Sie unsere Inhaltsrichtlinien über den folgenden Link.
> [!div class="nextstepaction"]
> [Nächster Schritt](contentguideline.md)
