---
title: Cómo instalar los certificados para mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24cd9c34fef3c7d984874cc72da13030b167d0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994101"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a>Cómo instalar los certificados para mensajes cifrados
En el siguiente procedimiento se enumeran los pasos de nivel superior que debe seguir para instalar los certificados que le permitirán recibir y enviar mensajes cifrados.  
  
-   Para instalar certificados en el almacén de certificados para descifrado  
  
-   Para instalar certificados en el almacén de certificados para cifrado  
  
-   Para configurar hosts de BizTalk para la recepción de mensajes cifrados  
  
> [!NOTE]
>  Puede usar un mismo certificado para las operaciones de firma y descifrado, o bien usar un certificado para cada función.  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a>Para instalar los certificados de descifrado en el almacén de certificados  
  
1. Un administrador de su organización solicita un par de claves pública y privada para cifrado a la entidad emisora de certificados (CA) para su uso por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2. El administrador envía la clave pública para el cifrado al socio comercial A.  
  
3. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio de la instancia de host que está ejecutando el controlador que recibirá mensajes del socio comercial A. Instale el certificado de clave privada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el descifrado de mensajes en el almacén personal de la cuenta de servicio. En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.  
  
    ![Los certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. En el socio comercial A, instale el certificado de clave pública de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el cifrado de mensajes enviados al socio comercial A en el almacén adecuado. (Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave pública en el almacén de otras personas.)  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a>Para instalar los certificados de cifrado en el almacén de certificados  
  
1. El socio comercial A solicita un par de claves pública y privada para cifrado a la entidad emisora de certificados (CA).  
  
2. El socio comercial A instala el certificado de clave privada para el descifrado de los mensajes en el almacén correspondiente. (Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave privada en el almacén de certificados personales.)  
  
3. El socio comercial A le envía su clave pública para el cifrado de los mensajes enviados a él.  
  
4. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que enviará mensajes al socio comercial A. Instale el certificado de clave pública del socio comercial A para el cifrado de los mensajes enviados a éste en el almacén Otras personas. En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.  
  
    ![Los certificados necesarios para enviar mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a>Para configurar hosts de BizTalk para la recepción de mensajes cifrados  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**, expanda **Hosts**.  
  
   1.  En el panel derecho, haga clic en un host de BizTalk es el controlador para recibir los mensajes cifrados y, a continuación, haga clic en **propiedades**.  
  
   2.  En el **propiedades de Host** cuadro de diálogo, haga clic en **certificado**, haga clic en **examinar**.  
  
   3.  En el **Seleccionar certificado** cuadro de diálogo, seleccione el certificado de descifrado que instaló y, a continuación, cierre todos los cuadros de diálogo.  
  
       > [!NOTE]
       >  Para obtener más información, consulte [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear una canalización para recibir mensajes cifrados, consulte [cómo configurar BizTalk Server para recibir mensajes cifrados](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)  
  
 Crear una canalización para enviar mensajes cifrados [cómo configurar BizTalk Server para enviar mensajes cifrados](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [Envío y recepción de mensajes cifrados](../core/sending-and-receiving-encrypted-messages.md)