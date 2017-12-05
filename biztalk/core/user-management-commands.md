---
title: "Comandos de administración de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16527acda7432b2eea35f0c87bb9d89fff632430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="user-management-commands"></a>Comandos de administración de usuario
Los comandos de administración de usuario de alertas de la utilidad de administración de BAM le permiten obtener, agregar y quitar usuarios.  
  
-   Get-accounts: Obtiene una lista de todos los usuarios y grupos a los que pueden tener acceso a una vista especificada.  
  
-   Agregar cuenta: concede derechos de acceso para el usuario o grupo especificado a la vista especificada.  
  
-   Remove-account: quita derechos de acceso para un usuario o grupo de una vista determinada.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-accounts-command"></a>Comando get-accounts  
 **Uso**  
  
 **bm.exe get-accounts-View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista\>|Nombre de la vista para la que se enumeran las cuentas.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a recuperar las cuentas. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a recuperar las cuentas. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera todos los usuarios y grupos que pueden tener acceso a la vista especificada.  
  
 **Ejemplos**  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a>Comando add-account  
 **Uso**  
  
 **bm.exe agregar-account - AccountName:\<nombre de la cuenta\> -View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|AccountName:<nombre de cuenta|Nombre de la cuenta a la que se conceden derechos.|  
|Vista:\<nombre de vista\>|Nombre de la vista a la que se conceden derechos.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Otorga los derechos de acceso a la vista especificada al usuario o grupo de usuarios especificado.  
  
> [!IMPORTANT]
>  Si usas agregaciones en tiempo Real (ATR), los usuarios agregados con **Agregar cuenta** comando no se conceden automáticamente derechos de inicio de sesión de SQL Server. Si está utilizando ATR, considere la posibilidad de establecer un grupo de usuarios de Windows que contenga todos los usuarios que necesitan tener acceso a las vistas de las ATR. Conceda a ese grupo derechos explícitos de inicio de sesión en el servidor SQL Server en el que residan las bases de datos de importación principal de BAM.  
  
 **Ejemplos**  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a>Comando remove-account  
 **Uso**  
  
 **bm.exe remove-account - AccountName:\<nombre de la cuenta\> -View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|AccountName:\<nombre de cuenta\>|Nombre de la cuenta desde la que se van a quitar derechos de la vista.|  
|Vista:\<nombre de vista\>|Nombre de la vista a la que se quitan derechos.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita los derechos de acceso de un usuario o un grupo desde una vista especificada Al quitar una cuenta de una vista, se quita esa cuenta y todos sus miembros de las alertas definidas para la vista especificada. Si esa cuenta es el único propietario de un alerta, el usuario actual (admin) se convierte en el nuevo propietario de la alerta.  
  
 **Ejemplos**  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)