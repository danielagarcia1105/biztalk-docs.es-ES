---
title: Asistente para la utilidad de certificados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b0341a11c45cd08f8476d48ea38cbf96bcc49c1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006181"
---
# <a name="certificate-wizard-utility"></a>Utilidad de Asistente para certificados
Use la utilidad CertWizard para importar un certificado de un archivo .pfx o .cer en un almacén privado o público para usarlo con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El código fuente del Asistente para certificados puede encontrarse en el **C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Utilities\Certificate asistente** carpeta. Con un sistema operativo de 64 bits y la versión de BizTalk Server, estará en el **C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\SDK\Utilities\Certificate asistente** carpeta. Para usar al Asistente para certificados primero tendrá que cree mediante Visual Studio.  
  
 CertWizard importa una clave privada de un archivo .pfx en el almacén personal e importa una clave pública de un archivo .cer en un almacén público. Al importar una clave privada, el certificado puede ser un certificado de descifrado para mensajes entrantes o un certificado de firma para mensajes salientes.  
  
 **Descripción de la sintaxis**  
  
 La siguiente tabla describe las partes de la sintaxis que usa la utilidad CertWizard.  
  
|||  
|-|-|  
|Sintaxis|Description|  
|Privatekey|Usada para importar una clave privada.|  
|Publickey|Usada para importar una clave pública.|  
|Rootkey|Usada para importar una clave raíz (de una autoridad de certificación).|  
|filename.pfx (o .cer)|Ruta completa del archivo .pfx (claves privadas) o .cer (claves públicas).|  
|Filepassword|Contraseña requerida para desbloquear el archivo .pxf.|  
|Useridentity|Identidad de servicio que utilizan uno o varios host de BizTalk. Especifique una cuenta de usuario si no desea especificar el host pero desea importar un certificado en una cuenta de usuario. **Nota:** si no se agrega el conmutador Useridentity, la utilidad importa y establecer el certificado para todos los usuarios. **Nota:** si agrega el conmutador Useridentity, pero no especifica un valor, WMI genera automáticamente la identidad del usuario.|  
|Contraseña|Contraseña del usuario de identidad de servicio.|  
|Thumbprint|La huella de un certificado específico, en caso de que el archivo contenga varios certificados. **Nota:** para un archivo de certificado público, si el archivo contiene más de un certificado y no se especifica la huella digital, la utilidad importa todos los certificados en el archivo. En el caso de un archivo de certificado privado, la utilidad solicita seleccionar el certificado que se va a importar.|  
|Uso|Uso intencionado del certificado privado importado. Puede ser uno de los valores siguientes:<br /><br /> **inicio de sesión** (para un certificado de firma)<br /><br /> **descifrar** (para un certificado de descifrado)<br /><br /> **ambos** (para un certificado que es un certificado de firma y un certificado de descifrado)<br /><br /> **Ninguno** (también para un certificado es un certificado de firma y un certificado de descifrado). **Nota:** si el conmutador /Usage como se establece en none, el asistente no establecerá la huella digital del certificado en los Hosts de BizTalk o el grupo de BizTalk.|  
|Exportable|Puede ser **True** o **False**. Si **True**, puede volver a exportar la clave privada.|  
  
 **Sintaxis para importar una clave privada**  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 **Sintaxis para importar una clave pública**  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 **Sintaxis para importar una clave raíz**  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-run-the-certificate-wizard"></a>Para ejecutar el Asistente para certificados  
  
1.  Abra un símbolo del sistema.  
  
2.  Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.  
  
3.  En el símbolo del sistema, escriba **CertWizard**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Si no proporciona el comando completo en el símbolo del sistema, CertWizard le solicitará que proporcione los valores requeridos.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades del SDK](../core/utilities-in-the-sdk.md)