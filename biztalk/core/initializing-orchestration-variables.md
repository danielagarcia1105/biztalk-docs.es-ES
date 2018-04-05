---
title: Inicializar Variables de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 770e4e55-1fb9-4b43-854c-63aec5a3c5ba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a90fbc33343e3576d6199a0a97a7a57ca881f720
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="initializing-orchestration-variables"></a>Inicializar variables de orquestación
Puede inicializar el valor de una variable si lo establece en la ventana Propiedades. Por ejemplo, puede establecer la **valor inicial** como 32 para inicializar la variable de tipo System.Int32. Cuando se agrega un valor inicial a una variable de cadena de tipo, debe escribir el valor inicial entre comillas en la ventana Propiedades. Si desea que la cadena contenga comillas, use la barra diagonal inversa como carácter de escape y barras diagonales inversas consecutivas cuando desee colocar una barra diagonal inversa literal en la cadena. Si no especifica un valor para las variables, las variables se asignará valores predeterminados en cuanto se crea una instancia de la orquestación.  
  
 Si la variable es una instancia de una clase, puede especificar un constructor para que la inicialice. De forma predeterminada, el **utilizar Constructor predeterminado** propiedad está establecida en **True** si está disponible; un constructor predeterminado, por lo tanto, se llamará al constructor predeterminado. Si solo desea utilizar el constructor predeterminado, no es necesario inicializar las variables de nuevo en el **expresión** forma para evitar la llamada al constructor dos veces. Si el **utilizar Constructor predeterminado** propiedad está establecida en **False**, no se llamará al constructor predeterminado; debe llamar a un constructor de una expresión o realizar una asignación a la variable antes de que se puede usar en la orquestación. Además, si el constructor requiere parámetros de entrada, debe establecer **utilizar Constructor predeterminado** a **False** y, a continuación, llame al constructor de un **expresión** forma; para ejemplo, `myVariable = myNamespace.myClass (param1, param2)`.  
  
 La única circunstancia en la que deben inicializar explícitamente las variables es cuando la orquestación contiene más de uno activar recibe, como sea posible en un **ámbito**, **acciones paralelas** , o **escuchar** forma. En este caso, la inicialización automática está deshabilitada, y debe usar un **expresión** forma para inicializar las variables. Debe colocar un **expresión** forma después de cada recepción de activación, y antes de que se tiene acceso a cualquier variable en la orquestación.