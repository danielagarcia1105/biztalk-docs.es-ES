---
title: Comandos de administración de infraestructura | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c82dc5cb65156af86e66abfeffef206f18add5cb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973362"
---
# <a name="infrastructure-management-commands"></a>Comandos de administración de infraestructura
Los comandos de configuración de la utilidad de administración de BAM (BM) permiten obtener y actualizar la configuración de BAM.  
  
-   Get-config: Obtiene el archivo de configuración de BAM.  
  
-   Update-config: actualiza la configuración de BAM.  
  
-   Get-changes: enumera los cambios de la infraestructura de BAM.  
  
-   Get-defxml: Obtiene un archivo que contiene todos los artefactos de la base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-config-command"></a>Comando get-config  
 **Uso**  
  
 **bm.exe get-config - FileName:\<archivo de salida\> [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre de archivo:\<archivo de salida\>|Ruta de acceso y nombre del archivo en el que se va a guardar el archivo de configuración.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a obtener la configuración. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a obtener la configuración. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Recupera el archivo XML de configuración de BAM y lo guarda en el archivo especificado. El **get-config** comando no sobrescribirá el archivo existente.  
  
 **Ejemplos**  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a>Comando update-config  
 **Uso**  
  
 **bm.exe update-config - FileName:\<el archivo de configuración\>**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre de archivo:\<el archivo de configuración\>|Ruta y nombre del archivo de configuración desde el que se va a actualizar la infraestructura de BAM.|  
  
 Actualiza la configuración en el equipo local desde un archivo que contiene el XML de configuración de BAM. Puede agregar nombres de servidor y de base de datos que todavía no existan en la configuración actual. Si cambia los nombres de servidor o de base de datos que ya tengan implementada la infraestructura dinámica se generará un error y bm.exe lo informará.  
  
 Si modifica la ubicación de descarga de archivos para las alertas entregadas por el archivo, deberá reiniciar los servicios de notificación de SQL. Si no se reinician los servicios de notificación, las alertas se seguirán entregando en la ubicación de entrega de archivos original.  
  
 Para cambiar la ubicación de entrega de archivos, modifique la siguiente línea del archivo de configuración de BAM.  
  
 \<Nombre de propiedad = "FileDropUNC"\>\\\\< nombre de equipo\>\alerts \< /Property\>  
  
 Para que conocer los pasos adecuados actualizar las referencias, vea [copia de seguridad y restauración de BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).  
  
> [!IMPORTANT]
>  Si ejecuta un comando update-database mediante un archivo de configuración de BAM que no contiene una sección de alertas y si ya ha configurado alertas BAM, bm.exe sobrescribirá la configuración de tal manera que ya no funcionarán las alertas.  
  
 **Ejemplos**  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a>Comando get-changes  
 **Uso**  
  
 **bm.exe get-changes [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside la base de datos de importación principal de BAM. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: Si no se especifica el nombre, bm.exe utiliza el nombre predeterminado BamPrimaryImport.|  
  
 Obtiene una lista de cambios aplicados a la base de datos de importación principal de BAM. Puede utilizar este comando para auditar cambios a la infraestructura de BAM. El comando devuelve la información siguiente:  
  
 Tipo de comando del cambio y del archivo desde el que se aplicó el cambio.  
  
 ¿Quién aplicó el cambio?  
  
 ¿Qué actividades se cambiaron?  
  
 ¿Qué vistas se cambiaron?  
  
 **Ejemplos**  
  
```  
bm.exe get-changes  
```  
  
 Salida de comando  
  
 \#1: implemente c:\bam\ordermanagement.xml  
  
 Por dominio\usuario en 12/30/2005 8:17:08 PM (v3.5.1536.0).  
  
 Actividades: OrderMgmt  
  
 Vistas: SalesManager  
  
## <a name="get-defxml-command"></a>Comando get-defxml  
 **Uso**  
  
 **bm.exe get-defxml - FileName:\<archivo de salida\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre de archivo:\<archivo de salida\>|Ruta y nombre del archivo en el que se van a guardar las definiciones.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a obtener las definiciones. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a obtener las definiciones. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Recupera todos los artefactos de la base de datos de importación principal de BAM y los guarda en un archivo como XML. El comando no sobrescribirá archivos existentes.  
  
 **Ejemplos**  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)