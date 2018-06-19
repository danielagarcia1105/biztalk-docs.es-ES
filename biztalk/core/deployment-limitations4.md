---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 847e66c189cb8fc14014691f95d78b6eec4b45dc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013363"
---
# <a name="deployment-limitations"></a>Limitaciones de implementación
La contraseña del adaptador de transporte se almacena como estrellas (*) en el archivo de enlace exportado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.  
  
 También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.  
  
## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Para solucionar la limitación de contraseña, puede realizar lo siguiente:  
  
#### <a name="to-work-around-the-password-limitation"></a>Para solucionar la limitación de contraseña  
  
1.  Use el inicio de sesión único empresarial en lugar de contraseñas. El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.  
  
2.  Compruebe el sistema lógico y los servicios de transmisión y recepción.  
  
## <a name="see-also"></a>Vea también  
 [Importar JD Edwards EnterpriseOne aplicación](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)