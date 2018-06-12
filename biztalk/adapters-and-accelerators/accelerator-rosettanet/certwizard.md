---
title: CertWizard | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa2f9dd1edc9a3541b3b0d9c9a2efe2dbbe6931
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855639"
---
# <a name="certwizard"></a>CertWizard
Use la utilidad CertWizard para importar un certificado desde un archivo .pfx o .cer en un almacén privado o público para su uso con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>archivos \Program (x86)\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\  
  
## <a name="running-certwizard"></a>Ejecutando CertWizard  
  
#### <a name="to-run-certwizard"></a>Para ejecutar CertWizard  
  
1.  Abra un símbolo del sistema.  
  
2.  Mover a \< *unidad*\>\ archivos de programa (x86)\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  
  
3.  En el símbolo del sistema, escriba **CertWizard**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione ENTRAR.  
  
## <a name="syntax-for-certwizard"></a>Sintaxis de CertWizard  
 A continuación se muestra la sintaxis que se utiliza para iniciar esta utilidad de línea de comandos:  
  
### <a name="syntax-for-importing-a-private-key"></a>Sintaxis para importar una clave privada  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a>Sintaxis para importar una clave pública  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a>Sintaxis para importar una clave raíz  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a>Descripción de la sintaxis  
 La siguiente tabla describe las partes de la sintaxis que usa la utilidad CertWizard.  
  
|**Sintaxis**|**Descripción**|  
|----------------|---------------------|  
|**PrivateKey**|Usada para importar una clave privada.|  
|**Clave pública**|Usada para importar una clave pública.|  
|**Clave**|Usada para importar una clave raíz (de una autoridad de certificación).|  
|**FileName.pfx (o .cer)**|Ruta completa del archivo .pfx (claves privadas) o .cer (claves públicas).|  
|**Filepassword**|Contraseña requerida para desbloquear el archivo .pxf.|  
|**Useridentity**|Identidad de servicio que utilizan uno o varios host de BizTalk. Especifique una cuenta de usuario si no desea especificar el host pero desea importar un certificado en una cuenta de usuario. **Nota:** si no se agrega el **Useridentity** cambia, las importaciones de utilidad y establecer el certificado para todos los usuarios. **Nota:** si agrega el **Useridentity** cambiar, pero no especifica un valor, WMI genera automáticamente la identidad del usuario.|  
|**Contraseña**|Contraseña del usuario de identidad de servicio.|  
|**Huella digital**|La huella de un certificado específico, en caso de que el archivo contenga varios certificados. **Nota:** para un archivo de certificado público, si el archivo contiene más de un certificado y no se especifica la huella digital, la utilidad importa todos los certificados en el archivo. En el caso de un archivo de certificado privado, la utilidad solicita seleccionar el certificado que se va a importar.|  
|**Usage**|Uso intencionado del certificado privado importado. Puede ser el inicio de sesión (para un certificado de firma), descifrar (para un certificado de descifrado), ambos (para un certificado que es un certificado de firma y un certificado de descifrado) o none (también para un certificado que es un certificado de firma y un certificado de descifrado ). **Nota:** si establece la **/Usage como** conmutador en ninguno, el asistente no establecerá la huella digital del certificado en los Hosts de BizTalk o el grupo de BizTalk.|  
|**Exportable**|Puede ser `True` o `False`. Si `True`, puede volver a exportar la clave privada.|  
  
## <a name="remarks"></a>Notas  
 CertWizard importa una clave privada de un archivo .pfx en el almacén personal e importa una clave pública de un archivo .cer en un almacén público. Al importar una clave privada, el certificado puede ser un certificado de descifrado para mensajes entrantes o un certificado de firma para mensajes salientes.  
  
 Si no proporciona el comando completo en el símbolo del sistema, CertWizard le solicitará que proporcione los valores requeridos.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
