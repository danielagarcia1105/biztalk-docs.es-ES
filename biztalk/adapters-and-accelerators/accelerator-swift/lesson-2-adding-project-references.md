---
title: "Lección 2: Agregar referencias de proyecto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00fc7d49024cec6f9c300444646da82069e16cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-project-references"></a>Lección 2: Agregar referencias de proyecto
Agregue referencias de proyecto para sus canalizaciones pueden acceder a los esquemas de tiempo de ejecución predeterminado ubicados en el archivo Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll. Este archivo de ensamblado contiene el esquema de encabezado con propiedades promocionadas necesarias para la resolución de tipo de mensaje.  
  
 Hacer referencia a los esquemas de encabezado más adelante cuando se agrega el componente de desensamblador a la canalización de recepción.  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>Para agregar una referencia al ensamblado de SWIFT RuntimeSchemas predeterminado  
  
1.  En el Explorador de soluciones, asegúrese de que el **SWIFTPipelines** se expande el proyecto. Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha.  
  
3.  Vaya a  **\<* unidad*\>: \Program Acelerador de BizTalk para SWIFT\Assemblies **.  
  
4.  Seleccione el **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** archivo.  
  
5.  Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  RuntimeSchemas ensamblado (dll) que seleccionó ahora aparece en la colección de referencias en el proyecto SWIFTPipelines.  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>Para agregar una referencia al ensamblado de esquemas SWIFTPipelines  
  
1.  En el Explorador de soluciones, bajo la **SWIFTPipelines** proyecto de equipo y haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, en la **proyectos** , haga clic en el **SWIFTSchemas** proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.  
  
 Continúe con [lección 3: agregar una canalización de recepción personalizada](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).