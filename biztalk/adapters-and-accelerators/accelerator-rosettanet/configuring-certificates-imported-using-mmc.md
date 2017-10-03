---
title: "Configuración de certificados importados con MMC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60811a8b6875c8cbcf4a8037501855a08fe0be6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-certificates-imported-using-mmc"></a>Configuración de certificados importados con MMC
Después de haber importado los certificados con el complemento certificados para el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC), debe configurar su uso. Esto es necesario configurar el grupo de BizTalk, las cuentas de servicio de Host de BizTalk y Host aislado, procesos de interfaz de socio (PIP), comerciales acuerdos de socios y socios. Debe realizar los pasos siguientes:  
  
> [!NOTE]
>  Si usa la utilidad CertWizard para importar y configurar un certificado, no es necesario que realizar estos pasos manuales.  
  
-   Configurar el uso de un certificado de firma de la organización principal. Esto significa que utiliza una clave privada para identificar la organización principal en los mensajes salientes. Para ello, configura el certificado de firma para el grupo de BizTalk.  
  
-   Configurar el uso de un certificado de descifrado de la organización principal. Esto significa que utiliza una clave privada, que se corresponde con la clave pública del socio, para descifrar los mensajes entrantes. Para ello, configure el certificado de descifrado para cada Host de BizTalk y las cuentas de servicio de Host aislado de BizTalk. Debe especificar el mismo certificado de descifrado para el host y las cuentas de servicio de host aislado, que para [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] debe establecer en la misma cuenta.  
  
    > [!NOTE]
    >  Los Hosts de BizTalk y el Host aislado deben tener el mismo certificado de descifrado para que las pueda descifrar los mismos mensajes cifrados entrantes. El Host aislado de BizTalk que se ejecuta el adaptador de HTTP debe tener el certificado que se va a recibir los mensajes, ya no tiene acceso al certificado de Host. El BizTalk Host también debe tener el certificado que se va a procesar los mensajes después de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] los reciba.  
  
-   Configure el cifrado y certificados de firma para cada socio. Para ello, escriba los certificados el **General** pestaña de la **asociado** página de propiedades en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. Esto incluye un certificado de cifrado de clave pública para cifrar los mensajes salientes a un socio comercial y un certificado de firma de clave pública para comprobar la identidad del asociado en los mensajes entrantes. Para obtener más información, consulte [crear o editar un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).  
  
-   Configurar la directiva de cifrado entre la organización principal y un socio comercial. Para ello, configure el acuerdo de socio comercial en la **protocolo** pestaña de la **propiedades del acuerdo de** página en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a>Para configurar el certificado de firma para un grupo de BizTalk o el certificado de descifrado para un Host de BizTalk  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **runas/user:\<servicio de host > mmc**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para \< *hospedar servicio*>, escriba el nombre del servicio que asociado al servicio de host cuando instaló [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
2.  Escriba la contraseña de \< *hospedar servicio*>, y, a continuación, presione ENTRAR.  
  
3.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración**.  
  
4.  Expanda **Certificados: usuario actual**, después **Personal**y, a continuación, haga clic en **Certificados**.  
  
5.  En el panel derecho, haga doble clic en un certificado privado.  
  
6.  En la ventana certificado, en la **detalles** , haga clic en **huella digital**y, a continuación, seleccione el número de identificación hexadecimal en la ventana. Presione CTRL+C para copiarlo.  
  
7.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
8.  Para configurar el certificado de firma para un grupo de BizTalk, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**y, a continuación, haga clic en **propiedades**. Haga clic en el cuadro de texto a la derecha del **huella digital**, presione CTRL+V para pegar el número de huella digital en el cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
9. Para configurar el certificado de descifrado para un Host de BizTalk, expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, expanda **Hosts**, haga clic en el host que desea configurar y, a continuación, haga clic en **propiedades**.  
  
10. En el **certificado** pestaña, haga clic en el cuadro de texto a la derecha del **huella digital**, presione CTRL+V para pegar el número de huella digital en el cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Debe configurar los certificados de descifrado en el Host de BizTalk (BizTalkServerApplication) y el Host aislado de BizTalk (BizTalkServerIsolatedHost).  
  
## <a name="see-also"></a>Vea también  
 [Administración de certificados](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)