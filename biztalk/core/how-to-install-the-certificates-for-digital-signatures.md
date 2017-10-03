---
title: "Cómo instalar los certificados para las firmas digitales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a755e59c7c916f3abe037513ddbc9e2a89892fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a>Cómo instalar los certificados para firmas digitales
En el siguiente procedimiento se enumeran los pasos de nivel superior que debe seguir para instalar los certificados que le permitirán recibir y enviar mensajes firmados.  
  
-   Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados  
  
-   Para instalar los certificados de firma para el envío de mensajes firmados al almacén de certificados  
  
-   Para configurar el grupo de BizTalk para el envío de mensajes firmados  
  
> [!NOTE]
>  Puede usar un mismo certificado para las operaciones de firma y descifrado, o bien usar un certificado para cada función.  
  
> [!IMPORTANT]
>  Únicamente puede especificar un certificado de firma con el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] firma todos los mensajes de salida. En otras palabras, no puede usar diferentes certificados de firma en función de a quién le envíe el mensaje.  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados  
  
1.  El socio comercial A solicita un par de claves pública y privada para las firmas digitales de la entidad emisora de certificados (CA).  
  
2.  El socio comercial A le envía la clave pública para las firmas digitales.  
  
3.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que recibirá mensajes del socio comercial A. Instale el certificado de clave pública del socio comercial A para comprobar la firma en el almacén Otras personas. En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.  
  
     ![Certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4.  En el socio comercial A, instale el certificado de clave privada del socio comercial A para firmar los mensajes en el almacén adecuado. (Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave privada en el almacén personal para la cuenta que firmará los mensajes enviados a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a>Para instalar los certificados de firma para el envío de mensajes firmados al almacén de certificados  
  
1.  Un administrador de su organización solicita un par de claves pública y privada para firmas digitales a la CA para que las use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  El administrador envía al socio comercial A (y al resto de socios comerciales) la clave pública para firmas digitales.  
  
3.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como cuenta de servicio de la instancia de host que está ejecutando el controlador que enviará mensajes al socio comercial A. Instale el certificado de clave privada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para firmar mensajes en el almacén personal de la cuenta de servicio. En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.  
  
     ![Certificados necesarios para enviar mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
4.  En el socio comercial A, instale el certificado de clave pública de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para comprobar la firma digital del almacén adecuado. (Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave pública en el almacén de Otras personas.)  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a>Para configurar el grupo de BizTalk para el envío de mensajes firmados  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Haga clic en **grupo de BizTalk**y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades del grupo de** cuadro de diálogo, haga clic en **certificado**, haga clic en **examinar**.  
  
4.  En el **Seleccionar certificado** cuadro de diálogo, seleccione el certificado de firma que instaló y, a continuación, cierre todos los cuadros de diálogo.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear una canalización para recibir mensajes firmados en [cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).  
  
 Crear una canalización para enviar mensajes firmados [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Enviar y recibir mensajes firmados](../core/sending-and-receiving-signed-messages.md)