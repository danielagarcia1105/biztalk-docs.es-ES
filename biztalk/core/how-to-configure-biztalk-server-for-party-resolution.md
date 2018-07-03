---
title: Cómo configurar BizTalk Server para la resolución de entidades | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6fc4f0f0dc61b111060aebb26b8dccfc32ec15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991061"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a>Cómo configurar BizTalk Server para Resolución de entidades
En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para la resolución de entidades.  
  
-   Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados  
  
-   Para crear una entidad que represente el socio comercial  
  
-   Para crear una canalización para la resolución de entidades mediante certificados  
  
-   Para configurar la ubicación de recepción para la resolución de entidades mediante certificados  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados  
  
1. El socio comercial A solicita un par de claves pública y privada para las firmas digitales de la entidad emisora de certificados (CA).  
  
2. El socio comercial A le envía la clave pública para las firmas digitales.  
  
3. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que recibirá mensajes del socio comercial A. Instale el certificado de clave pública del socio comercial A para comprobar la firma en el almacén Otras personas. En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.  
  
    ![Los certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. En el socio comercial A, instale el certificado de clave privada del socio comercial A para firmar los mensajes en el almacén adecuado. (Si está usando el socio comercial A [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], o [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave privada en el almacén personal de la cuenta que firmará los mensajes enviados a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)  
  
   > [!NOTE]
   >  Este paso es exactamente el mismo que el paso "para instalar los certificados en el almacén de certificados para recibir mensajes firmados" en [cómo instalar los certificados para firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).  
  
### <a name="to-create-a-party-to-represent-your-partner"></a>Para crear una entidad que represente el socio comercial  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, cree una entidad para el socio comercial A. Para obtener más información sobre cómo crear una entidad, vea [cómo crear una entidad](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).  
  
2. En el **certificados** propiedades, seleccione la clave pública que firma el certificado que se usará para identificar esta entidad, socio comercial A.  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a>Para crear una canalización para la resolución de entidades mediante certificados  
  
1. En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.  
  
   1.  En el **archivo** menú, haga clic en **Agregar nuevo elemento**.  
  
   2.  En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de recepción** plantilla.  
  
   3.  En el **nombre** , escriba un nombre para la canalización.  
  
   4.  Haga clic en **Agregar**.  
  
        La nueva canalización aparecerá en el Explorador de soluciones.  
  
2. Arrastre el componente de canalización de descodificador de MIME/SMIME en el **Decode** fase de una canalización de recepción.  
  
    ![MIME&#47;componente de canalización de descodificador de SMIME](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME en el **propiedades** ventana. Para obtener más información sobre el descodificador MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
   > [!NOTE]
   >  Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk. Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).  
   > 
   > [!NOTE]
   >  El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones). Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción. Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.  
  
3. Arrastre el componente de canalización de resolución de entidades en el **ResolveParty** fase de una canalización de recepción. Para obtener más información sobre el componente de canalización de resolución de entidades, vea [cómo configurar el componente de canalización de resolución de entidad](../core/how-to-configure-the-party-resolution-pipeline-component.md).  
  
   > [!NOTE]
   >  Asimismo, puede usar la canalización XMLReceive predeterminada en lugar de crear una canalización de recepción nueva. La canalización XMLReceive ejecuta el componente de resolución de entidades, que resuelve el sujeto el Id. de entidad del certificado Tenga en cuenta que la canalización XMLReceive tiene una fase de descodificación vacía y, por lo tanto, no se puede utilizar para recibir mensajes cifrados o comprobar firmas digitales.  
  
   -   En la ventana Propiedades, configure la propiedad de canalización de resolución de entidades **resolver entidad mediante certificado** a `True`.  
  
4. Genere e implemente la canalización de recepción.  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a>Para configurar la ubicación de recepción para la resolución de entidades mediante certificados  
  
1.  Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes firmados. Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
2.  Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior. Para obtener más información sobre cómo configurar las ubicaciones de recepción, vea [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Autenticación de mensajes entrantes](../core/inbound-message-authentication.md)   
 [Uso de certificados para la resolución de entidades](../core/using-certificates-for-party-resolution.md)