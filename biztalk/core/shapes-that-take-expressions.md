---
title: Formas que usan expresiones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, shapes
- Decide shape [Orchestration Designer], expressions
- Message Assignment shape [Orchestration Designer], expressions
- Filter Expression property
- Listen shape [Orchestration Designer], expressions
- Delay shape [Orchestration Designer], expressions
- shapes, expressions
- Receive shape [Orchestration Designer], expressions
- Loop shape [Orchestration Designer], expressions
- Rule shape [Orchestration Designer]
ms.assetid: 0d27f711-ff7c-422b-b231-aa3c9a42ed0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e78ada2c69205a0201c4bae9f3c7fa5b0656fa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270788"
---
# <a name="shapes-that-take-expressions"></a>Formas que usan expresiones
Varias formas en el Diseñador de orquestaciones, incluidos los **decidir** y **bucle**, usan expresiones booleanas para crear reglas que controlan la bifurcación. Otras formas utilizan expresiones para otros fines. Puede crear o editar una expresión para estas formas mediante el Editor de expresiones de BizTalk.  
  
 En la siguiente tabla se resumen las formas que utilizan expresiones en el Diseñador de orquestaciones y se muestran los tipos de datos válidos para esas expresiones.  
  
|Forma|Descripción del uso de la expresión|Tipos de datos válidos para las expresiones|  
|-----------|-----------------------------------|---------------------------------|  
|**Decidir**|**Decidir** contienen formas **regla** formas, que usan expresiones booleanas.|Boolean|  
|**Recepción**|**Recibir** formas que tienen la propiedad Activar establecida en True utilizan la **expresión de filtro** propiedad que se va a filtrar los mensajes entrantes. La expresión de esta propiedad debe evaluarse como booleana, cuyo valor determina si se debe aceptar o no un mensaje entrante.<br /><br /> El **expresión de filtro** cuadro de diálogo se utiliza para crear expresiones de filtro.|Boolean|  
|**Bucle**|A **bucle** forma requiere un **regla** forma, que a su vez debe contener una expresión booleana.|Boolean|  
|**Regla**|**Regla** (que se muestra en el área de procesos como formas "rama") son formas simples que contienen expresiones booleanas y se usan dentro de otras formas (complejas) para regir la bifurcación.|Boolean|  
|**Escuchar**|Cada rama de un **escuchar** forma contiene, como mínimo, ya sea un **recepción** forma, que utiliza una expresión booleana solo para las expresiones de filtro (vea la entrada del **recepción**) , o un **retraso** forma, que usa un **System.DateTime** objeto o **System.TimeSpan** objeto.|Booleano, System.DateTime, System.TimeSpan|  
|**Retraso**|La expresión utilizada en un **retraso** forma se debe evaluar como un **System.DateTime** objeto, para expresar un plazo, o un **System.TimeSpan** objeto para expresar una duración.|System.DateTime, System.TimeSpan|  
|**Asignación de mensajes**|La expresión en una **asignación de mensajes** forma asigna un valor a un mensaje. El valor asignado puede ser de cualquier tipo, aunque normalmente se asigna un mensaje.|Cualquiera|  
|**Expresión**|El **expresión** forma le permite escribir las expresiones que desee utilizar en la orquestación. Por ejemplo, puede hacer una llamada a .NET para ejecutar un programa externo o, sencillamente, cambiar los valores de las variables de la orquestación.|Cualquiera|  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo usar la forma expresión](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a>Vea también  
 [Requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md)   
 [Construir mensajes](../core/constructing-messages.md)   
 [Configurar las formas de Control de flujo](../core/configuring-flow-control-shapes.md)