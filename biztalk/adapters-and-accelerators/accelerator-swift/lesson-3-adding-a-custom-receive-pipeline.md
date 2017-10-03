---
title: "Lección 3: Agregar una canalización de recepción personalizada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76abee50cce743dde6c62ea078f5ef9dada0c998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a>Lección 3: Agregar una canalización de recepción personalizada
En esta lección, creará una canalización de recepción personalizada usando el Diseñador de canalizaciones de BizTalk. Una canalización de recepción personalizada es una canalización que se ejecuta en los mensajes después de que el adaptador recibe los mensajes, pero antes [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publica en la base de datos de cuadro de mensajes.  
  
 Configurar la canalización personalizada para usar el componente de desensamblador SWIFT (DASM). El Desensamblador SWIFT toma un archivo plano con formato SWIFT y convierte o analiza, el contenido del mensaje SWIFT en una representación basada en XML, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede consumir.  
  
 El esquema de Common Language runtime MT103 que agregó en el paso anterior ([lección 2: agregar referencias de proyecto](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) es el formato que utilice para la conversión.  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a>Para crear una personalizada nueva canalización de recepción  
  
1.  En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento-SWIFTPipelines, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** desde el panel de plantillas.  
  
3.  En el **nombre** , escriba **MT103ReceivePipeline.btp**.  
  
4.  Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.  
  
 Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk. Visual Studio también agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.  
  
 Continúe con [lección 4: agregar el SWIFT ensamblador y desensamblador al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).