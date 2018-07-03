---
title: Creación la recepción de FRR canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf4e735019c5399e1b7f1648f3adbcffe18fed2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970805"
---
# <a name="creating-the-frr-receive-pipeline"></a>Crear el FRR la canalización de recepción
Para llevar a cabo la conciliación de respuestas de FIN, debe crear una canalización de recepción que contiene el descodificador de FRR SWIFT y componentes de canalización de resolución de CorrelationSet FRR SWIFT, además del desensamblador de SWIFT.  

 **Resumen**  

 Crear una canalización de recepción con las propiedades y las fases siguientes:  

|Fase o propiedad|Componente/configuración|  
|---------------------|------------------------|  
|Fase de desensamblado|Desensamblador de SWIFT|  
|Propiedad de validación del BRE (Desensamblador de SWIFT)|True|  
|Propiedad de validación de XML (Desensamblador de SWIFT)|True|  
|Propiedad de esquema de encabezado de SWIFT (Desensamblador de SWIFT)|(Ninguno)|  
|Fase de descodificador|Descodificador de MQSeries FRR SWIFT|  
|Fase de resolución de entidades|Resolución de conjunto de correlaciones de FRR SWIFT|  

### <a name="to-create-a-custom-receive-pipeline-for-frr"></a>Para crear una canalización de recepción personalizada de FRR  

1. En el Explorador de soluciones de Visual Studio, haga clic en el proyecto que contiene su [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalizaciones, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  

2. En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** en el panel Plantillas.  

3. En el **nombre** , escriba un nombre para la canalización de recepción, tales como **FRRReceivePipeline.btp**. Haga clic en **Agregar**.  

   > [!NOTE]
   >  Antes de realizar el paso 4, debe haber agregado el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR canalización componentes al cuadro de herramientas, como se describe en [agregar componentes de canalización de SWIFT al cuadro de herramientas](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).  

4. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, haga clic en **cuadro de herramientas**.  

5. En el panel cuadro de herramientas de componentes de canalización de BizTalk, arrastre el **Desensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **desensamblar** almacenar provisionalmente la forma en el Diseñador de canalizaciones.  

6. Con el **componente de desensamblador de SWIFT** seleccionado en el Diseñador de canalizaciones, en **propiedades**, compruebe que la **BRE validación** y **devalidacióndeXML** propiedades se establecen en **True**y el **esquema de encabezado de SWIFT** propiedad está establecida en **(ninguno)**.  

7. En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR MQSeries descodificador** a la **Coloque aquí** cuadro a continuación el **descodificador** almacenar provisionalmente la forma en el Diseñador de canalizaciones.  

8. En el panel cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT FRR correlación establecer resolución** a la **Coloque aquí** cuadro a continuación el **ResolveParty** almacenar provisionalmente la forma en la canalización Diseñador.  

9. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.
