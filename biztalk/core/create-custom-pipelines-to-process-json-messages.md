---
title: Crear canalizaciones personalizadas para procesar mensajes JSON | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>Crear canalizaciones personalizadas para procesar mensajes JSON
> [!NOTE]
>  Este tutorial se aplica solo a [!INCLUDE[prague](../includes/prague-md.md)].  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona componentes de canalización que se pueden usar para procesar mensajes JSON en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este paso, usamos esos componentes de canalización para crear canalizaciones personalizadas que se pueden usar cuando se configura una aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="create-a-custom-receive-pipeline"></a>Crear una canalización de recepción personalizada  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizaciónderecepción**. Proporcione el nombre de canalización como `JSONToXmlReceivePipeline.btp`y, a continuación, haga clic en **agregar**.  
  
2.  En el **Decode** fase agrega el nuevo **descodificador JSON**. Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.  
  
     ![Canalización de recepción personalizada](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>Crear una canalización de envío personalizada  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y seleccione **agregar** > **nuevo elemento** > **decanalizacióndeenvío**. Proporcione el nombre de canalización como `XmlToJSONSendPipeline.btp`y, a continuación, haga clic en **agregar**.  
  
2.  En el **Encode** fase agrega el nuevo **codificador JSON**. Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.  
  
     ![Canalización de envío personalizada](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)