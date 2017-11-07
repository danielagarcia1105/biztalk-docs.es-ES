---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: acc8560096423eb69b7cad8d9e6264707ae9a636
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a>Limitaciones de implementación

## <a name="overview"></a>Información general
La contraseña del adaptador de transporte se almacena con asteriscos (******) en el archivo de enlace exportado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y pasa al componente de administración con el mismo formato.  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación.  
  

## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
    > [!CAUTION]
    >  No se recomienda por motivos de seguridad.  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
    > [!NOTE]
    >  Esta solución solo puede utilizarse si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.  
  
 -O bien-  
  
-   Use el inicio de sesión único (SSO) empresarial en lugar de utilizar contraseñas.  
  
     El uso de la opción SSO requiere una importación del archivo de enlace.  
  
 Compruebe el sistema lógico y la transmisión y recepción de servicios.  
  
## <a name="see-also"></a>Vea también  
[Importar enlaces & limitaciones](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)