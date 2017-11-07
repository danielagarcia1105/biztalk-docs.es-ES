---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0bc5b29ff129b145d6b55cbe44ea3aa6a97def76
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="importing-binding-files"></a>Importar archivos de enlace
En este tema se proporciona información relativa al proceso de importación al implementar BizTalk Adapter para JD Edwards EnterpriseOne. Al volver a implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se vuelven a importar.  
  
### <a name="to-clean-the-target-computer"></a>Para limpiar el equipo de destino  
  
-   Quite los puertos de envío y las ubicaciones de recepción vinculados a la orquestación.  
  
     Si Visual Studio no está instalado en el equipo de destino, puede quitar los puertos ejecutando estos scripts:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     Remove Send Port\VBScript\RemoveSendPort.vbs  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
     Por ejemplo, desde un símbolo del sistema, ejecute:  
  
     **cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**  
  
## <a name="see-also"></a>Vea también  
 [Importar JD Edwards EnterpriseOne aplicación](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)