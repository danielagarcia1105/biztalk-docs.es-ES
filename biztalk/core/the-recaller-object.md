---
title: Objeto Recaller | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-recaller-object"></a>Objeto Recaller
La solución Administración de procesos empresariales proporciona una forma genérica de reintentar llamar a algunos métodos de objeto con errores. La solución hace esto mediante la **Recaller** objeto en el **ExceptionHandler** orquestación. El **ExceptionHandler** orquestación utiliza el objeto para volver a intentar las llamadas de método de objeto. Para obtener más información, consulte [la orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md).  
  
## <a name="the-invoke-method"></a>Método Invoke  
 El **Recaller** objeto tiene un único método estático, **Invoke**. Puesto que es estático, nunca debe crear una instancia de la **Recaller** objeto. Puede usar el **Invoke** método de tres maneras: para crear un objeto, llamar a un método estático para un objeto, o para llamar a un método no estático de un objeto.  
  
> [!NOTE]
>  El **Invoke** método actúa como un contenedor para la **Type.InvokeMember** método en el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] biblioteca de clases.  
  
### <a name="arguments-for-the-invoke-method"></a>Argumentos del método Invoke  
 La tabla siguiente describe los argumentos para el **Invoke** método:  
  
|Parámetro|Tipo|Description|  
|---------------|----------|-----------------|  
|*t*|**Tipo**|Tipo de objeto en el que se debe llamar el método.|  
|*obj*|**Object**|Instancia del objeto que se va a usar.|  
|*methodName*|**string**|El nombre del método que se invoca.|  
|*args*|**Matriz**|Una matriz de tipo **objeto** que contiene los argumentos del método.|  
  
 Para llamar al constructor de un objeto, use una cadena vacía ("") o **null** para *methodName*.  
  
 Para llamar a un método estático, use **null** para *obj*.  
  
 Para llamar a un método no estático, proporcione todos los argumentos.  
  
> [!NOTE]
>  Usar **null** como el valor del argumento de tipo, *t*, hace que **Invoke** para producir un **ArgumentNullException** excepción. El argumento *t* no debe ser null porque el **Invoke** método usa la **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] método.  
  
## <a name="calling-invoke"></a>Llamar a Invoke  
 En la solución, solo el **ExceptionHandler** orquestación utiliza la **Recaller** objeto. El **ExceptionHandler** , a su vez, utiliza otras orquestaciones. Los valores pasados a la **Invoke** método proceden de estas otras orquestaciones. Por ejemplo, aparece el siguiente código en el **activar** orquestación en el **InitialException** forma expresión:  
  
```  
Ex = CodeEx;  
ObjectType = orderHandler.GetType();  
CalledObject = orderHandler;  
Reason = "Standard Activate Failed";  
MethodName = "Activate";  
ParameterArray = System.Array.CreateInstance(typeof(System.Object),  
                                              3 );  
ParameterArray.SetValue(ServiceType, 0);  
ParameterArray.SetValue(OrderMsg.CustNum, 1);  
ParameterArray.SetValue(OrderMsg.OrderNum, 2);  
ReturnValue = null; // no return value expected  
  
```  
  
 Observe cómo el código crea una matriz mediante **System.Array.CreateInstance** y usa el **SetValue** método para almacenar los valores que se usan en él.  
  
 Después de la forma de expresión, la orquestación Activate llama el **ExceptionHandler** orquestación. En el siguiente código se muestra cómo el Diseñador de orquestaciones traduce la forma de llamada:  
  
```  
call Microsoft.Samples.  
    BizTalk.SouthridgeVideo.  
        OrderManager.ExceptionHandlerOrch  
            (  
                Reason,  
                Ex,  
                CalledObject,  
                MethodName,   
                ParameterArray,   
                OrderCorrelation,   
                OrderMsg,   
                out ReturnValue,   
                ObjectType  
            );  
  
```  
  
 En el **ExceptionHandler** orquestación, el código siguiente aparece en el **Call Original Code** forma expresión:  
  
```  
ReturnValue =   
    Microsoft.Samples.  
        BizTalk.SouthridgeVideo.  
            Utilities.Recaller.  
                Invoke(  
                    ObjectType,  
                    CalledObject,  
                    MethodName,  
                    ParameterArray  
                );  
```  
  
 Observe que aunque los nombres de argumento coinciden con los de la llamada de la orquestación Activate, los argumentos coinciden por orden y no por nombre cuando se llaman las orquestaciones.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [La orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md)