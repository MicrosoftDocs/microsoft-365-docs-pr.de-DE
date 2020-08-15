---
title: Hoch Verfügbarkeits Verbund Authentifizierungs Phase 2 Konfigurieren von Domänencontrollern
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Zusammenfassung: Konfigurieren Sie die Domänencontroller und den Verzeichnissynchronisierungsserver für die Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690673"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Hochverfügbarkeit der Verbundauthentifizierung, Phase 2: Konfigurieren von Domänencontrollern

In dieser Phase der Bereitstellung von hoher Verfügbarkeit für die Verbundauthentifizierung von Microsoft 365 in Azure-Infrastrukturdiensten konfigurieren Sie zwei Domänencontroller und den Verzeichnissynchronisierungsserver im virtuellen Azure-Netzwerk. Clientwebanforderungen für die Authentifizierung können dann im virtuellen Azure-Netzwerk authentifiziert werden, anstatt diesen Authentifizierungsverkehr über das VPN zwischen Standorten an Ihr lokales Netzwerk zu senden.
  
> [!NOTE]
> Active Directory Verbunddienste (AD FS) kann Azure Active Directory (Azure AD) nicht als Ersatz für Active Directory-Domänendienste (AD DS) Domänencontroller verwenden. 
  
Sie müssen diese Phase abschließen, bevor Sie mit [Phase 3: Konfigurieren von AD FS-Servern](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)fortfahren. Unter [Bereitstellen der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) für alle Phasen.
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Erstellen der Domänencontroller der virtuellen Computer in Azure

Zunächst müssen Sie die Spalte **Name des virtuellen Computers** in Tabelle M ausfüllen und in der Spalte **Mindestgröße** die Größe der einzelnen virtuellen Computer nach Bedarf anpassen.
  
|**Element**|**Name des virtuellen Computers**|**Katalogbild**|**Speichertyp**|**Mindestgröße**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![Zeile](../media/Common-Images/TableLine.png)  (erster Domänencontroller, Beispiel DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![Zeile](../media/Common-Images/TableLine.png)  (zweiter Domänencontroller, Beispiel DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![Zeile](../media/Common-Images/TableLine.png) (Verzeichnissynchronisierungsserver, Beispiel ds1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![Zeile](../media/Common-Images/TableLine.png) (erster AD FS-Server, Beispiel ADFS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![Zeile](../media/Common-Images/TableLine.png) (zweiter AD FS-Server, Beispiel ADFS2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![Zeile](../media/Common-Images/TableLine.png) (erster Webanwendungs-Proxy Server, Beispiel WEB1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![Zeile](../media/Common-Images/TableLine.png) (zweiter Webanwendungs-Proxy Server, Beispiel web2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabelle M – virtuelle Computer für die Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure**
  
Eine vollständige Liste der Größen der virtuellen Computer finden Sie unter [Größen für virtuelle Computer](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).
  
Verwenden Sie den folgenden Azure PowerShell-Befehlsblock, um die virtuellen Computer für die beiden Domänencontroller zu erstellen. Geben Sie die Werte für die Variablen an, und entfernen Sie die \< and > Zeichen. Beachten Sie, dass dieser Azure PowerShell-Befehlsblock Werte aus den folgenden Tabellen verwendet:
  
- Tabelle M (für die virtuellen Computer)
    
- Tabelle R (für die Ressourcengruppen)
    
- Tabelle V (für die Einstellungen des virtuellen Netzwerks)
    
- Tabelle S (für das Subnetz)
    
- Tabelle I (für die statischen IP-Adressen)
    
- Tabelle A (für die Verfügbarkeitsgruppen)
    
Erinnern Sie sich, dass Sie die Tabellen R, V, S, I und A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)definiert haben.
  
> [!NOTE]
> [!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Weitere Informationen finden Sie unter [Erste Schritte mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Sobald Sie alle Werte korrekt festgelegt haben, führen Sie den resultierenden Block über die Azure PowerShell-Eingabeaufforderung oder in PowerShell ISE (Integrated Script Environment) auf Ihrem lokalen Computer aus.
  
> [!TIP]
> Verwenden Sie diese [Microsoft Excel Konfigurations Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx), um Ready-to-Run PowerShell-Befehlsblöcke basierend auf Ihren benutzerdefinierten Einstellungen zu generieren. 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Da diese virtuellen Computer für eine Intranetanwendung gedacht sind, wird ihnen weder eine öffentliche IP-Adresse noch eine DNS-Domänennamenbezeichnung zugewiesen. Sie sind also nicht über das Internet erreichbar. Das bedeutet allerdings, dass Sie auch nicht über das Azure-Portal auf sie zugreifen können. Wenn Sie die Eigenschaften eines der virtuellen Computer aufrufen, ist die Option zum **Verbinden**nicht verfügbar. Verwenden Sie eine Remotedesktopverbindung oder ein anderes Remotedesktoptool, um eine Verbindung über die private IP-Adresse des betreffenden virtuellen Computers oder seinen Intranet-DNS-Namen herzustellen.
  
## <a name="configure-the-first-domain-controller"></a>Konfigurieren des ersten Domänencontrollers

Erstellen Sie mithilfe eines Remotedesktopclients Ihrer Wahl eine Remotedesktopverbindung zum virtuellen Computer mit dem ersten Domänencontroller. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.
  
Als Nächstes fügen Sie den zusätzlichen Datenträger dem ersten Domänencontroller mit diesem Befehl an einer Windows PowerShell Eingabeaufforderung **auf dem ersten virtuellen Domänencontroller-Computer**hinzu:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Im nächsten Schritt testen Sie die Verbindung des ersten Domänencontrollers mit Standorten im Netzwerk Ihrer Organisation mithilfe des Befehls **ping** aus, um einen Ping an die Namen und IP-Adressen von Ressourcen innerhalb des Netzwerks Ihrer Organisation zu senden.
  
Gleichzeitig stellen Sie damit sicher, dass die DNS-Namensauflösung korrekt funktioniert (d. h., dass der virtuelle Computer korrekt mit denlokalen DNS-Servern konfiguriert ist) und dass Pakete sowohl an das standortübergreifende Netzwerk als auch aus ihm gesendet werden können. Wenn bei diesem grundlegenden Test ein Fehler auftritt, wenden Sie sich an Ihre IT-Abteilung, um die Probleme mit der DNS-Namensauflösung und der Paketzustellung zu lösen.
  
Führen Sie im nächsten Schritt an der Windows PowerShell-Eingabeaufforderung auf dem ersten Domänencontroller die folgenden Befehle aus:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

Sie werden aufgefordert, die Anmeldeinformationen für ein Domänenadministratorkonto einzugeben. Der Computer wird neu gestartet.
  
## <a name="configure-the-second-domain-controller"></a>Konfigurieren des zweiten Domänencontrollers

Erstellen Sie mithilfe eines Remotedesktopclients Ihrer Wahl eine Remotedesktopverbindung zum virtuellen Computer mit dem zweiten Domänencontroller. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.
  
Als nächstes müssen Sie den zusätzlichen Datenträger dem zweiten Domänencontroller mit diesem Befehl an einer Windows PowerShell Eingabeaufforderung **auf dem zweiten Domänencontroller-virtuellen Computer**hinzufügen:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Führen Sie als nächsten Schritt die folgenden Befehle aus:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

Sie werden aufgefordert, die Anmeldeinformationen für ein Domänenadministratorkonto einzugeben. Der Computer wird neu gestartet.
  
Als Nächstes müssen Sie die DNS-Server für Ihr virtuelles Netzwerk so aktualisieren, dass Azure den virtuellen Computern die IP-Adressen der beiden neuen Domänencontroller zur Verwendungals DNS-Server zuweist. Geben Sie die Variablen ein, und führen Sie diese Befehle an einer Windows PowerShell Eingabeaufforderung auf dem lokalen Computer aus:
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

Beachten Sie, dass die beiden Domänencontroller neu gestartet werden, damit sie nicht mit den lokalen DNS-Server als DNS-Server konfiguriert werden. Da beide selbst DNS-Server sind, wurden sie bei der Höherstufung zu Domänencontrollern automatisch mit den lokalen DNS-Servern als DNS-Weiterleitungen konfiguriert.
  
Als Nächstes müssen wir eine Active Directory-Replikationswebsite erstellen, um sicherzustellen, dass Server im virtuellen Azure-Netzwerk die lokalen Domänencontroller verwenden. Stellen Sie mit einem Domänenadministratorkonto eine Verbindung zu einem der Domänencontroller her, und führen Sie folgende Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>Konfigurieren des Verzeichnissynchronisierungsservers

Verwenden Sie den Remote Desktop Client Ihrer Wahl, und erstellen Sie eine Remotedesktopverbindung zum virtuellen Computer des Verzeichnissynchronisierungsservers. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.
  
Als Nächstes fügen Sie es mit den folgenden Befehlen an der Windows PowerShell-Eingabeaufforderung der entsprechenden AD DS Domäne hinzu.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Wenn Sie diese Phase erfolgreich abgeschlossen haben, sieht Ihre Konfiguration wie folgt aus. Für die Computernamen werden hier Platzhalter verwendet.
  
**Phase 2: der Domänencontroller und der Verzeichnissynchronisierungsserver für die Verbund Authentifizierungsinfrastruktur mit hoher Verfügbarkeit in Azure**

![Phase 2 der Microsoft 365-Verbund Authentifizierungsinfrastruktur mit hoher Verfügbarkeit in Azure mit Domänencontrollern](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Nächster Schritt

Verwenden Sie [Phase 3: Konfigurieren von AD FS-Servern](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) , um die Konfiguration dieser Arbeitsauslastung fortzusetzen.
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Verbundidentität für Ihre Microsoft 365-Entwicklungs-/Testumgebung](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 Lösungs- und Architektur-Center](../solutions/solution-architecture-center.md)


