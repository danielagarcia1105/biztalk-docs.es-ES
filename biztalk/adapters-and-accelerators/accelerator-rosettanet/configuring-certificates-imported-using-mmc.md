---
title: Configuración de certificados importados con MMC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7663d5df833635e557af699dd5ce5fc7de9c7d9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996125"
---
# <a name="configuring-certificates-imported-using-mmc"></a>Configuración de certificados importados con MMC
Después de haber importado los certificados mediante el complemento certificados para Microsoft Management Console (MMC), debe configurar su uso. Esto requiere configurar el grupo de BizTalk, las cuentas de servicio Host de BizTalk y Host aislado, procesos de interfaz de socio (PIP), comerciales acuerdos de socios y asociados. Debe realizar los pasos siguientes:  
  
> [!NOTE]
>  Si usa la utilidad CertWizard para importar y configurar un certificado, no es necesario que realizar estos pasos manuales.  
  
- Configurar el uso de un certificado de firma de la organización propia. Esto significa que usar una clave privada para identificar la organización principal en los mensajes salientes. Para ello, configure el certificado de firma para el grupo de BizTalk.  
  
- Configurar el uso de un certificado de descifrado de la organización propia. Esto significa que usa una clave privada, que corresponde a la clave pública del socio, para descifrar los mensajes entrantes. Para ello, configure el certificado de descifrado para cada Host de BizTalk y las cuentas de servicio de Host aislado de BizTalk. Debe escribir el mismo certificado de descifrado para el host y las cuentas de servicio de host aislado, lo que, para [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] debe establecer en la misma cuenta.  
  
  > [!NOTE]
  >  Los Hosts de BizTalk y el Host aislado deben tener el mismo certificado de descifrado para que ambos pueden descifrar los mismos mensajes cifrados entrantes. El Host aislado de BizTalk que se ejecuta el adaptador de HTTP debe tener el certificado para recibir los mensajes, porque no tiene acceso al certificado de Host. El Host de BizTalk también debe tener el certificado para procesar los mensajes después de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ha recibido.  
  
- Configure el cifrado y certificados de firma para cada socio comercial. Para ello, escriba los certificados el **General** pestaña de la **asociado** página de propiedades de Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. Se trata de un certificado de cifrado de clave pública para cifrar los mensajes salientes a un socio comercial y un certificado de firma de clave pública para comprobar la identidad del asociado en los mensajes entrantes. Para obtener más información, consulte [creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).  
  
- Configurar la directiva de cifrado entre la organización principal y un socio comercial. Para ello, configure el acuerdo entre socios comerciales en el **protocolo** pestaña de la **las propiedades del acuerdo** página en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a>Para configurar el certificado de firma para un grupo de BizTalk o el certificado de descifrado para un Host de BizTalk  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **runas/user:\<hospedar servicio\> mmc**y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Para \< *hospedar servicio*\>, escriba el nombre del servicio que ha asociado con el servicio de host cuando instaló [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
2. Escriba la contraseña de \< *hospedar servicio*\>, y, a continuación, presione ENTRAR.  
  
3. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración**.  
  
4. Expanda **Certificados: usuario actual**, después **Personal**y, a continuación, haga clic en **Certificados**.  
  
5. En el panel derecho, haga doble clic en un certificado privado.  
  
6. En la ventana certificado, en el **detalles** , haga clic **huella digital**y, a continuación, seleccione el número de identificación hexadecimal en la ventana de presentación. Presione CTRL+C para copiarlo.  
  
7. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
8. Para configurar el certificado de firma para un grupo de BizTalk, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)** y, a continuación, haga clic en **propiedades**. Haga clic en el cuadro de texto a la derecha del **huella digital**, presione CTRL+V para pegar el número de huella digital en el cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
9. Para configurar el certificado de descifrado para un Host de BizTalk, expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, expanda **Hosts**, haga clic en el host que desea configurar y, a continuación, haga clic en **propiedades**.  
  
10. En el **certificado** pestaña, haga clic en el cuadro de texto a la derecha del **huella digital**, presione CTRL+V para pegar el número de huella digital en el cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Debe configurar los certificados de descifrado en el Host de BizTalk (BizTalkServerApplication) y el Host de BizTalk aislado (BizTalkServerIsolatedHost).  
  
## <a name="see-also"></a>Vea también  
 [Administración de certificados](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)