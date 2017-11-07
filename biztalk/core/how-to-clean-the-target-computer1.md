---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 4ceaef21127ec010450082228b765dcbb8e76005
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-clean-the-target-computer"></a>Cómo limpiar el equipo de destino
Implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.  
  
### <a name="to-clean-the-target-computer"></a>Para limpiar el equipo de destino  
  
-   Quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
     Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
         Por ejemplo, en un símbolo del sistema, ejecute:  
  
         **cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**  
  
