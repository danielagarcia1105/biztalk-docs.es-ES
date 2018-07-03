---
title: 'Lección 1: Implementación de las reglas de negocios relacionada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6228f890e0f508650827f2bb2c3e52b5d29f96f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971109"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>Lección 1: Implementación de las reglas de negocios relacionadas
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye un programa en el Kit de desarrollo de Software de A4SWIFT (SDK) llama a la utilidad de implementación del motor de reglas de negocios (BRE). En esta lección, use esta utilidad para inspeccionar un ensamblado para los esquemas implementados, determinar las reglas necesarias e implementar las directivas para cada esquema y los vocabularios necesarios.  
  
 También puede implementar las reglas mediante el uso de las guías de versión de estándares (SRG) de SWIFT para identificar las reglas necesarias y, a continuación, usar la herramienta Compositor de reglas de negocios para implementar las directivas y vocabularios.  
  
### <a name="to-deploy-the-related-business-rules"></a>Para implementar las reglas de negocios relacionadas  
  
1. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para SWIFT**y, a continuación, haga clic en **Utilidad de implementación de BRE**.  
  
2. En el cuadro de diálogo Utilidad de implementación de BRE, haga clic en **examinar**.  
  
3. En el cuadro de diálogo de la caché Global de ensamblados. NET, seleccione **SWIFTSchemas**y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  SWIFTSchemas hace referencia al ensamblado implementó anteriormente.  
  
4. Haga clic en **implementar**.  
  
    Según los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE. Cuando haya terminado, la utilidad de implementación de BRE muestra el mensaje siguiente:  
  
    **Ha completado la implementación. Para obtener más información, vea el archivo de registro o el Compositor de reglas de negocios.**  
  
5. Cierre el cuadro de diálogo Utilidad de implementación de BRE SWIFT.  
  
6. En el Explorador de Windows, vaya a \< *unidad*\>: \Documents and Settings\All Users\Application Data para confirmar que el archivo de registro **BREDeploymentLog.txt** aparece en el carpeta.  
  
   > [!NOTE]
   >  Puede abrir el archivo de registro con un editor de texto para confirmar cada uno de los pasos de implementación.  
  
7. Reinicie el servicio de actualización de motor de reglas. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escribiendo **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.  
  
   Continúe con [lección 2: confirmación de la implementación mediante la herramienta de Compositor de reglas de negocio regla](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).