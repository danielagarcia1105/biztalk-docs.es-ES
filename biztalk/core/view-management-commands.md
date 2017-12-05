---
title: "Ver los comandos de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ced7a9ac58fa0375e3eaefa49832e6c23ba1a73
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="view-management-commands"></a>Comandos de administración de vistas
Los comandos de administración de vistas de la utilidad de administración de BAM permiten trabajar con vistas implementadas.  
  
-   Get-views: enumera todas las vistas implementadas.  
  
-   Remove-view: quita una vista implementada.  
  
-   Get-rtawindow: Obtiene la duración de una vista.  
  
-   Set-rtawindow: establece la duración de una vista.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-views-command"></a>get-views (comando)  
 **Uso**  
  
 **bm.exe get-views [-actividad:\<nombre de la actividad\> ] [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de la actividad\>|Nombre de la actividad desde la que se van a enumerar las vistas.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a obtener la lista de vistas. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a obtener la lista de vistas. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera las vistas implementadas en el equipo en el que se ejecuta el comando.  
  
 **Ejemplos**  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a>remove-view (comando)  
 **Uso**  
  
 **bm.exe remove-view-Name:\<nombre de la vista\> [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre:\<nombre de vista\>|Nombre de la vista que se va a quitar.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a quitar de la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a quitar de la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita la vista especificada de la base de datos de importación principal de BAM. Si la vista tiene alertas dependientes, se quitan al mismo tiempo.  
  
 **Ejemplos**  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a>get-rtawindow (comando)  
 **Uso**  
  
 **bm.exe get-rtawindow-View:\<nombre de la vista\> -actividad:\<nombre de la actividad\> -ATR:\<nombre de ATR\>[-Server:\<server\> ] [-base de datos:\< base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista\>|Nombre de vista.|  
|Actividad:\<nombre de la actividad\>|Nombre de actividad.|  
|RTA:\<nombre de ATR\>|Nombre de agregación en tiempo real.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Muestra la duración de la agregación en tiempo real especificada. El comando recupera la longitud de la duración y las unidades con las que se mide la duración.  
  
 **Ejemplos**  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a>set-rtawindow (comando)  
 **Uso**  
  
 **bm.exe set-rtawindow-View:\<nombre de la vista\> -actividad:\<nombre de la actividad\> -nombre:\<nombre de ATR\> - TimeLength:\<número entero\>- TimeUnit:Day &#124; Hora &#124; Minuto [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista\>|Nombre de vista.|  
|Actividad:\<nombre de la actividad\>|Nombre de actividad.|  
|Nombre:\<nombre de ATR\>|Nombre de agregación en tiempo real.|  
|TimeLength:\<número entero\>|Duración de la agregación en tiempo real.|  
|TimeUnit:Month &#124; día &#124; Hora &#124; Minuto|Unidad de medida de la duración de la ventana.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Establece la duración para la agregación en tiempo real especificada.  
  
 **Ejemplos**  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)