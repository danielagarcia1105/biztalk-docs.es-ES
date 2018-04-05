---
title: Cómo agregar parámetros a orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, parameters
ms.assetid: 35c731ed-6327-4de7-8d2e-4d14024bda77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8328a97631efb2b8454e0a2679b257d35402cf4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-parameters-to-orchestrations"></a>Cómo agregar parámetros a orquestaciones
Puede especificar qué parámetros debería tomar la orquestación en la ventana Vista orquestación. Una orquestación puede tomar los siguientes elementos como parámetros:  
  
-   Mensajes  
  
-   Variables (objetos incluidos)  
  
-   Conjuntos de correlaciones  
  
-   Vínculos de rol  
  
-   Puertos  
  
 Los parámetros se pueden pasar entre orquestaciones como parámetros de entrada o de salida. Los parámetros de entrada se pueden pasar por valor o por referencia. En cambio, los parámetros de salida solo se pueden pasar por referencia. Los parámetros pueden incluir variables, mensajes, conjuntos de correlaciones, vínculos de rol y puertos.  
  
### <a name="to-set-orchestration-parameters"></a>Para establecer parámetros de orquestación  
  
1.  En la ventana Vista orquestación, use la **parámetros de orquestación** carpeta para agregar las variables, mensajes y puertos.  
  
2.  Para cada elemento agregado a la **parámetros de orquestación** carpeta, utilice la ventana Propiedades para especificar el **dirección** propiedad:  
  
    -   En, se pasa un parámetro por valor.  
  
    -   Ref, se pasa un parámetro por referencia.  
  
    -   Salida: un parámetro se pasa por referencia.  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a>Para agregar un parámetro a una orquestación  
  
1.  En la ventana Vista orquestación, haga clic en el **parámetros de orquestación** carpeta y, a continuación, haga clic en el tipo de parámetro que desee.  
  
2.  En el caso de puertos y vínculos de rol configurados, use el Asistente para configurar el parámetro.  
  
     : "O":  
  
     Para otros tipos de parámetros, use la página de propiedades para configurar el parámetro.  
  
 **Tipos de parámetros**  
  
 Los parámetros se pueden pasar por valor, como parámetros de referencia y como parámetros de salida. Cuando se pasa un parámetro por valor a una orquestación, se realiza una copia de los datos y la orquestación la usa.  
  
 Cuando se usa un parámetro de referencia, no se realiza ninguna copia. El programa que llama y la orquestación comparten la ubicación de la memoria que contiene los datos y la orquestación puede modificar este contenido. Esta modificación implica que el valor del parámetro se cambia no solo en la orquestación sino también en el programa que llama.  
  
 Un parámetro de salida es similar a un parámetro de referencia pero la orquestación no puede asumir que contiene datos válidos cuando lo pasa; en su lugar, el programa que llama espera que la orquestación asigne un valor a este parámetro.  
  
 **Reglas de los parámetros de orquestación**  
  
-   solo puede pasar mensajes y variables (objetos incluidos) como parámetros de salida o de referencia.  
  
-   No se puede eliminar ni hacer referencia a parámetros a una orquestación en un **Iniciar orquestación** forma.  
  
-   Los parámetros de entrada, incluidos los vínculos de rol y los puertos dinámicos, deben estar asignados de forma definitiva antes de que se puedan pasar a una orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Formas de orquestación](../core/orchestration-shapes.md)   
 [Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md)   
 [Cómo usar el cuadro de diálogo de tipo de artefacto Select](../core/how-to-use-the-select-artifact-type-dialog-box.md)