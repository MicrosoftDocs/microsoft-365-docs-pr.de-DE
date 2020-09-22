---
title: Schutzfunktionen in Azure Information Protection, die für vorhandene Mandanten bereitstellen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel werden die Änderungen erläutert, die für die Schutzfunktionen in Azure Information Protection ausgeführt werden.
ms.openlocfilehash: 070b0d1af0576391ce5f22a827975d1541646454
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203599"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Schutzfunktionen in Azure Information Protection, die für vorhandene Mandanten bereitstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Um mit dem ersten Schritt beim Schutz Ihrer Informationen zu helfen, werden ab Juli 2018 alle Azure Information Protection-berechtigten Mandanten die Schutzfunktionen in Azure Information Protection standardmäßig aktiviert haben. Die Schutzfunktionen in Azure Information Protection waren früher in Office 365 als Rights Management oder Azure RMS bekannt. Wenn Ihre Organisation über einen Office E3-Dienstplan oder einen höheren Service Plan verfügt, erhalten Sie jetzt einen Head-Start Schutz für Informationen durch Azure Information Protection, wenn wir diese Features bereitstellen.

## <a name="changes-beginning-july-1-2018"></a>Änderungen beginnen am 1. Juli 2018

Ab dem 1. Juli 2018 wird Microsoft die Schutzfunktion in Azure Information Protection für alle Organisationen mit einem der folgenden Abonnement Pläne aktivieren:

- Office 365 Nachrichtenverschlüsselung wird im Rahmen von Office 365 E3 und E5, Microsoft E3 und E5, Office 365 a1, a3 und A5 sowie Office 365 G3 und G5 angeboten. Sie benötigen keine zusätzlichen Lizenzen, um die neuen Schutzfunktionen zu erhalten, die von Azure Information Protection betrieben werden.

- Sie können auch Azure Information Protection Plan 1 zu den folgenden Plänen hinzufügen, um die neuen Office 365 Nachrichten Verschlüsselungsfunktionen zu erhalten: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard oder Office 365 Enterprise E1.

- Jeder Benutzer, der von Office 365 Nachrichtenverschlüsselung profitiert, muss lizenziert sein, damit er von der Funktion abgedeckt wird.

- Die vollständige Liste finden Sie in den [Exchange Online Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) für Office 365 Nachrichtenverschlüsselung.

Mandantenadministratoren können den Schutzstatus im Office 365 Administratorportal überprüfen.

![Screenshot, der zeigt, dass die Rechteverwaltung in Office 365 aktiviert wird.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Warum machen wir diese Änderung?

Office 365 Nachrichtenverschlüsselung nutzt die Schutzfunktionen in Azure Information Protection. Im Mittelpunkt der jüngsten Verbesserungen an Office 365 Nachrichtenverschlüsselung und unserer umfassenderen Investitionen in den Informationsschutz in Microsoft 365 ist es für Organisationen einfacher, unsere Schutzfunktionen zu aktivieren und zu nutzen, da Verschlüsselungstechnologien historisch gesehen schwer einzurichten sind. Wenn Sie die Schutzfunktionen in Azure Information Protection standardmäßig aktivieren, können Sie schnell mit dem Schutz Ihrer vertraulichen Daten beginnen.

## <a name="does-this-impact-me"></a>Wirkt sich dies auf mich aus?

Wenn Ihre Organisation eine berechtigte Office 365 Lizenz erworben hat, wird Ihr Mandant von dieser Änderung betroffen sein.

 **Wichtig!** Wenn Sie Active Directory Rights Management Services (AD RMS) in Ihrer lokalen Umgebung verwenden, müssen Sie entweder diese Änderung sofort deaktivieren oder zu Azure Information Protection migrieren, bevor wir diese Änderung innerhalb der nächsten 30 Tage ausführen. Informationen zum Deaktivieren von finden Sie unter "Ich verwende AD RMS, wie kann ich mich abmelden?" weiter unten in diesem Artikel. Wenn Sie lieber migrieren möchten, lesen Sie [Migrieren von AD RMS zu Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kann ich Azure Information Protection mit Active Directory Rights Management Services (AD RMS) verwenden?

Nein. Dies ist kein unterstütztes Bereitstellungsszenario. Ohne die zusätzlichen Opt-out-Schritte verwenden einige Computer möglicherweise automatisch den Azure Rights Management-Dienst und stellen außerdem eine Verbindung mit Ihrem AD RMS-Cluster her. Dieses Szenario wird nicht unterstützt und hat unzuverlässige Ergebnisse, daher ist es wichtig, dass Sie diese Änderung innerhalb der nächsten 30 Tage deaktivieren, bevor wir diese neuen Features bereitstellen. Informationen zum Deaktivieren von finden Sie unter "Ich verwende AD RMS, wie kann ich mich abmelden?" weiter unten in diesem Artikel. Wenn Sie lieber migrieren möchten, lesen Sie [Migrieren von AD RMS zu Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Wie kann ich feststellen, ob ich AD RMS verwende?

Verwenden Sie diese Anweisungen aus [dem Vorbereiten der Umgebung für Azure Rights Management, wenn Sie auch Active Directory Rights Management Services (AD RMS) haben](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) , um zu überprüfen, ob Sie AD RMS bereitgestellt haben:

1. Obwohl optional, veröffentlichen die meisten AD RMS-Bereitstellungen den Dienstverbindungspunkt (Service Connection Points, SCP) für Active Directory, damit Domänencomputer den AD RMS-Cluster ermitteln können.

Verwenden Sie die ADSI-Bearbeitung, um festzustellen, ob ein SCP in Active Directory veröffentlicht wurde: CN = Configuration [Servername], CN = Services, CN = RightsManagementServices, CN = SCP

2. Wenn Sie keinen SCP verwenden, müssen Windows-Computer, die eine Verbindung mit einem AD RMS-Cluster herstellen, für die clientseitige Dienstermittlung oder die Lizenzierungs Umleitung mithilfe der Windows-Registrierung konfiguriert werden: HKEY_LOCAL_MACHINE \software\microsoft\msipc\servicelocation oder HKEY_LOCAL_MACHINE \software\wow6432node\microsoft\msipc\servicelocation

Weitere Informationen zu diesen Registrierungs Konfigurationen finden Sie unter [Aktivieren der clientseitigen Dienstermittlung mithilfe der Windows-Registrierung](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) und [Umleiten des Lizenzierungsserver Datenverkehrs](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ich verwende AD RMS, wie kann ich mich abmelden?

Wenn Sie die bevorstehende Änderung deaktivieren möchten, führen Sie die folgenden Schritte aus:

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie das Cmdlet "IRMConfiguration" mit der folgenden Syntax aus:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Was kann ich erwarten, nachdem diese Änderung vorgenommen wurde?

Sobald diese Option aktiviert ist, können Sie, vorausgesetzt, Sie haben sich nicht entschieden, die neue Version von Office 365 Nachrichtenverschlüsselung verwenden, die bei [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) angekündigt wurde und die Verschlüsselungs-und Schutzfunktionen von Azure Information Protection nutzt.

![Screenshot, der eine OM-geschützte Nachricht in Outlook im Internet zeigt.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Weitere Informationen zu den neuen Verbesserungen finden Sie unter [Office 365 Nachrichtenverschlüsselung](../../compliance/ome.md).
