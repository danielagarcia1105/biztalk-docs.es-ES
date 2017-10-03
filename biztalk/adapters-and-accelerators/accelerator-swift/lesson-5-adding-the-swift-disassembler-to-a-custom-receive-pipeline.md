---
title: "Lección 5: Agregar el Desensamblador SWIFT a una canalización de recepción personalizada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04feeaf88cef2f4ab876b22eda1b1e060a1e0173
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>Lección 5: Agregar el Desensamblador SWIFT a una canalización de recepción personalizada
En esta lección, agregará el Desensamblador SWIFT personalizado (DASM) a la canalización. Un componente de canalización DASM es un componente de canalización que divide los mensajes de un lote en documentos individuales.  
  
 Los componentes de canalización DASM proporcionados en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] son:  
  
-   Desensamblador de archivos sin formato  
  
-   Desensamblador de BizTalk Framework  
  
-   Desensamblador de XML  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] agrega un desensamblador SWIFT adicional.  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>Para agregar el Desensamblador personalizado SWIFT a la canalización  
  
1.  En el menú Ver, haga clic en **cuadro de herramientas**.  
  
2.  Desde el **cuadro de herramientas de componentes de canalizaciones de BizTalk**, haga clic en **SWIFT Desensamblador** y arrástrelo hasta el **Coloque aquí los** cuadro siguiente el **desensamblar**fase forma **Diseñador de canalizaciones de BizTalk**. Deje el **SWIFT Desensamblador** forma seleccionada en la **Diseñador de canalizaciones de BizTalk**.  
  
3.  En el **propiedades** panel, seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** para el **esquema de encabezado de SWIFT** propiedad.  
  
    > [!NOTE]
    >  No confunda **esquema de encabezado de SWIFT** y el esquema de encabezado de mensaje. Debe establecer **esquema de encabezado de SWIFT** en el paso 3.  
  
4.  En el **propiedades** panel, asegúrese de que el **BRE validación** propiedad está establecida en **True**.  
  
    > [!NOTE]
    >  Obtener una explicación del motor de reglas de negocios (BRE) sigue más adelante en este tutorial.  
  
5.  En el **propiedades** panel, asegúrese de que el **validación XML** propiedad está establecida en **True**.  
  
6.  En el **propiedades** panel, asegúrese de que el **entrada anulando** propiedad está establecida en **False**.  
  
7.  En el **archivo** menú, seleccione **guardar todo** para guardar los cambios.  
  
 Continúe con [lección 6: crear una personalizada canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).