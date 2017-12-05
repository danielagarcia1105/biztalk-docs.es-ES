---
title: "Forma reglas de cómo utilizar la llamada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85badfaf22ff4fb6aebd9ed19c757faaa1f303c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-use-the-call-rules-shape"></a>Cómo usar la forma Reglas de llamada
En el Diseñador de orquestaciones, puede usar el **reglas de llamada** forma para llamar a una directiva empresarial.  
  
### <a name="to-configure-the-call-rules-shape"></a>Para configurar la forma Reglas de llamada  
  
1.  En el cuadro de herramientas, en la **orquestaciones de BizTalk** ficha, arrastre el **reglas de llamada** forma en una línea de conexión en la superficie de diseño de orquestación.  
  
     : "O":  
  
     Haga clic en la línea de conexión o el marcador de posición de la forma en la que desea agregar la forma, seleccione **Insertar forma** en el menú contextual y, a continuación, haga clic en **reglas de llamada**.  
  
    > [!NOTE]
    >  En BizTalk Server, no es necesario tener un ámbito atómico para insertar un **reglas de llamada** forma. Puede arrastrar una **reglas de llamada** forma en la superficie de diseño de orquestación en el cuadro de herramientas. Sin embargo, en el servidor BizTalk Server, el **reglas de llamada** elemento de menú está deshabilitado en el menú contextual si se intenta insertar un **reglas de llamada** forma dentro de una orquestación que no tiene un ámbito atómico. Ésta es una limitación del producto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  En el Diseñador de orquestaciones, seleccione la **reglas de llamada** forma.  
  
3.  Haga doble clic en la forma que se va a mostrar el **configuración de directiva CallRules** cuadro de diálogo.  
  
4.  En el **seleccione la directiva empresarial que se va a llamar a** lista desplegable, seleccione la directiva que necesite.  
  
    > [!NOTE]
    >  La configuración de directivas de Reglas de llamada se fijará en la última versión guardada de una directiva para determinar los tipos que se han utilizado en ésta. En tiempo de ejecución, se utilizará la última versión implementada de la directiva.  
  
5.  En el **especificar parámetros de la directiva** cuadro de lista, seleccione una variable de la **nombre de parámetro** propiedad.  
  
    > [!NOTE]
    >  El **reglas de llamada** forma básicamente reconstruye el mensaje, como si utilizara una **construir** forma, que a su vez puede provocar que las propiedades de contexto del mensaje se perderán.  
  
    > [!NOTE]
    >  Puede especificar un mensaje o una variable de .NET como un parámetro a una directiva del BRE. Para pasar un **TypedXmlDocument** hecho, especifique el mensaje correspondiente declarado en la orquestación como un parámetro. Para pasar un hecho de .NET, especifique una variable de .NET declarada en la orquestación como parámetro. Para pasar un hecho de base de datos, especifique una variable de .NET de tipo **DataConnection** o **TypedDataTable** como un parámetro a la directiva.