---
title: "Cómo agregar Variables de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8516ceb780e64c4f4a01370de0e7c40098f3da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-orchestration-variables"></a>Cómo agregar variables de orquestación
La ventana Vista orquestación permite administrar las propiedades de una orquestación (también conocido como **servicio** propiedades), parámetros, puertos, mensajes y otras variables. Además de los puertos y mensajes, puede crear variables de tipo entero, variables booleanas, variables de cadena o variables de una clase .NET.  
  
 Asimismo, puede usar la ventana Vista orquestación para administrar las variables que pertenecen a los ámbitos.  
  
### <a name="to-add-a-variable"></a>Para agregar una variable  
  
1.  En la ventana Vista orquestación, haga clic en el **Variables** carpeta y, a continuación, haga clic en **nueva Variable**.  
  
     El **Variables** carpeta se expande, si se contrae, y se agrega una nueva variable.  
  
2.  Asígnele un nombre a la variable mediante la escritura de un nombre en la propiedad Identificador de la ventana Propiedades.  
  
3.  Asocie la variable con un tipo, por ejemplo, una clase .NET.  
  
    > [!NOTE]
    >  El **tipos** lista desplegable contiene los siguientes tipos de variables predefinidos: **booleano**, **bytes**, **datetime**,  **decimal**, **doble**, **int16**, **int32**, **int64**, **sbyte** , **único**, **cadena**, **timespan**, **uint16**, **uint32**y **uint64**. También puede acceder a los tipos de datos de .NET y las clases seleccionando  **\<clase. NET... \>** , que abrirá el **Seleccionar tipo de artefacto** cuadro de diálogo.  
  
4.  Si selecciona un tipo de variable predefinido, tiene la opción de especificar un valor inicial para la variable. En la ventana Propiedades, establezca la **valor inicial** propiedad.  
  
     De otro modo, si el tipo seleccionado es una clase .NET, tiene la opción de usar un constructor predeterminado. En la ventana Propiedades, establezca la siguiente propiedad:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |**Utilizar Constructor predeterminado**|Si se encuentra disponible un constructor predeterminado para una clase .NET, esta propiedad determina si se llamará al constructor predeterminado cuando se use la variable por primera vez:<br /><br /> Es true, se llamará al constructor predeterminado. Este es el valor predeterminado cuando se encuentre disponible un constructor predeterminado.<br /><br /> False: no se llamará al constructor predeterminado; debe llamar a un constructor en una expresión o realizar una asignación a la variable antes de utilizarla en la orquestación.|  
  
    > [!NOTE]
    >  Si el constructor predeterminado requiere parámetros de entrada, puede establecer **utilizar Constructor predeterminado** a **False** y, a continuación, llame al constructor de un **asignación** forma; para ejemplo, `myVariable = myNamespace.myClass (param1, param2)`.  
  
    > [!NOTE]
    >  Al agregar una variable a la orquestación, antes de definirla por completo, verá los signos de exclamación en la orquestación. Si elimina esta variable antes de definirla por completo y continúan apareciendo signos de exclamación en la orquestación, puede exigir que la orquestación elimine estos signos de exclamación mediante la creación y eliminación de un parámetro de orquestación.  
  
### <a name="to-remove-a-variable"></a>Para quitar una variable  
  
-   En la ventana Vista orquestación, haga clic en la variable que desea quitar y, a continuación, haga clic en **eliminar**.