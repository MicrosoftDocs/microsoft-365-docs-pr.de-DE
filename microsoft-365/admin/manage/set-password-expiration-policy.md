---
title: Festlegen der Kennwortablaufrichtlinie für Ihre Organisation
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Erfahren Sie, wie ein Administrator im Microsoft 365 Admin Center eine Richtlinie zum Ablauf von Passwörtern für Ihr Unternehmen, Ihre Schule oder Ihre gemeinnützige Organisation festlegen kann.
ms.openlocfilehash: 64a17053ad8bc018935f99ee375e3a7164dff711
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392467"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Festlegen der Kennwortablaufrichtlinie für Ihre Organisation

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)

Als Administrator können Sie festlegen, dass Benutzerkennwörter nach einer bestimmten Anzahl von Tagen oder nie ablaufen. Standardmäßig sind Passwörter für Ihre Organisation so eingestellt, dass sie nie ablaufen.

Aktuelle Untersuchungen weisen nachdrücklich darauf hin, dass erzwungene Kennwortänderungen mehr Schaden anrichten als sinnvoll sind. Sie treiben Benutzer dazu, schwächere Kennwörter zu wählen, Kennwörter wiederzuverwenden oder alte Kennwörter in einer Weise zu aktualisieren, die von Hackern leicht erraten werden kann. Wir empfehlen, die [mehrstufige Authentifizierung zu aktivieren](../security-and-compliance/set-up-multi-factor-authentication.md). Um mehr über Passwortrichtlinien zu erfahren, lesen Sie die [Empfehlungen für Passwortrichtlinien](../misc/password-policy-recommendations.md).

Sie müssen [globaler Administrator](../add-users/about-admin-roles.md) sein, um diese Schritte ausführen zu können.

Wenn Sie ein Benutzer sind, haben Sie nicht die Berechtigungen, um Ihr Kennwort so festzulegen, dass es nie abläuft. Bitten Sie den technischen Support Ihres Unternehmens bzw. der Schule/Uni, die Schritte in diesem Artikel für Sie durchzuführen.

## <a name="set-password-expiration-policy"></a>Festlegen der Kennwortablaufrichtlinie

Führen Sie die folgenden Schritte aus, wenn Sie festlegen möchten, dass Benutzerkennwörter nach einer bestimmten Zeit ablaufen.

1. Wechseln Sie im Admin Center zu **Einstellungen** \> **Org-Einstellungen**.

2. Wechseln Sie zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Datenschutz</a>.
 Wenn Sie kein globaler Administrator sind, wird die Option "Sicherheit und Datenschutz" nicht angezeigt.
  
3. Wählen Sie **Kennwortablaufrichtlinie** aus.
  
4. Wenn Sie nicht möchten, dass die Benutzer ihre Kennwörter ändern müssen, deaktivieren Sie das Kästchen neben **Festlegen, dass Benutzerkennwörter nach einer Anzahl von Tagen ablaufen**.
  
5. Geben Sie ein, wie oft Kennwörter ablaufen sollen. Wählen Sie eine Anzahl von Tagen zwischen 14 und 730.
  
6. Geben Sie im zweiten Feld ein, wann die Benutzer über den Ablauf ihres Kennworts informiert werden sollen, und wählen Sie dann **Speichern** aus. Wählen Sie eine Anzahl von Tagen zwischen 1 und 30 aus.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Wichtige Informationen über das Feature zum Ablauf von Kennwörtern
  
Personen, die nur die Outlook-App verwenden, werden nicht gezwungen, ihr Microsoft 365-Kennwort zurückzusetzen, bis es im Cache abläuft. Dies kann mehrere Tage nach dem tatsächlichen Ablaufdatum sein. Es gibt keine Problemumgehung für dieses Problem auf Administratorebene.

## <a name="prevent-last-password-from-being-used-again"></a>Verhindern, dass das letzte Kennwort erneut verwendet wird

Wenn Sie Ihre Benutzer daran hindern möchten, alte Kennwörter wiederzuverwenden, können Sie das durch Erzwingen des Kennwortverlaufs im lokalen Active Directory (AD) erledigen. Informationen hierzu finden Sie unter [Erstellen einer benutzerdefinierten Kennwortrichtlinie](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

In Azure AD kann das letzte Kennwort nicht mehr verwendet werden, wenn der Benutzer ein Kennwort ändert. Die Kennwortrichtlinie wird auf alle Benutzerkonten angewendet, die direkt in Azure AD erstellt und verwaltet werden. Die Kennwortrichtlinie kann nicht geändert werden. Informationen hierzu finden Sie unter [Azure AD-Kennwortrichtlinien](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Synchronisieren der Benutzerkennworthashes zwischen einem lokalen Active Directory und Azure Active Directory (Microsoft 365)

Dieser Artikel befasst sich mit dem Festlegen der Ablaufrichtlinie für Nur-Cloud-Benutzer (Azure AD). Er gilt nicht für Benutzer von Hybrididentitäten, die eine Kennworthashsynchronisierung, eine Passthrough-Authentifizierung oder einen lokalen Partnerverbund wie ADFS verwenden.
  
Informationen, wie Benutzerkennworthashes über lokales AD mit Azure AD synchronisiert werden, finden Sie unter [Implementieren der Kennworthashsynchronisierung bei Azure AD Connect-Synchronisierung](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory

Sie können weitere Kennwortrichtlinien und Einschränkungen in Azure Active Directory festlegen. Weitere Informationen finden Sie unter [Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).

## <a name="update-password-policy"></a>Aktualisieren der Kennwortrichtlinie

Das Cmdlet "Set-MsolPasswordPolicy" aktualisiert die Kennwortrichtlinie einer angegebenen Domäne oder eines Mandanten. Zwei Einstellungen sind erforderlich; die erste ist die Angabe der Zeitspanne, die ein Kennwort gültig bleibt, bevor es geändert werden muss, und die zweite ist die Angabe der Anzahl von Tagen vor dem Ablaufdatum des Kennworts, das ausgelöst wird, wenn Benutzer ihre erste Benachrichtigung erhalten, dass ihr Kennwort bald abläuft.

Wie Sie die Kennwortrichtlinie für eine bestimmte Domäne oder einen bestimmten Mandanten aktualisieren, erfahren Sie unter [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).

## <a name="related-content"></a>Verwandte Inhalte

[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)\

[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)
