---
title: "Comandos de administración de alertas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b73129d884fea81bdb64609de5e95570275a344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="alert-management-commands"></a>Comandos de administración de alerta
Los comandos de administración de alertas de la utilidad de administración de BAM permiten trabajar con alertas implementadas.  
  
-   Get-alerts: obtener una lista de alertas implementadas.  
  
-   Remove-alerts: quita una alerta.  
  
-   Activar alertas: habilita todas las alertas en una vista.  
  
-   Disable-alerts: deshabilita todas las alertas en una vista.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-alerts-command"></a>Comando get-alerts  
 **Uso**  
  
 **bm.exe get-alerts [-View:\<nombre de vista >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista desde la que se va a obtener la lista de alertas.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera las alertas definidas en el equipo en el que se ejecuta el comando.  
  
 **Ejemplos**  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a>Comando remove-alerts  
 **Uso**  
  
 **bm.exe remove-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista desde la que se van a quitar las alertas.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita todas las alertas en la vista especificada.  
  
 **Ejemplos**  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a>Comando enable-alerts  
 **Uso**  
  
 **bm.exe enable-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista en la que se van a habilitar las alertas.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Habilita todas las alertas en la vista especificada.  
  
 **Ejemplos**  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a>Comando disable-alerts  
 **Uso**  
  
 **bm.exe disable-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista en la que se van a deshabilitar las alertas.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Deshabilita todas las alertas en la vista especificada.  
  
 **Ejemplos**  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)