---
title: Cómo configurar BizTalk Server para enviar mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f7388e9f6b8e56397a3b6efdf466aec3383746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023906"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a>Cómo configurar BizTalk Server para el envío de mensajes cifrados
En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados.  
  
-   Para crear una canalización para enviar mensajes cifrados  
  
-   Para configurar el puerto de envío para enviar mensajes cifrados  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para enviar mensajes cifrados, debe realizar los pasos descritos en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md).  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a>Para crear una canalización para enviar mensajes cifrados  
  
1. En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.  
  
   1.  En el **archivo** menú, haga clic en **Agregar nuevo elemento**.  
  
   2.  En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de envío** plantilla.  
  
   3.  En el **nombre** , escriba un nombre para la canalización.  
  
   4.  Haga clic en **Agregar**.  
  
        La nueva canalización aparecerá en el Explorador de soluciones.  
  
2. Arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de una canalización de recepción.  
  
    ![MIME&#47;componente de canalización de codificador SMIME](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
   -   En la ventana Propiedades, configure el componente de canalización de codificador de MIME/SMIME **habilitar el cifrado** propiedad `True`. Para obtener más información sobre la **habilitar el cifrado** propiedad, vea [cómo configurar el componente de canalización de codificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).  
  
   > [!NOTE]
   >  Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk. Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para un puerto de envío](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).  
   > 
   > [!NOTE]
   >  El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones). Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío. Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.  
  
3. Genere e implemente la canalización de envío.  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a>Para configurar el puerto de envío para enviar mensajes cifrados  
  
1.  Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidos los puertos de envío para enviar mensajes cifrados. Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
2.  Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior y, a continuación, asigne el certificado de cifrado que instaló en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md). Para obtener más información acerca de cómo configurar puertos de envío, consulte [cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar BizTalk Server para recibir mensajes cifrados](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)   
 [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [Envío y recepción de mensajes cifrados](../core/sending-and-receiving-encrypted-messages.md)