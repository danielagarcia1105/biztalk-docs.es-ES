---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: b669c06c5c474d5ce134b593dcecd110c6e8d572
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015723"
---
# <a name="deployment-limitations"></a>Limitaciones de implementación
La contraseña del adaptador de transporte se almacena como estrellas (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por BizTalk Server y pasa al componente de administración en el mismo formato. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
 Se trata de una limitación conocida. Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación correctamente.  
  
  
## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
> [!CAUTION]
>  Por motivos de seguridad, esta práctica no es recomendable.  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
> [!NOTE]
>  Esta solución solo se puede usar si Visual Studio está instalado en el equipo de destino, o si desarrolla una herramienta personalizada.  
  
-   Compruebe el sistema lógico y los servicios de transmisión y recepción.  
  
