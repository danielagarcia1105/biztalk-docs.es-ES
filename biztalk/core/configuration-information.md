---
title: "Información de configuración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a35767815eaf7406a7baae5d9dccb833492287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-information"></a>Información de configuración
Este tema describe cómo configurar la **reglas de llamada** forma.  
  
## <a name="orchestration-variables-and-fact-types"></a>Tipos de hechos y variables de orquestación  
 En la orquestación donde la **reglas de llamada** forma reside, debe disponer de las variables que coinciden con los tipos utilizados en la directiva. Si no tiene el tipo de variables correcto, no puede suministrar los parámetros correctos a la directiva. Suponga que tiene un **reglas de llamada** forma de una orquestación, CallMyRules y utiliza CallMyRules para llamar a MyPolicy. Si una clase .NET, MyClass, se utiliza en MyPolicy, deberá crear una variable de tipo MyAssembly.MyClass en la orquestación. De forma similar, si MyPolicy tiene **DataConnection** enlaces, debe crear una variable de un **Microsoft.RuleEngine.DataConnection** tipo en la orquestación.  
  
 Además de crear las variables en la orquestación, deberá también crear instancias para estas variables. Puede hacerlo agregando una **expresión** forma a la orquestación. En el ejemplo anterior, debe crear una instancia MyAssembly.MyClass y un **DataConnection** instancia. Para crear una instancia de la **DataConnection** instancia, realice lo siguiente:  
  
-   Crear un **SqlConnection** instancia y asígnela a MySqlCon.  
  
-   Crear un **DataConnection** instancia y asígnela a dataConnection (variable de **DataConnection** tipo), tal y como se muestra en el siguiente fragmento de código:  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  Si no tiene variables que coincidan con los tipos de hechos, estos tipos no aparecerán como parámetros en la **especificar parámetros de la directiva** cuadro de lista en la **configuración de directiva CallRules** cuadro de diálogo.  
  
> [!NOTE]
>  El motor de orquestación convierte automáticamente las variables de mensaje que indique como parámetros a una directiva del BRE en **TypedXmlDocument** objetos y los impone en la memoria de trabajo del motor de reglas antes de ejecutar la directiva. Por lo tanto, no es necesario que declare variables de tipo TypedXmlDocument como hizo para los hechos de base de datos y .NET.  
  
## <a name="message-type-and-document-type"></a>Tipo de mensaje y tipo de documento  
 Debe asegurarse de que el **DocumentType** propiedad para nodos XML utilizada en la regla de negocios (que implementó en el Compositor de reglas de negocios) es el mismo que el **MessageType** para aquellos nodos XML definidos en el orquestación, debe coincidir con el **MessageType** del mensaje o parte del mensaje que se pasa al motor de reglas en la **reglas de llamada** forma.  
  
 Por ejemplo, si se define un esquema XML de pedido (PO) en un proyecto de BizTalk, el **MessageType** definido para este esquema es **BTSProject.PO** (si **BTSProject** es el espacio de nombres o el nombre del proyecto mediante el espacio de nombres predeterminado).  
  
 En el caso de los **Pedido\Cantidad** elemento, antes de colocarlo en una definición de regla, debe cambiar su **DocumentType**propiedad **BTSProject.PO** en la ventana Propiedades . Puede tener acceso a la ventana Propiedades cuando se selecciona cualquier nodo en el esquema en el **esquemas XML** pestaña en el Explorador de hechos. Este cambio se aplica a todos los elementos del esquema, pero no se almacenará con él. Debe volver a establecerse al iniciar el Compositor de reglas de negocio o al volver a cargar el esquema. Esto es necesario para definiciones de vocabulario basadas en esquemas XML o en reglas generadas directamente desde esquemas XML. Si no lo hace, aún puede ejecutar la directiva, pero la **reglas de llamada** forma no funcionará correctamente y el tipo de mensaje no aparecerá en la **especificar parámetros de la directiva** cuadro de lista en la  **Configuración de directiva CallRules** cuadro de diálogo.