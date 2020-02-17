---
title: Benutzerdefinierte Typen vertraulicher Informationen für DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Bekommen Sie einen Überblick über benutzerdefinierte Typen vertraulicher Informationen für DLP.
ms.openlocfilehash: b95501c08c2ac53eed6101abfa9f4b814c49f940
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076980"
---
# <a name="custom-sensitive-information-types"></a>Benutzerdefinierte Typen vertraulicher Informationen

## <a name="overview"></a>Übersicht

Office 365 enthält viele einsatzbereite integrierte Typen vertraulicher Informationen, die Sie in Ihrer Organisation nutzen können, wie zum Beispiel zur [Verhinderung vor Datenverlust](data-loss-prevention-policies.md) (DLP) oder mit [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). Integrierte Typen vertraulicher Informationen helfen beim Erkennen und Schützen von Kreditkartennummern, Bankverbindungsnummern, Reisepassnummern und mehr, basierend auf Mustern, die durch einen regulären Ausdruck (RegEx) oder eine Funktion definiert sind. Weitere Informationen finden Sie unter [Wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).

Was aber ist, wenn Sie eine andere Art Typ vertraulicher Informationen identifizieren und schützen müssen, zum Beispiel für Mitarbeiter-IDs oder Projektnummern, die ein für Ihre Organisation spezifisches Format verwendet? Hierfür können Sie einen benutzerdefinierten Typ vertraulicher Informationen erstellen.

Die grundlegenden Bestandteile eines benutzerdefinierten Typs für vertrauliche Informationen sind wie folgt:

- **Primäres Muster**: Mitarbeiter-ID-Nummer, Projektnummern usw. Dieses wird in der Regel durch einen regulären Ausdruck (RegEx) gekennzeichnet, kann aber auch eine Liste von Schlüsselwörtern sein.

- **Zusätzliche Nachweise**: Angenommen, Sie suchen nach einer neunstelligen Mitarbeiter-ID-Nummer. Nicht alle neunstelligen ID-Nummern sind Mitarbeiter-ID-Nummern, Sie können daher nach zusätzlichem Text suchen: Schlüsselwörter wie „Mitarbeiter“, „Ausweis“, „ID“ oder andere Textmuster basierend auf zusätzlichen regulären Ausdrücken. Diese Nachweise (auch bezeichnet als _unterstützende_ oder _bestätigende_ Nachweise) erhöhen die Wahrscheinlichkeit, dass die neunstellige Nummer, die in Inhalten gefunden wird, auch wirklich eine Mitarbeiter-ID-Nummer ist.

- **Zeichenabstand**: Je näher sich das primäre Muster an den unterstützenden Nachweisen befindet, desto größer ist die Wahrscheinlichkeit, dass die gefundenen Inhalte den von Ihnen gesuchten Inhalten entsprechen. Sie können den Zeichenabstand zwischen dem primären Muster und den unterstützenden Nachweisen angeben (auch als _Näherungsfenster_ bezeichnet), wie in der folgenden Abbildung dargestellt:

    ![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Zuverlässigkeitsgrad**: Je mehr unterstützende Nachweise Sie haben, desto höher die Wahrscheinlichkeit, dass eine Übereinstimmung die vertraulichen Informationen enthält, die Sie suchen. Sie können höhere Zuverlässigkeitsstufen für Übereinstimmungen zuweisen, die gefunden werden, indem Sie mehr Nachweise verwenden.

  Wenn eine Übereinstimmung gefunden wurde, gibt ein Muster eine Anzahl und einen Zuverlässigkeitsgrad zurück, die bzw. den Sie in den Bedingungen Ihrer DLP-Richtlinien verwenden können. Wenn Sie eine Bedingung zum Erkennen eines Typs vertraulicher Informationen zu einer DLP-Richtlinie hinzufügen, können Sie die Anzahl und den Zuverlässigkeitsgrad wie in der folgenden Abbildung dargestellt bearbeiten:

    ![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Benutzerdefinierte Typen vertraulicher Informationen erstellen

Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:

- **Verwenden von EDM** (NEU!) Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen, basierend auf der Klassifizierung der genauen Datenübereinstimmung (EDM). Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen. Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell. Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen. Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers. Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).



