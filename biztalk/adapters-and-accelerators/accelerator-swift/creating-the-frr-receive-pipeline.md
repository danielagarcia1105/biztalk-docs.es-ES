---
title: "Crear el FRR la canalización de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-pipeline"></a>Crear el FRR la canalización de recepción
Para realizar la conciliación de respuesta de FIN, debe crear una canalización de recepción que contiene el descodificador de SWIFT FRR y componentes de canalización de SWIFT FRR CorrelationSet resolución, así como el Desensamblador SWIFT.  
  
 **Resumen**  
  
 Crear una canalización de recepción con las siguientes fases/propiedades:  
  
|Fase o la propiedad|Componente/configuración|  
|---------------------|------------------------|  
|Fase de desensamblado|Desensamblador SWIFT|  
|Propiedad de validación de BRE (SWIFT desensamblador)|True|  
|Propiedad de validación de XML (SWIFT desensamblador)|True|  
|Propiedad de esquema de encabezado de SWIFT (SWIFT desensamblador)|(Ninguno)|  
|Fase de descodificador|Descodificador de MQSeries FRR SWIFT|  
|Fase de resolución de entidades|Resolución de conjunto de correlaciones de SWIFT FRR|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a>Para crear una canalización de recepción personalizada para FRR  
  
1.  En el Explorador de soluciones de Visual Studio, haga clic en el proyecto que contiene su [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalizaciones, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** en el panel Plantillas.  
  
3.  En el **nombre** , escriba un nombre para la canalización de recepción, como **FRRReceivePipeline.btp**. Haga clic en **Agregar**.  
  
    > [!NOTE]
    >  Antes de realizar el paso 4, debe haber agregado el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR canalización componentes al cuadro de herramientas, como se describe en [agregar componentes de canalización de SWIFT al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).  
  
4.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, haga clic en **cuadro de herramientas**.  
  
5.  En el panel cuadro de herramientas de componentes de canalizaciones de BizTalk, arrastre el **SWIFT Desensamblador** a la **Coloque aquí los** cuadro siguiente la **desensamblar** fase forma en el Diseñador de canalizaciones.  
  
6.  Con el **componente de desensamblador de SWIFT** seleccionada en el Diseñador de canalizaciones, en **propiedades**, compruebe que la **BRE validación** y **devalidacióndeXML** propiedades se establecen en **True**y el **esquema de encabezado de SWIFT** propiedad está establecida en **(ninguno)**.  
  
7.  En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR MQSeries descodificador** a la **Coloque aquí los** cuadro siguiente la **descodificador** fase forma en el Diseñador de canalizaciones.  
  
8.  En el panel cuadro de herramientas de componentes de canalizaciones de BizTalk, arrastre **resolución de conjunto de correlación de SWIFT FRR** a la **Coloque aquí los** cuadro siguiente la **ResolveParty** fase forma de canalización Diseñador.  
  
9. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.