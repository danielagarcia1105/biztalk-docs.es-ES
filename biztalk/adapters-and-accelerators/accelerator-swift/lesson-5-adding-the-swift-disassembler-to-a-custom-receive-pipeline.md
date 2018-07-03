---
title: 'Lección 5: Agregar el Desensamblador de SWIFT a una canalización de recepción personalizada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af7635b424a74b160991b1d6cfdeb53bfb7f23f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971301"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>Lección 5: Agregar el Desensamblador de SWIFT a una canalización de recepción personalizada
En esta lección, agregará el Desensamblador SWIFT personalizado (DASM) a la canalización. Un componente de canalización DASM es un componente de canalización que divide los mensajes en un lote en documentos individuales.  
  
 Los componentes de canalización DASM proporcionados MicrosoftBizTalk Server son:  
  
- Desensamblador de archivos  
  
- Desensamblador de BizTalk Framework  
  
- Desensamblador de XML  
  
  Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] agrega un desensamblador de SWIFT adicional.  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>Para agregar el Desensamblador de SWIFT personalizado a la canalización  
  
1. En el menú Ver, haga clic en **cuadro de herramientas**.  
  
2. Desde el **cuadro de herramientas de componentes de canalización de BizTalk**, haga clic en **Desensamblador de SWIFT** y arrástrelo hasta el **Coloque aquí** cuadro a continuación el **desensamblar**en forma de organizar **Diseñador de canalizaciones de BizTalk**. Deje el **Desensamblador de SWIFT** forma seleccionada en el **Diseñador de canalizaciones de BizTalk**.  
  
3. En el **propiedades** panel, seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** para el **esquema de encabezado de SWIFT** propiedad.  
  
   > [!NOTE]
   >  No confunda **esquema de encabezado de SWIFT** y esquema de encabezado de mensaje. Debe establecer **esquema de encabezado de SWIFT** en el paso 3.  
  
4. En el **propiedades** panel, asegúrese de que el **BRE validación** propiedad está establecida en **True**.  
  
   > [!NOTE]
   >  Obtener una explicación del motor de reglas de negocios (BRE) sigue más adelante en este tutorial.  
  
5. En el **propiedades** panel, asegúrese de que el **validación XML** propiedad está establecida en **True**.  
  
6. En el **propiedades** panel, asegúrese de que el **entrada desagrupación** propiedad está establecida en **False**.  
  
7. En el **archivo** menú, seleccione **guardar todo** para guardar los cambios.  
  
   Continúe con [lección 6: creación de un archivo de canalización de envío](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).