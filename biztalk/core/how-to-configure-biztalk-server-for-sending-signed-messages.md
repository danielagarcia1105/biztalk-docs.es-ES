---
title: Cómo configurar BizTalk Server para enviar mensajes firmados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53487a4f7f70a7f22a2f9fdae988159723266847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966357"
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a>Cómo configurar BizTalk Server para el envío de mensajes firmados
El procedimiento siguiente indica los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que envíe mensajes firmados.  
  
-   Para crear una canalización para enviar mensajes firmados  
  
-   Para configurar el puerto de envío para enviar mensajes firmados  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para enviar mensajes firmados, debe realizar los pasos descritos en [cómo instalar los certificados para firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a>Para crear una canalización para enviar mensajes firmados  
  
1. En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.  
  
   1.  En el **archivo** menú, haga clic en **Agregar nuevo elemento**.  
  
   2.  En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de envío** plantilla.  
  
   3.  En el **nombre** , escriba un nombre para la canalización.  
  
   4.  Haga clic en **Agregar**.  
  
        La nueva canalización aparecerá en el Explorador de soluciones.  
  
2. Arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de una canalización de recepción.  
  
    ![MIME&#47;componente de canalización de codificador SMIME](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
3. En la ventana Propiedades, configure el componente de canalización de codificador de MIME/SMIME **tipo de firma** propiedad **ClearSign**o **BlobSign**. Para obtener más información sobre la **habilitar el cifrado** propiedad, vea [cómo configurar el componente de canalización de codificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).  
  
   > [!IMPORTANT]
   >  Si también usa cifrado, sólo se puede seleccionar **BlobSign**.  
   > 
   > [!NOTE]
   >  Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk. Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para un puerto de envío](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).  
   > 
   > [!NOTE]
   >  El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones). Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío. Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.  
  
4. Genere e implemente la canalización de envío.  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a>Para configurar el puerto de envío para enviar mensajes firmados  
  
1.  Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para enviar mensajes firmados. Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
2.  Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior. Para obtener más información acerca de cómo configurar puertos de envío, consulte [crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md).  
  
3.  Configurar el grupo de BizTalk con el certificado de firma que instaló en [cómo instalar los certificados para firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md). Para obtener más información acerca de cómo configurar un grupo de BizTalk, consulte [cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Envío y recepción de mensajes firmados](../core/sending-and-receiving-signed-messages.md)