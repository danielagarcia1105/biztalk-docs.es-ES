---
title: Cómo configurar el servidor BizTalk Server para recibir mensajes firmados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814aa3f25866f18a1d7fe536bc47a996f286916d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249100"
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a>Cómo configurar BizTalk Server para la recepción de mensajes firmados
En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados.  
  
-   Para crear una canalización para recibir mensajes firmados.  
  
-   Para configurar la ubicación de recepción para recibir mensajes firmados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para recibir mensajes firmados, debe realizar los pasos descritos en [cómo instalar los certificados para las firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a>Para crear una canalización para recibir mensajes firmados.  
  
1.  En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.  
  
    1.  En el **archivo** menú, haga clic en **Agregar nuevo elemento**.  
  
    2.  En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de recepción** plantilla.  
  
    3.  En el **nombre** , escriba un nombre para la canalización.  
  
    4.  Haga clic en **Agregar**.  
  
         La nueva canalización aparecerá en el Explorador de soluciones.  
  
2.  Arrastre el componente de canalización de descodificador de MIME/SMIME en el **Decode** fase de una canalización de recepción.  
  
     ![MIME &#47; Componente de canalización de descodificador de SMIME](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
    -   Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME en el **propiedades** ventana. Para obtener más información sobre el descodificador MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
    > [!NOTE]
    >  Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk. Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).  
  
    > [!NOTE]
    >  El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones). Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción. Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.  
  
3.  Genere e implemente la canalización de recepción.  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a>Para configurar la ubicación de recepción para recibir mensajes firmados.  
  
1.  Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes firmados. Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
2.  Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior. Para obtener más información sobre cómo configurar ubicaciones de recepción, consulte [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Cómo configurar el servidor BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)   
 [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)   
 [Enviar y recibir mensajes firmados](../core/sending-and-receiving-signed-messages.md)