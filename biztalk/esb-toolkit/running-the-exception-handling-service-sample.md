---
title: Ejecutar el ejemplo de servicio de control de excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a224c985591801bc9622000c35587b7137f933
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-exception-handling-service-sample"></a>Ejecutar el ejemplo de servicio de control de excepciones
El ejemplo de servicio de control de excepciones muestra cómo consumir el servicio Web de control de excepciones para poder enviar un error en el marco de control de excepciones de ESB desde una aplicación externa. El procedimiento siguiente para ejecutar este ejemplo requiere [instalar los ejemplos de administración de excepción](../esb-toolkit/installing-the-exception-management-samples.md).  
  
 **Para ejecutar el ejemplo de servicio de control de excepciones**  
  
1.  En el Explorador de Windows, abra el \Source\Samples\ExceptionHandlingService carpeta, donde se instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio denominado ExceptionHandlingService.sln.  
  
2.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], haga clic en **Iniciar depuración** en la barra de herramientas.  
  
3.  En el formulario que se carga, haga clic en el **generar excepciones** botón.  
  
4.  En el Explorador de Windows, abra la carpeta \Samples\Exception Handling\Test\Filedrop\All_Exceptions y, a continuación, abra el archivo .xml de Exceptions_ {GUID} más reciente.  
  
5.  Examine el contenido de la excepción generada.  
  
 Para obtener más información acerca de cómo el ejemplo de servicio de control de excepciones utiliza el servicio de administración de excepciones, vea [excepción control de servicio de ejemplo de funcionamiento del](../esb-toolkit/how-the-exception-handling-service-sample-works.md).