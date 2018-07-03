---
title: Crear canalizaciones personalizadas para procesar mensajes JSON | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e28f825b1f26f3c080a02fd9a2e2bf8960a816fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005997"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>Crear canalizaciones personalizadas para procesar mensajes JSON
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona componentes de canalización que se pueden usar para procesar mensajes JSON en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este paso, usamos esos componentes de canalización para crear canalizaciones personalizadas que se pueden usar cuando se configura una aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="create-a-custom-receive-pipeline"></a>Crear una canalización de recepción personalizada  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y elija **agregar** > **nuevo elemento** > **decanalizaciónderecepción**. Proporcione el nombre de la canalización como `JSONToXmlReceivePipeline.btp`y, a continuación, haga clic en **agregar**.  
  
2. Dentro de la **Decode** agregar la nueva fase **descodificador JSON**. Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.  
  
    ![Canalización de recepción personalizada](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>Crear una canalización de envío personalizada  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, desde el Explorador de soluciones, haga clic en el proyecto y elija **agregar** > **nuevo elemento** > **decanalizacióndeenvío**. Proporcione el nombre de la canalización como `XmlToJSONSendPipeline.btp`y, a continuación, haga clic en **agregar**.  
  
2. Dentro de la **Encode** agregar la nueva fase **codificador JSON**. Proceda en las demás fases y otros componentes de canalización como se muestra en la captura de pantalla y guarde los cambios.  
  
    ![Canalización de envío personalizada](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)