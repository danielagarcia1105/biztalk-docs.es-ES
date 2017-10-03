---
title: El controlador de errores de las operaciones de ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-operations-error-handler"></a>El controlador de errores de operaciones de ejemplo
El controlador de errores de las operaciones de ejemplo tiene tres ensamblados principales: **OperationsClient**, **OperationsHandler**, y **OperationsServer**.  
  
 La solución configura el adaptador para usar el **OpsClient** objeto en el **OperationsClient** ensamblado. Como cabría esperar, el **OpsClient** objeto implementa la **IOpsAIC** interfaz.  
  
 El **OpsClient** de objeto usa la **IOperationsSystem** interfaz para llamar a la **OpsHandler** objeto a través de la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] característica de comunicación remota. El **IOperationsSystem** interfaz aparece como sigue:  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 El **OperationsServer**, una aplicación de consola, escucha las solicitudes de la **OpsHandler** de objeto y actúa como el servidor para el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] característica de comunicación remota. Llamando a la **Execute** método de la **OpsClient** objeto a su vez, se invoca el **Post** método de la **OpsHandler** objeto.  
  
 El **OpsHandler** métodos responden escribiendo las cadenas de argumento utilizando el **seguimiento** objeto. Esto envía los errores a la consola. Para obtener más información sobre la **seguimiento** de objetos, vea "Clase Trace" en la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] biblioteca de clases.  
  
> [!NOTE]
>  El patrón aquí es el mismo que en el **OrderHandler** en el que una interfaz especifica las llamadas al método entre un cliente y un objeto remoto. Sin embargo, hay un nivel adicional de direccionamiento indirecto entre el **OpsClient** y **OpsHandler**.  
  
## <a name="see-also"></a>Vea también  
 [El adaptador Ops](../core/the-ops-adapter.md)