---
title: 'Lección 3: Agregar esquemas de SWIFT a un proyecto | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fcaa7f9af0dd802f457f84d7661f92bcdf08157
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982045"
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a>Lección 3: Agregar esquemas de SWIFT a un proyecto
Ahora que tiene una solución y un nuevo proyecto, puede agregar elementos al proyecto. El primer elemento que se agrega es un esquema para un mensaje MT103 SWIFT pago. Cuando se selecciona la plantilla de esquema, se inicia el Editor de BizTalk.  
  
### <a name="to-add-a-new-schema-to-the-project"></a>Para agregar un nuevo esquema al proyecto  
  
1. En el Explorador de soluciones, haga clic en el **SWIFTSchemas** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
2. En el cuadro de diálogo Agregar elemento existente-SWIFTSchemas, vaya a  **\< *unidad*\>: Acelerador de BizTalk para SWIFT \Program Files\Microsoft \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base esquemas**.  
  
3. Seleccione el **SWIFT Base Types.xsd** y **Types.xsd datos comunes de SWIFT** esquemas y, a continuación, haga clic en **agregar**.  
  
   > [!NOTE]
   >  El Types.xsd Base SWIFT y los esquemas de SWIFT Types.xsd de datos comunes aparecen en el Explorador de soluciones bajo el proyecto SWIFTSchemas.  
  
4. En el Explorador de soluciones, haga clic en el **SWIFTSchemas** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
5. En el cuadro de diálogo Agregar elemento existente-SWIFTSchemas, vaya a la  **\< *unidad*\>: Acelerador de BizTalk para SWIFT \Program Files\Microsoft \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MT103** carpeta.  
  
6. Seleccione el **MT103.xsd** esquema y, a continuación, haga clic en **agregar**.  
  
   > [!NOTE]
   >  El nuevo esquema, MT103.xsd, aparece en el Explorador de soluciones bajo el proyecto SWIFTSchemas.  
  
7. En el Explorador de soluciones, haga doble clic en **MT103.xsd** para ver el esquema en el Editor de BizTalk.  
  
   > [!NOTE]
   >  El árbol de esquema (panel izquierdo) y la vista XSD (panel derecho) aparecen en el Editor de BizTalk.  
  
8. En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.  
  
   Continúe con [lección 4: crear e implementar el ensamblado](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md).