---
title: 'Lección 2: Agregar referencias de proyecto | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e7ade122e725c07772dba431bd364bc8f933b82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969701"
---
# <a name="lesson-2-adding-project-references"></a>Lección 2: Agregar referencias de proyecto
Agregar referencias de proyecto para las canalizaciones pueden acceder a los esquemas de tiempo de ejecución predeterminado ubicados en el archivo Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll. Este archivo de ensamblado contiene el esquema de encabezado con propiedades promocionadas necesarias para la resolución de tipo de mensaje.  
  
 Hacer referencia a los esquemas de encabezado más tarde al agregar el componente de desensamblador a la canalización de recepción.  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>Para agregar una referencia al ensamblado de SWIFT RuntimeSchemas predeterminada  
  
1.  En el Explorador de soluciones, asegúrese de que el **SWIFTPipelines** se expande el proyecto. Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha.  
  
3.  Vaya a  **\< *unidad*\>: Acelerador de BizTalk para SWIFT\Assemblies \Program Files\Microsoft**.  
  
4.  Seleccione el **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** archivo.  
  
5.  Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El ensamblado RuntimeSchemas (dll) que ha seleccionado ahora aparece en la colección de referencias en el proyecto SWIFTPipelines.  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>Para agregar una referencia al ensamblado SWIFTPipelines esquemas  
  
1. En el Explorador de soluciones, bajo la **SWIFTPipelines** del proyecto, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2. En el cuadro de diálogo Agregar referencia, en el **proyectos** pestaña, haga clic en el **SWIFTSchemas** del proyecto, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
3. En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.  
  
   Continúe con [lección 3: adición de una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).