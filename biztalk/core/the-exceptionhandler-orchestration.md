---
title: "La orquestación de ExceptionHandler | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, systems
- errors, applications
- applications, errors
- orchestrations, errors [process management solutions]
- process management solution tutorial, errors
ms.assetid: ac154e76-9dfe-433a-948b-e098df705fe5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b79a1c6d9e6fada206ba0298913fe8f369783c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-exceptionhandler-orchestration"></a>ExceptionHandler (orquestación)
La solución de administración de procesos empresariales utiliza dos tipos de excepciones: excepciones del sistema y las excepciones de aplicación. Excepciones del sistema incluyen problemas como los errores de recursos: un error, por ejemplo una conexión de red. Es probable que dichos problemas se puedan resolver por sí mismos tras un período y que la solución vuelva a intentar repetir todas las operaciones que provocan excepciones del sistema. Las excepciones de aplicación surgen por problemas con menos probabilidades de resolverse por sí mismos, como los errores lógicos o algunos tipos de incoherencia. La solución utiliza la **ExceptionHandlerOrch** orquestación para procesar los errores de aplicación y del sistema.  
  
 Las fases de procesamiento de pedidos (**CableOrder1**, **CableOrder2**) y sus orquestaciones satélite (**activar**, **analizar**,  **Cancelar**, **cambio**, **completar**, **validar**) todo, use **ExceptionHandlerOrch**.  
  
> [!NOTE]
>  Puede que desee leer esta sección con la **ExceptionHandlerOrch** orquestación abierta en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="application-errors"></a>Errores de aplicación  
 El controlador de excepciones en primer lugar registra el error mediante una llamada a la **PostError** método de la **ErrorHandler** objeto en el **utilidades** ensamblado. A continuación, comprueba si se trata de un error del sistema o de un error de aplicación. La siguiente captura de pantalla muestra la rama de la orquestación que procesa las excepciones de aplicación:  
  
 ![Rama de aplicación de la orquestación de ExceptionHandler](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")  
  
 Para un error de aplicación, la orquestación construye una cadena que describe el error y llama el **ErrorHandlerOrch** orquestación. Esta orquestación envía el error a operaciones en las que un operador decide si corregir el error o finalizar la operación. Si el operador corrige el error, la orquestación ErrorHandlerOrch devuelve el mensaje reparado y se vuelve a intentar repetir la operación. El controlador de excepciones para ello mediante una llamada a la **Invoke** método de la **Recaller** objeto en el **utilidades** ensamblado. El **Recaller** objeto usa la reflexión para llamar al código que produjo el error.  
  
 Si la llamada a **Invoke** se realiza correctamente, las salidas del controlador de excepción. En caso contrario, se produce un bucle invertido y se intenta la llamada a **Invoke** nuevo. Para obtener más información sobre la **Recaller** de objetos, consulte [el objeto Recaller](../core/the-recaller-object.md).  
  
## <a name="system-errors"></a>Errores del sistema  
 El siguiente diagrama muestra la rama de error de sistema de la **ExceptionHandler** orquestación:  
  
 ![Error del sistema de orquestación de ExceptionHandler](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")  
  
 Para un error del sistema, el controlador de excepciones llama primero la **CheckInterrupt** orquestación y, a continuación, espera un minuto. Este tiempo de espera permite que desaparezcan los errores a corto plazo temporales, como los problemas de conexión de red, antes de que se vuelva a intentar la operación. Cuando se realizan llamadas remotas, siempre existe la probabilidad de que se produzca un problema de red.  
  
> [!NOTE]
>  Como regla general, en un diseño que se puede interrumpir, lo ideal es comprobar si hay interrupciones durante uno de los períodos de espera o justo después de uno de ellos para ver si se ha producido una interrupción.  
  
 Después de la espera, el controlador utiliza la **Invoke** método de la **Recaller** objeto que se va a ejecutar el código original. Si la llamada se realiza correctamente, el controlador se cierra. En caso contrario, el controlador intentará ejecutar el código original un par de veces más. Si se produce un error en los tres intentos, el controlador crea una cadena de error y llama el **ErrorHandlerOrch** orquestación.  
  
 Si al procesar una excepción del sistema se genera una excepción, un bloque de excepción la captura:  
  
 ![Controlador de excepciones para rama de Error del sistema](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")  
  
 El controlador de la excepción comprueba el tipo de excepción y reduce el contador de reintentos si se trata de una excepción del sistema o establece un indicador para especificar una excepción de aplicación.  
  
## <a name="the-errorhandlerorch-orchestration"></a>Orquestación ErrorHandlerOrch  
 El siguiente diagrama muestra la primera parte de la **ErrorHandlerOrch** orquestación:  
  
 ![Orquestación de controlador de errores, primera parte](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")  
  
 El **ErrorHandlerOrch** orquestación comprueba en primer lugar el **IsBadOrder** parámetro para ver si el error es un pedido incorrecto (**IsBadOrder** es true) o algún otro error. Si el error es de pedido incorrecto, asigna el destino del mensaje desde el remite del pedido original y vuelve a enviar el mensaje al sistema de atención al cliente. Si no se refiere a un pedido incorrecto, la orquestación crea un mensaje de error de pedido y lo envía al sistema de operaciones.  
  
 Después de cualquier error, la orquestación escucha si se genera un mensaje de respuesta o de interrupción:  
  
 ![Controlador de errores, segunda parte](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")  
  
 Si la orquestación recibe una respuesta, vuelve al autor de la llamada. Si la orquestación recibe un mensaje de interrupción, pasa el mensaje a un puerto de interrupción y genera una excepción personalizada **InterruptException**.  
  
 Para obtener más información acerca de cómo la solución utiliza y controla las interrupciones, consulte [de interrupción de control en la solución de administración de procesos empresariales](../core/interrupt-handling-in-the-business-process-management-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Control de excepciones en la solución de administración de procesos empresariales](../core/exception-handling-in-the-business-process-management-solution.md)   
 [Excepciones personalizadas](../core/custom-exceptions.md)   
 [Control de interrupciones en la solución de administración de procesos empresariales](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [Objeto Recaller](../core/the-recaller-object.md)