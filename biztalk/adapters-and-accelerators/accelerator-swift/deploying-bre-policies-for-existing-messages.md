---
title: "Implementación de directivas del BRE para los mensajes existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03f6f3319e90d4782e1e9e5fd7e2a7e2a27b527
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bre-policies-for-existing-messages"></a>Implementación de directivas del BRE para los mensajes existentes
**Para implementar las reglas de negocios relacionadas:**  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación del BRE**.  
  
2.  En la utilidad de implementación del BRE, haga clic en **examinar**.  
  
3.  En el cuadro de diálogo de la caché Global de ensamblados de .NET, seleccione **SWIFT MX esquema**y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic en **implementar**.  
  
     En función de los esquemas implementados con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE. Cuando haya finalizado, la utilidad de implementación del BRE muestra el siguiente mensaje: "la implementación haya finalizado. Ver el archivo de registro o el Compositor de reglas de negocio para obtener más información".  
  
5.  Cierre el cuadro de diálogo Utilidad de implementación de SWIFT BRE.  
  
6.  En el Explorador de Windows, vaya a  *\<unidad >*: \Documents and Settings\All Users\Application datos para confirmar que el archivo de registro BREDeploymentLog.txt aparece en la carpeta.  
  
7.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **services.msc**y, a continuación, haga clic en **Aceptar**. En la ventana Servicios (Local), haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.