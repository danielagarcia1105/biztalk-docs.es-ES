---
title: "Realización de las pruebas funcionales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f17c2701d6aa90393b8839bafc933bea2fba5746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="performing-functional-testing"></a>Realización de las pruebas funcionales
Usar las pruebas funcionales para probar un escenario de extremo a extremo específico o un caso de uso determinado en el contexto de una determinada aplicación de BizTalk. Una prueba funcional debe cubrir todas las rutas posibles a través de un escenario que nos ocupa, incluidas las rutas de acceso de error. Las rutas de acceso de error se deben evaluar para asegurarse de que la aplicación trata las condiciones de error apropiadamente.  
  
 Se deben invocar todos los artefactos (por ejemplo, orquestaciones, componentes de canalización personalizados y ensamblados personalizados), y todas las ramas de código a través de estos objetos se deben probar también. Todas las combinaciones posibles de mensajes deben tomar precauciones para asegurarse de que los mensajes fluyen a través del sistema correctamente. Los mensajes no válidos se deben probar también para asegurarse de que la aplicación reacciona de la manera esperada en el caso de error y para probar el código incluido en todos los bloques de excepción de las orquestaciones y los componentes personalizados.  
  
## <a name="automating-functional-testing"></a>Automatizar las pruebas funcionales  
 Se deberían automatizar las pruebas funcionales para que sea rápido, por lo que puede repetirse, de modo que evitará errores humanos. **BizUnit** es un marco de prueba declarativa diseñado para permitir a los desarrolladores rápidamente los casos de prueba de diseño. De hecho, un archivo de configuración XML denominado caso de prueba de BizUnit XML es suficiente para definir cómo se debería realizar una prueba. Para ejecutar pruebas, puede crear su propio controlador personalizado o más aprovechan fácilmente **pruebas unitarias de Visual Studio** o **NUnit** para hospedar y ejecutar las pruebas.  
  
 Cada caso de prueba de BizUnit XML contiene tres fases: **TestSetup**, **TestExecution**, y **TestCleanup**. Cada una de estas fases puede contener cero o más pasos de prueba. Cada paso representa una unidad de trabajo y se implementa como una clase de .NET diseñada para realizar una tarea determinada. Este marco de trabajo proporciona un amplio conjunto de componentes. Sin embargo, si necesita llevar a cabo componentes especializados para satisfacer necesidades específicas, puede escribir sus propios componentes del paso de prueba personalizada. Para obtener más información acerca de estas herramientas, consulte [herramientas para pruebas](~/technical-guides/tools-for-testing.md).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)