---
title: "Lección 6: Crear una personalizada canalización de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>Lección 6: Crear una canalización de envío personalizada
En esta lección, creará una canalización de envío personalizada utilizando el Diseñador de canalizaciones de BizTalk. Una canalización de envío es una canalización que se ejecuta en los mensajes antes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] envía los mensajes a su destino.  
  
 Configurar la canalización personalizada para usar el componente de ensamblador SWIFT (ASM). ASM toma un mensaje con formato XML y convierte o serializa el contenido en un archivo plano SWIFT. Esta conversión se basa en el esquema de MT103 que ha creado en [lección 3: agregar una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).  
  
### <a name="to-create-a-custom-send-pipeline"></a>Para crear una canalización de envío personalizada  
  
1.  En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento-SWIFTPipelines, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel de plantillas.  
  
3.  En el **nombre** , escriba **MT103SendPipeline.btp**.  
  
4.  Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.  
  
    > [!NOTE]
    >  Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.  
  
 Continúe con [la lección 7: agregar el ensamblador SWIFT a una personalizada canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).