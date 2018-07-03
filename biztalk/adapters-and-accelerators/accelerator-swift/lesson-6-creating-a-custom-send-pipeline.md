---
title: 'Lección 6: Crear un personalizado canalización de envío | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12afba9368554dc85cf57658f674a088db7580d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973725"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>Lección 6: Crear una canalización de envío personalizada
En esta lección, creará una canalización de envío personalizada mediante el Diseñador de canalizaciones de BizTalk. Una canalización de envío es una canalización que se ejecuta en los mensajes antes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] envía los mensajes a su destino.  
  
 Configurar la canalización personalizada para usar el componente de ensamblador de SWIFT (ASM). ASM toma un mensaje con formato XML y convierte o serializa el contenido en un archivo plano SWIFT. Esta conversión se basa en el esquema de MT103 que ha creado en [lección 3: adición de una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).  
  
### <a name="to-create-a-custom-send-pipeline"></a>Para crear una canalización de envío personalizada  
  
1. En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2. En el cuadro de diálogo Agregar nuevo elemento-SWIFTPipelines, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel Plantillas.  
  
3. En el **nombre** , escriba **MT103SendPipeline.btp**.  
  
4. Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.  
  
   > [!NOTE]
   >  Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.  
  
   Continúe con [lección 7: agregar el ensamblador de SWIFT a una personalizada canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).