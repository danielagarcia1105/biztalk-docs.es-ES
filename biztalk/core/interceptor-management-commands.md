---
title: Comandos de administración de interceptor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2be6460-1f81-4bc3-a831-34ff24d65d34
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aefeefc7010c4cefca323782dac5a1349479a07d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023170"
---
# <a name="interceptor-management-commands"></a>Comandos de administración de interceptor
Para el funcionamiento de la nueva funcionalidad del interceptor de BAM, se han agregado cuatro nuevos comandos a la utilidad de administración de BAM.  
  
 Estos comandos permiten la implementación, recuperación y eliminación de interceptores. También se incluye un comando para enumerar los interceptores configurados.  
  
-   interceptor de implementar: implementa una configuración de interceptor.  
  
-   Get-interceptorlist: Obtiene una lista de actividades en el que se implementa la interceptación.  
  
-   Get-interceptor: Obtiene la configuración del interceptor.  
  
-   Remove-interceptor: quita una configuración de interceptor.  
  
> [!NOTE]
>  Habilitar seguimiento de cualquier comando de la utilidad BM, incluya el **-Trace: en&#124;desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="deploy-interceptor-command"></a>Comando deploy-interceptor:  
 **Usage**  
  
 **bm.exe implementar-interceptor - FileName:\<el nombre de archivo de configuración XML\> [-Force: True] [-Server:\<server\>] [-base de datos:\<base de datos\>]**  
  
 **Parámetros**  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|Nombre de archivo:\<el nombre de archivo de configuración XML\>|nombre del archivo XML que contiene la configuración del interceptor.|  
|Force:True|Opcional: Fuerza la implementación de la configuración del interceptor cuando se detectan conflictos de nombres de origen de eventos.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que se va a implementar el interceptor. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos de importación principal de BAM en el que se va a configurar el interceptor.|  
  
 Este comando implementa la configuración del interceptor en la base de datos y el servidor especificados. Durante la implementación, la utilidad de administración de BAM lleva a cabo las validaciones siguientes:  
  
- Validación de XSD: la configuración del interceptor se valida con respecto al esquema de configuración del interceptor común.  
  
- Validación de que la actividad existe (está implementada en la base de datos de importación principal) y de que los puntos de control son válidos (existen y tienen un tipo de datos coincidente).  
  
  Si se detecta un conflicto en el nombre del origen del evento, se genera una advertencia que describe ese conflicto. En caso de conflicto, la implementación se producirá un error a menos que el **– Force: True** marcador de parámetro se utiliza.  
  
> [!NOTE]
>  El **– Force: True** parámetro potencialmente elimina configuraciones de interceptores que hacen referencia a orígenes de eventos con el mismo nombre. Debe usar el **get-interceptor** comando para crear una copia de seguridad de las configuraciones de interceptor existentes antes de usar el **– Force: True** parámetro.  
  
 **Ejemplos**  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a>Comando get-interceptorlist  
 **Usage**  
  
 **bm.exe get-interceptorlist [-Server:\<server\>] [-base de datos:\<base de datos\>]**  
  
 **Parámetros**  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a devolver una lista de los interceptores implementados. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar los interceptores implementados.|  
  
 Este comando devuelve una lista de actividades (y de sus orígenes de eventos asociados) para las que se encuentra habilitada la interceptación.  
  
 **Ejemplo**  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a>Comando get-interceptor  
 **Usage**  
  
 **bm.exe get-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] - FileName: \<el nombre de archivo de configuración XML\> [-actividad: \<denombredeactividad\>] [-EventSource: \<nombre origen del evento\>]**  
  
 **Parámetros**  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se va a recuperar el interceptor implementado. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar el interceptor implementado.|  
|Nombre de archivo:\<el nombre de archivo de configuración XML\>|nombre del archivo XML en el que escribir la configuración del interceptor.|  
|Actividad:\<nombre de actividad\>|Opcional: Especifica la actividad que se va a devolver el interceptor configurado. Se puede usar junto con el **EventSource** parámetro para especificar la configuración para devolver.|  
|EventSource:\<el nombre del origen de eventos\>|Opcional: Especifica el origen del evento que se va a devolver el interceptor configurado. Se puede usar junto con el **actividad** parámetro para especificar la configuración para devolver.|  
  
 Si no se proporciona ningún nombre de actividad o de origen de evento, el comando devuelve un archivo de configuración válido que contiene las configuraciones del interceptor para todos los orígenes de eventos y todas las actividades.  
  
 Si sólo se proporciona un nombre de actividad, el comando devuelve un archivo de configuración de interceptor válido para todos los orígenes de eventos de esa actividad.  
  
 Si sólo se proporciona un nombre de origen de evento, el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en todas las actividades.  
  
 Si se proporcionan tanto un nombre actividad como uno de origen de evento, entonces el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en esa actividad.  
  
 **Ejemplos**  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a>Comando remove-interceptor  
 **Usage**  
  
 **bm.exe remove-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] [-actividad: \<nombre de la actividad\>] [-EventSource: \<denombredeorigendeeventos\>]**  
  
 **Parámetros**  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que está configurado el interceptor. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que está configurado el interceptor.|  
|Actividad: \<nombre de actividad\>|Opcional: Especifica la actividad que se va a eliminar el interceptor especificado. Se puede usar junto con el **EventSource** parámetro para especificar la configuración para devolver.|  
|EventSource: \<el nombre del origen de eventos\>|Opcional: Especifica el origen del evento que se va a eliminar el interceptor especificado. Se puede usar junto con el **actividad** parámetro para especificar la configuración para devolver.|  
  
 Si sólo se proporciona un nombre de actividad, el comando elimina el interceptor de todos los orígenes de eventos de esa actividad.  
  
 Si sólo se proporciona un nombre de origen de evento, el comando elimina sólo esa porción del origen del evento para esa actividad.  
  
 **Ejemplo**  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)