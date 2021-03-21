---
title: Schutzfunktionen in Azure Information Protection, die für vorhandene Mandanten bereitgestellt werden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel werden die Änderungen erläutert, die an den Schutzfunktionen in Azure Information Protection vorgenommen werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32f21c7b57f4f81ea153f7fe1fe84de1f041c592
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921264"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Schutzfunktionen in Azure Information Protection, die für vorhandene Mandanten bereitgestellt werden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Um den ersten Schritt beim Schutz Ihrer Informationen zu unterstützen, sind ab Juli 2018 alle azure Information Protection-berechtigten Mandanten standardmäßig über die Schutzfunktionen in Azure Information Protection aktiviert. Die Schutzfunktionen in Azure Information Protection wurden früher in Office 365 als Rechteverwaltung oder Azure RMS bezeichnet. Wenn Ihre Organisation über einen Office E3-Dienstplan oder einen höheren Dienstplan verfügt, erhalten Sie jetzt einen Vorstart zum Schutz von Informationen durch Azure Information Protection, wenn wir diese Features bereitstellen.

## <a name="changes-beginning-july-1-2018"></a>Änderungen ab dem 1. Juli 2018

Ab dem 1. Juli 2018 aktiviert Microsoft die Schutzfunktion in Azure Information Protection für alle Organisationen mit einem der folgenden Abonnementpläne:

- Die Office 365-Nachrichtenverschlüsselung wird als Teil von Office 365 E3 und E5, Microsoft E3 und E5, Office 365 A1, A3 und A5 sowie Office 365 G3 und G5 angeboten. Sie benötigen keine zusätzlichen Lizenzen, um die neuen Schutzfunktionen zu erhalten, die von Azure Information Protection unterstützt werden.

- Sie können Azure Information Protection Plan 1 auch den folgenden Plänen hinzufügen, um die neuen Office 365-Nachrichtenverschlüsselungsfunktionen zu erhalten: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard oder Office 365 Enterprise E1.

- Jeder Benutzer, der von der Office 365-Nachrichtenverschlüsselung profitiert, muss lizenziert sein, um von dem Feature abgedeckt zu werden.

- Die vollständige Liste finden Sie in den [Exchange Online-Dienstbeschreibungen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) für die Office 365-Nachrichtenverschlüsselung.

Mandantenadministratoren können den Schutzstatus im Office 365-Administratorportal überprüfen.

![Screenshot, der zeigt, dass die Rechteverwaltung in Office 365 aktiviert ist.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Warum wird diese Änderung geändert?

Die Office 365-Nachrichtenverschlüsselung nutzt die Schutzfunktionen in Azure Information Protection. Im Mittelpunkt der jüngsten Verbesserungen bei der Office 365-Nachrichtenverschlüsselung und unserer umfassenderen Investitionen in den Informationsschutz in Microsoft 365 machen wir es Organisationen einfacher, unsere Schutzfunktionen zu aktivieren und zu nutzen, da verschlüsselungstechnologien in der Vergangenheit schwer eingerichtet werden können. Wenn Sie standardmäßig die Schutzfunktionen in Azure Information Protection aktivieren, können Sie schnell damit beginnen, Ihre vertraulichen Daten zu schützen.

## <a name="does-this-impact-me"></a>Wirkt sich dies auf mich aus?

Wenn Ihre Organisation eine berechtigte Office 365-Lizenz erworben hat, wird Ihr Mandant von dieser Änderung betroffen sein.

> [!IMPORTANT]
> Wenn Sie Active Directory-Rechteverwaltungsdienste (AD RMS) in Ihrer lokalen Umgebung verwenden, müssen Sie diese Änderung entweder sofort abmelden oder zu Azure Information Protection migrieren, bevor wir diese Änderung innerhalb der nächsten 30 Tage bereitstellen. Informationen zum Opt-out finden Sie unter "Ich verwende AD RMS, wie kann ich mich abmelden?" weiter später in diesem Artikel. Wenn Sie lieber migrieren möchten, lesen [Sie Migrieren von AD RMS zu Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kann ich Azure Information Protection mit Active Directory-Rechteverwaltungsdienste (AD RMS) verwenden?

Nein. Dies ist kein unterstütztes Bereitstellungsszenario. Ohne die zusätzlichen Abmeldeschritte zu ergreifen, können einige Computer automatisch mit der Verwendung des Azure Rights Management-Diensts beginnen und auch eine Verbindung mit Ihrem AD RMS-Cluster herstellen. Dieses Szenario wird nicht unterstützt und hat unzuverlässige Ergebnisse. Daher ist es wichtig, dass Sie diese Änderung innerhalb der nächsten 30 Tage abmelden, bevor wir diese neuen Features rollouten. Informationen zum Opt-out finden Sie unter "Ich verwende AD RMS, wie kann ich mich abmelden?" weiter später in diesem Artikel. Wenn Sie lieber migrieren möchten, lesen [Sie Migrieren von AD RMS zu Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Wo kann ich wissen, ob ich AD RMS verwendet?

Verwenden Sie die folgenden Anweisungen aus Preparing the environment for Azure Rights Management, wenn Sie auch [über Active Directory-Rechteverwaltungsdienste (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) verfügen, um zu überprüfen, ob Sie AD RMS bereitgestellt haben:

1. Obwohl optional, veröffentlichen die meisten AD RMS-Bereitstellungen den Dienstverbindungspunkt (Service Connection Point, SCP) in Active Directory, damit Domänencomputer den AD RMS-Cluster ermitteln können.

   Verwenden der #A0 zum Anzeigen, ob ein SCP in Active Directory veröffentlicht wurde: CN=Configuration [Servername], CN=Services, CN=RightsManagementServices, CN=SCP

2. Wenn Sie keinen SCP verwenden, müssen Windows-Computer, die eine Verbindung mit einem AD RMS-Cluster herstellen, für die clientseitige Dienstermittlung oder Lizenzierungsumleitung mithilfe der Windows-Registrierung konfiguriert werden: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Weitere Informationen zu diesen Registrierungskonfigurationen finden Sie unter [Enabling client-side service discovery by using the Windows registry](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ich verwende AD RMS, wie kann ich mich abmelden?

Führen Sie die folgenden Schritte aus, um die bevorstehende Änderung abmelden zu können:

1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-IRMConfiguration cmdlet mit der folgenden Syntax aus:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Was kann ich erwarten, nachdem diese Änderung vorgenommen wurde?

Sobald dies aktiviert ist, können Sie die neue Version der Office 365-Nachrichtenverschlüsselung verwenden, die auf [der Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) angekündigt wurde und die Verschlüsselungs- und Schutzfunktionen von Azure Information Protection nutzt.

![Screenshot, der eine OME-geschützte Nachricht in Outlook im Web zeigt.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Weitere Informationen zu den neuen Verbesserungen finden Sie unter [Office 365 Message Encryption](../../compliance/ome.md).