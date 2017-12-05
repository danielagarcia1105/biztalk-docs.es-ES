---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 907c21377a6affd5a99576137a5babaa1626c135
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="import-binding-files"></a>Importar archivos de enlace

## <a name="overview"></a>Información general
Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft. Compruebe que la ubicación de estos archivos es el mismo en el nuevo equipo, o editar el archivo de enlace.  
  
-   Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.  
  
-   Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. 
  
> [!NOTE]
>  La implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
 Para obtener instrucciones detalladas sobre la importación de archivos de enlace, consulte el tema "Cómo importar enlaces a un grupo de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino  
Para limpiar el equipo de destino para la implementación de la nueva aplicación, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**  
  
Por ejemplo, en un símbolo del sistema, ejecute:  
  
**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío\>**  
  
