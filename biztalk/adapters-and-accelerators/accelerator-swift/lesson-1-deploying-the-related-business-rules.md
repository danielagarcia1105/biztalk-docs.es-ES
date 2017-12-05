---
title: "Lección 1: Implementar las reglas de negocios relacionados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17c4b470b802a980306481361c1fafcec4f70269
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>Lección 1: Implementar las reglas de negocios relacionadas
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye un programa en el Kit de desarrollo de Software de A4SWIFT (SDK) llamado a la utilidad de implementación del motor de reglas de negocios (BRE). En esta lección, use esta utilidad para examinar un ensamblado para esquemas implementados, determinar las reglas requeridas e implementar los vocabularios necesarios y directivas para cada esquema.  
  
 También puede implementar reglas mediante las guías de versión de estándares de SWIFT (SRG) para identificar las reglas necesarias y, a continuación, usar la herramienta de Compositor de reglas de negocios para implementar las directivas y vocabularios.  
  
### <a name="to-deploy-the-related-business-rules"></a>Para implementar las reglas de negocios relacionadas  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para SWIFT**y, a continuación, haga clic en **Utilidad de implementación de BRE**.  
  
2.  En el cuadro de diálogo Utilidad de implementación del BRE, haga clic en **examinar**.  
  
3.  En el cuadro de diálogo de la caché Global de ensamblados de .NET, seleccione **SWIFTSchemas**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  SWIFTSchemas hace referencia al ensamblado implementó anteriormente.  
  
4.  Haga clic en **implementar**.  
  
     En función de los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE. Cuando haya finalizado, la utilidad de implementación del BRE muestra el mensaje siguiente:  
  
     **Implementación se haya completado. Para obtener más información, vea el archivo de registro o el Compositor de reglas de negocio.**  
  
5.  Cierre el cuadro de diálogo Utilidad de implementación de SWIFT BRE.  
  
6.  En el Explorador de Windows, vaya a \< *unidad*\>: \Documents and Settings\All Users\Application datos para confirmar que el archivo de registro **BREDeploymentLog.txt** aparece en el carpeta.  
  
    > [!NOTE]
    >  Puede abrir el archivo de registro con un editor de texto para confirmar cada uno de los pasos de implementación.  
  
7.  Reinicie el servicio de actualización de motor de reglas. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, iniciando **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.  
  
 Continúe con [lección 2: confirmar la implementación mediante la herramienta de Compositor de reglas de negocios](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).