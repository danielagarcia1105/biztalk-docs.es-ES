---
title: "Comandos de administración de la actividad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90c5f394ed32b68f4f9b747c580fac02e22a8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-management-commands"></a>Comandos de la administración de la actividad
Los comandos de administración de la actividad de la utilidad de administración de BAM permiten trabajar con actividades implementadas.  
  
-   Get-activities: Obtiene una lista de actividades implementadas.  
  
-   Remove-activity: quita una actividad.  
  
-   Get-activitywindow: Obtiene la duración de una actividad.  
  
-   Set-activitywindow: establece la duración de una actividad.  
  
-   Get-index: Obtiene la lista de índices.  
  
-   Crear índice: crea un nuevo índice.  
  
-   índice de Delete: elimina un índice.  
  
-   Get-archive: Obtiene el comportamiento de la actividad archivada.  
  
-   Set-archive: establece el comportamiento de la actividad archivada.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BAM mediante la inclusión de la **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede usarse junto con cualquier comando normal de BAM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-activities-command"></a>Comando get-activities  
 **Uso**  
  
 **bm.exe get-activities [-View:\<nombre de vista >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre:\<nombre de actividad >|Nombre de la actividad que se va a quitar.|  
|Servidor:\<server >|Opcional: El nombre del servidor desde el que se va a obtener la lista de actividades. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos que se va a obtener la lista de actividades. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera las actividades implementadas en el equipo en el que se ejecuta el comando.  
  
 **Ejemplos**  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a>Comando remove-activity  
 **Uso**  
  
 **bm.exe remove-activity-Name:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre:\<nombre de actividad >|Nombre de la actividad que se va a quitar.|  
|Servidor:\<server >|Opcional: El nombre del servidor desde el que se va a quitar de la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos que se va a quitar de la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita la actividad especificada de la base de datos de importación principal de BAM. Si la actividad tiene vistas dependientes, el comando no funcionará e informará de un error. Utilice el comando remove-view para quitar todas las vistas dependientes y ejecutar de nuevo el comando remove-activity.  
  
 **Ejemplos**  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a>Comando get-activitywindow  
 **Uso**  
  
 **bm.exe get-activitywindow-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de actividad >|El nombre de la .activity.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Muestra la duración de la actividad especificada. El comando recupera la longitud de la duración y las unidades con las que se mide la duración.  
  
 **Ejemplos**  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a>Comando set-activitywindow  
 **Uso**  
  
 **bm.exe set-activitywindow-actividad:\<nombre de actividad > - TimeLength:\<número entero > - TimeUnit: mes &#124; día &#124; Hora &#124; Minuto [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de actividad >|Nombre de la actividad.|  
|TimeLength:\<número entero >|Duración de la actividad.|  
|TimeUnit:Month &#124; día &#124; Hora &#124; Minuto|Unidad de medida de la duración.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Establece la duración de la actividad especificada.  
  
 **Ejemplos**  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a>Comando get-index  
 **Uso**  
  
 **bm.exe get-index-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de actividad >|Nombre de la actividad.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera todos los índices que se han creado para la actividad especificada.  
  
 **Ejemplos**  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a>Comando create-index  
 **Uso**  
  
 **bm.exe crear-index - IndexName:\<nombre de índice >-actividad:\<nombre de actividad >-punto de comprobación:\<punto de Control1 > [,\<punto de control2 >...] [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|IndexName:\<nombre de índice >|Nombre del índice nuevo.|  
|Actividad:\<nombre de actividad >|Nombre de la actividad para la que se crea el índice.|  
|Punto de comprobación:\<punto de Control1 > [,\<punto de control2 >...]|Lista delimitada por comas de puntos de control para el índice.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Crea un índice para la actividad especificada mediante los puntos de control especificados.  
  
 **Ejemplos**  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a>Comando delete-index  
 **Uso**  
  
 **bm.exe delete-index - IndexName:\<nombre de índice >-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|IndexName:\<nombre de índice >|Nombre del índice que se va a eliminar.|  
|Actividad:\<nombre de actividad >|Nombre de la actividad para la que se elimina el índice.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Elimina el índice especificado con el nombre dado de la actividad especificada.  
  
 **Ejemplos**  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a>Comando set-archive  
 **Uso**  
  
 **bm.exe get-archivo-actividad:\<actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de actividad >|Nombre de la actividad para la que se debe mostrar el comportamiento.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Obtiene el comportamiento del paquete de archivo para la actividad especificada, independientemente de si el paquete archiva datos de actividad o los depura.  
  
 **Ejemplos**  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a>Comando set-archive  
 **Uso**  
  
 **bm.exe set-archivo - actividad:\<actividad > - ShouldArchive: True [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Actividad:\<nombre de actividad >|Nombre de la actividad para la que se debe mostrar el comportamiento.|  
|ShouldArchive: True|Si se define como True, la actividad se traslada a la base de datos de archivo. Si se define como False, la actividad se purga.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la actividad. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la actividad. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Define el comportamiento del paquete de archivo para la actividad especificada para que los datos de actividad se trasladen a la base de datos de archivo. De forma predeterminada, se define este comportamiento para las actividades nuevas que se implementan.  
  
 **Ejemplos**  
  
 Para purgar los datos de actividad BAM, ejecute lo siguiente:  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 Para trasladar los datos de actividad BAM a la base de datos de archivo BAM, ejecute lo siguiente:  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)