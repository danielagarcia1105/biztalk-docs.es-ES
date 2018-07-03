---
title: Cómo configurar BizTalk Server para recibir mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765c47755e0d170473d92e755eba11e10a4dc3d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023578"
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a>Cómo configurar BizTalk Server para la recepción de mensajes cifrados
En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados.  
  
-   Para crear una canalización para recibir mensajes cifrados  
  
-   Para configurar la ubicación de recepción para recibir mensajes cifrados  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para recibir mensajes cifrados, debe realizar los pasos descritos en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md).  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a>Para crear una canalización para recibir mensajes cifrados  
  
1. En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.  
  
   1.  En el **archivo** menú, haga clic en **Agregar nuevo elemento**.  
  
   2.  En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de recepción** plantilla.  
  
   3.  En el **nombre** , escriba un nombre para la canalización.  
  
   4.  Haga clic en **Agregar**.  
  
        La nueva canalización aparecerá en el Explorador de soluciones.  
  
2. Arrastre el componente de canalización de descodificador de MIME/SMIME a la fase de descodificación de una canalización de recepción.  
  
    ![MIME&#47;componente de canalización de descodificador de SMIME](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME en el **propiedades** ventana. Para obtener más información sobre el descodificador MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
   > [!NOTE]
   >  Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk. Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).  
   > 
   > [!NOTE]
   >  El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones). Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción. Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.  
  
3. Genere e implemente la canalización de recepción.  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a>Para configurar la ubicación de recepción para recibir mensajes cifrados  
  
1.  Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes cifrados. Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
2.  Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior. Para obtener más información sobre cómo configurar las ubicaciones de recepción, vea [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).  
  
3.  Configurar el host usado como controlador de recepción para la ubicación de recepción con el certificado de descifrado que instaló en el procedimiento"para configurar hosts de BizTalk para recibir mensajes cifrados" en [cómo instalar los certificados de cifrado Mensajes](../core/how-to-install-the-certificates-for-encrypted-messages.md). Para obtener más información acerca de cómo configurar propiedades de host, vea [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [Cómo configurar BizTalk Server para enviar mensajes cifrados](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)   
 [Envío y recepción de mensajes cifrados](../core/sending-and-receiving-encrypted-messages.md)