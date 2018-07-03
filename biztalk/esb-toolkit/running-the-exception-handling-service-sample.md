---
title: Ejecutar el ejemplo de servicio de control de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabab8678d8ee8b65854e494ce0a2ec53eba78fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999397"
---
# <a name="running-the-exception-handling-service-sample"></a>Ejecutar el ejemplo de servicio de control de excepciones
El ejemplo de servicio de control de excepciones muestra cómo consumir el servicio Web de control de excepciones para enviar un error en el marco de control de excepciones de ESB desde una aplicación externa. El procedimiento siguiente para ejecutar este ejemplo requiere [instalar los ejemplos de administración de excepciones](../esb-toolkit/installing-the-exception-management-samples.md).  
  
 **Para ejecutar el ejemplo de servicio de control de excepciones**  
  
1. En el Explorador de Windows, abra la carpeta \Source\Samples\ExceptionHandlingService, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio denominado ExceptionHandlingService.sln.  
  
2. En Visual Studio, haga clic en **Iniciar depuración** en la barra de herramientas.  
  
3. En el formulario que se carga, haga clic en el **generar excepciones** botón.  
  
4. En el Explorador de Windows, abra la carpeta de \Samples\Exception Handling\Test\Filedrop\All_Exceptions y, a continuación, abra el archivo .xml de Exceptions_ {GUID} más reciente.  
  
5. Examine el contenido de la excepción generada.  
  
   Para obtener más información acerca de cómo el ejemplo de servicio de control de excepciones usa el servicio de administración de excepciones, vea [excepción control servicio ejemplo funcionamiento](../esb-toolkit/how-the-exception-handling-service-sample-works.md).