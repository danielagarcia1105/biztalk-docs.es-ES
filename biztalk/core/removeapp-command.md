---
title: Comando RemoveApp | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 323290ae-8498-4ad6-9b06-a1d54640250e
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05269411c81aeccdaf1c30e36e47c02787bf044a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="removeapp-command"></a>RemoveApp (comando)
Quita (elimina) de la base de datos de administración de BizTalk una aplicación de BizTalk así como todos los artefactos que contiene. No se desinstala la aplicación. Para obtener instrucciones sobre cómo hacer esto, consulte [cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md).  
  
 Se producirá un error en la operación de quitar cuando:  
  
-   **No se detiene la aplicación.** Para obtener instrucciones acerca de cómo detener una aplicación, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md). El **ApplicationManager** ejemplo SDK que se instala en el  *\<ruta de ejemplos\>\\*directorio Admin\ExplorerOM\ ilustra cómo mediante programación iniciar o detener un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación.  
  
-   **Otras aplicaciones contienen referencias a la aplicación.** Si otras aplicaciones contienen referencias a la aplicación que desea quitar, primero debe quitar las referencias de las otras aplicaciones. Para obtener instrucciones, consulte [cómo quitar una referencia a otra aplicación](../core/how-to-remove-a-reference-to-another-application.md).  
  
-   **La aplicación contiene un grupo de puertos de envío de los cuales un puerto de envío de otra aplicación es un miembro.** Debe dar de baja el puerto de envío miembro para poder eliminar la aplicación. Para obtener instrucciones, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md).  
  
-   **La aplicación contiene un puerto de envío que hace referencia a una entidad.** Puede eliminar la referencia de la entidad o mover el puerto de envío a una aplicación diferente. Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca) o [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).  
  
-   **La aplicación es la aplicación predeterminada.** Si desea eliminarla, primero debe hacer que otra aplicación sea la predeterminada. Para obtener instrucciones, consulte [cómo cambiar la aplicación predeterminada](../core/how-to-change-the-default-application.md).  
  
-   **Una orquestación en la aplicación se inscribe, inicia, o tiene una instancia suspendida.** Para obtener más información acerca de las orquestaciones, consulte [administrar orquestaciones](../core/managing-orchestrations.md).  
  
> [!NOTE]
>  Si la aplicación contiene una directiva que se encuentra en un estado implementado, la directiva no se quita de la base de datos de motor de reglas y continuará mostrándose en la carpeta directivas bajo el \<todos los artefactos\> nodo de la aplicación de BizTalk Consola de administración. Si agrega la directiva a otra aplicación, la directiva permanece en un estado implementado.  
  
## <a name="usage"></a>Uso  
 **/ ApplicationName BTSTask RemoveApp:** *valor* [**/Server:***valor*] [**/Database:**  *valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|Sí|Nombre de la aplicación de BizTalk Server que se va a eliminar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask RemoveApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)