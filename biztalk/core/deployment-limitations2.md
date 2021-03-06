---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 314bffd50e152c1e3141e4f644c60bdbe7a3824a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011037"
---
# <a name="deployment-limitations"></a>Limitaciones de implementación
La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace exportado por el Asistente para la implementación de BizTalk, y se pasa a la administración componente en el mismo formato. Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta). A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.  
  

## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Use una de las siguientes soluciones como alternativa para la limitación de contraseña.  
  
#### <a name="to-work-around-the-password-limitation"></a>Para solucionar la limitación de contraseña  
  
1. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
   > [!CAUTION]
   >  Por motivos de seguridad, esta práctica no es recomendable.  
  
2. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.  
  
   > [!NOTE]
   >  Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.  
  
   **O bien**  
  
#### <a name="to-work-around-the-password-limitation"></a>Para solucionar la limitación de contraseña  
  
1.  Use el inicio de sesión único empresarial en lugar de contraseñas.  
  
     El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.  
  
2.  Compruebe el sistema lógico y los servicios de transmisión y recepción.  
  
## <a name="see-also"></a>Vea también  
 [Agregar los artefactos a administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Importar el JD Edwards OneWorld app](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)