---
title: Zusammenarbeit mit Personen außerhalb Ihrer Organisation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Konfigurieren Sie Microsoft 365, um die Freigabe und zusätzliche Sicherheit zu ermöglichen, wenn Sie externe Benutzer zur Zusammenarbeit in Microsoft Teams einladen und SharePoint-Websites freigeben.
ms.openlocfilehash: f8dc81ae32bed7a12daf21955ada60ab852d4617
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255791"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Zusammenarbeit mit Personen außerhalb Ihrer Organisation

Die Funktionen zur externen Freigabe in Microsoft 365 bieten Personen in Ihrer Organisation die Möglichkeit, mit Partnern, Lieferanten, Kunden und anderen Personen zusammenzuarbeiten, die kein Konto in Ihrem Verzeichnis haben. Sie können ganze Teams oder Standorte für Personen außerhalb Ihrer Organisation oder nur für einzelne Dateien freigeben.

Die Zusammenarbeit mit Personen außerhalb Ihrer Organisation besteht aus zwei Hauptkomponenten:

- **Freigabe aktivieren** : Konfigurieren Sie die Freigabe Steuerelemente in Azure Active Directory, Microsoft Teams, Microsoft 365-Gruppen und SharePoint, um die für Ihre Organisation gewünschte Freigabeebene zu ermöglichen.
- **Aktivieren zusätzlicher Sicherheit** : während die grundlegenden Freigabefunktionen so konfiguriert werden können, dass Personen außerhalb Ihrer Organisation authentifiziert werden müssen, bietet Microsoft 365 zahlreiche zusätzliche Sicherheits-und Compliance-Funktionen, die Ihnen dabei helfen, Ihre Daten zu schützen und ihre Steuerungsrichtlinien beizubehalten, während Sie extern freigeben.

## <a name="enable-sharing"></a>Freigabe aktivieren

Standardmäßig ist in Microsoft 365 die Freigabe für Personen außerhalb Ihrer Organisation für SharePoint und OneDrive aktiviert, aber für Teams deaktiviert. Viele SharePoint-und OneDrive-Szenarien für externe Freigaben funktionieren ohne weitere Konfiguration. Wählen Sie eine der folgenden Optionen aus, um die Einstellungen für ein von Ihnen verwendetes Szenario zu bestätigen oder ein neues zu aktivieren:

- [Zusammenarbeit an Dokumenten](collaborate-on-documents.md) -erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass die Freigabe und Zusammenarbeit mit Personen außerhalb Ihrer Organisation (sowohl Gäste als auch nicht authentifizierte Benutzer) in Dateien und Ordnern zugelassen wird.
- [Zusammenarbeiten an einer Website](collaborate-in-site.md) – erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass SharePoint-Websites für Gäste freigegeben werden.
- [Zusammenarbeit als Team](collaborate-as-team.md) -erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass die Zusammenarbeit von Gästen in Teams ermöglicht wird.

Eine umfassende Übersicht über die in Microsoft 365 verfügbaren Gäste Freigabeeinstellungen finden Sie unter [Microsoft 365 Guest Sharing Settings Reference](microsoft-365-guest-settings.md).

## <a name="enable-additional-security"></a>Aktivieren zusätzlicher Sicherheit

Nachdem Sie das Szenario, das Sie für die Freigabe für Personen außerhalb Ihrer Organisation verwenden möchten, aktiviert haben, sollten Sie zusätzliche Schutzvorkehrungen zum Schutz Ihrer Inhalte vor versehentlicher oder vorsätzlicher ungeeigneter Freigaben ergreifen.

- [Bewährte Methoden für die Freigabe von Dateien und Ordnern mit nicht authentifizierten Benutzern](best-practices-anonymous-sharing.md) – erfahren Sie mehr über bewährte Methoden für die Freigabe mit nicht authentifizierten Benutzern.
- [Begrenzen Sie die unbeabsichtigte Belichtung](share-limit-accidental-exposure.md) – erfahren Sie, wie Sie die Wahrscheinlichkeit verringern, dass vertrauliche Inhalte versehentlich mit Personen außerhalb Ihrer Organisation geteilt werden.
- [Erstellen Sie eine sichere Gast Freigabe Umgebung](create-secure-guest-sharing-environment.md) -erfahren Sie mehr über die in Microsoft 365 bereitgestellten Tools, um sicherzustellen, dass die Freigabe für Personen außerhalb Ihrer Organisation auf sichere und sichere Weise erfolgt und ihre Steuerungsanforderungen erfüllt.

## <a name="collaborate-with-partner-companies"></a>Zusammenarbeit mit Partnerunternehmen

Wenn Sie an einem großen Projekt arbeiten, das viele Gäste aus einer anderen Organisation umfasst, oder wenn Sie eine ständige Lieferantenbeziehung haben, in der sich Gäste häufig ändern, können Sie die Verwaltung von Berechtigungen in Azure Active Directory verwenden, um die Verwaltung von Gast zu vereinfachen und das Partnerunternehmen in dieser Verantwortung zu teilen. Weitere Informationen finden Sie unter [Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md) .

## <a name="limit-sharing"></a>Freigabe einschränken

Wenn einige der Freigabefeatures in Microsoft 365 mit ihren Steuerungsrichtlinien in Konflikt stehen, finden Sie unter [Limit Sharing in Microsoft 365](microsoft-365-limit-sharing.md) Informationen zu Optionen zum Einschränken der Freigabe.

## <a name="related-topics"></a>Verwandte Themen

[Einführung in die Zusammenarbeit in Dateien in Microsoft 365](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Planen der Zusammenarbeit von Dateien in SharePoint mit Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
