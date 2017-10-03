---
title: "Control de excepciones en la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a>Control de excepciones en la solución de administración de procesos empresariales
La solución Administración de procesos empresariales utiliza una orquestación de control de excepciones especial, así como el control de excepciones estándar de BizTalk Server. Además, para los errores de adaptadores, canalizaciones, asignaciones y enrutamiento, usa la nueva característica de informes de errores. Este sistema personalizado se basa en el **ExceptionHandler** orquestación. La solución utiliza la **ExceptionHandler** orquestación para volver a intentar una operación o volver a intentar una llamada que podría realizarse correctamente después de un problema transitorio.  
  
> [!NOTE]
>  Se puede reutilizar el código de orquestaciones, como **activar**, que utilizan el **ExceptionHandler** orquestación. Todas estas orquestaciones incluyen un ámbito denominado **CallingCode** con un **excepción** bloque. Reemplace el código de la **CallingCode** ámbito con el código. El **excepción** bloque define todas las variables necesarias para llamar a la **ExceptionHandler** orquestación. Edite los valores asignados a las variables.  
  
 La solución utiliza excepciones personalizadas y un par de excepciones de BizTalk predefinidas para los casos de errores irrecuperables, como un mensaje de pedido incorrecto.  
  
> [!NOTE]
>  La solución usa un adaptador personalizado para el control de errores en algunos puertos. Para obtener más información acerca del adaptador, vea [el adaptador Ops](../core/the-ops-adapter.md).  
  
 Esta sección se describe la **ExceptionHandler** orquestación y las excepciones personalizadas. También se ofrece una breve descripción acerca de cómo la solución utiliza la característica del producto de informes de errores.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [La orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md)  
  
-   [Excepciones personalizadas](../core/custom-exceptions.md)