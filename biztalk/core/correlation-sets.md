---
title: Conjuntos de correlaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bad0bf41f5b509f9a64e9484cac84f66a84e4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="correlation-sets"></a>Conjuntos de correlaciones
Este tipo de correlación de mensajes con instancias de orquestación se consigue mediante la definición de conjuntos de correlaciones. Un conjunto de correlaciones es un conjunto de propiedades *con valores específicos*. Es diferente de un tipo de correlación, que no es más que una lista de propiedades. Si un mensaje entrante no tiene todas estas propiedades, con valores coincidentes para cada una de ellas, se producirá un error en la correlación y la instancia de orquestación no recibirá el mensaje.  
  
 Los tipos de correlación definen un conjunto de propiedades en el que se correlacionarán mensajes. Éstos pueden ser cualquier propiedad definida anteriormente en un esquema de propiedades e implementada con algún proyecto de BizTalk, incluidas las propiedades del sistema implementadas con GlobalPropertySchemas, que se instala como parte de la instalación básica de BizTalk. Un conjunto de correlaciones define un conjunto de propiedades, así como de valores de estas últimas, que un mensaje debe contener para que su procesamiento se efectúe en una orquestación concreta.  
  
 Por ejemplo, un tipo de correlación se compondría de las propiedades siguientes:  
  
|Tipo de correlación (propiedad)|Posible representación XML|  
|-------------------------------|---------------------------------|  
|Número de la seguridad social|\<Nº DE SS\>\</SSN\>|  
|Fecha de nacimiento|\<FECHA DE NACIMIENTO\>\</DOB\>|  
|Gender|\<Sexo\> \< /género\>|  
  
 Mientras que un conjunto de correlación derivado de este tipo de correlación constaría de las propiedades y valores siguientes:  
  
|Propiedad o valor del conjunto de correlación|Posible representación XML|  
|-------------------------------------|---------------------------------|  
|Número de la seguridad social = 222112222|\<Nº DE SS\>222112222\</SSN\>|  
|Fecha de nacimiento= “1/1/1995”|\<FECHA DE NACIMIENTO\>"1/1/1995"\</DOB\>|  
|Sexo = Varón|\<Sexo\>M \< /género\>|  
  
> [!NOTE]
>  Cada conjunto de correlación admite un máximo de tres parámetros.  
  
## <a name="initializing-correlation-sets"></a>Conjuntos de correlaciones de inicialización  
  
-   **Conjuntos de correlaciones inicializados en una acción de recepción**  
  
     Los conjuntos de correlaciones inicializados en una acción de recepción definen el conjunto exacto de propiedades que debe contener un mensaje publicado para que lo procesen las acciones de recepción correspondientes en una orquestación. Un conjunto de correlaciones de inicialización creará un conjunto a partir de un tipo de correlación basado en los valores correspondientes de un documento.  
  
-   **Conjuntos de correlaciones inicializados en una acción de envío**  
  
     Los conjuntos de correlaciones inicializados en una acción de envío se crean a partir de un tipo de correlación basado en los valores correspondientes de un documento y promocionan las propiedades de correlación en el documento saliente.  
  
## <a name="following-correlation-sets"></a>Siguientes conjuntos de correlaciones  
 Los conjuntos de correlaciones siguientes solo pueden enlazarse a una acción de recepción de no activación o a una acción de envío. Estos conjuntos de correlaciones se especifican conjuntamente con los conjuntos de correlación inicializados anteriormente.  
  
-   **Siguientes conjuntos de correlaciones enlazados a una acción de recepción**  
  
     Los conjuntos de correlaciones siguientes enlazados a una acción de recepción definen las propiedades y los valores que el documento debe contener para su recepción.  Las acciones de recepción con conjuntos de correlaciones siguientes aceptan documentos que contienen propiedades de un conjunto de correlación inicializado anterior.  
  
-   **Siguientes conjuntos de correlaciones enlazados a una acción de envío**  
  
     Los conjuntos de correlaciones siguientes enlazados a una acción de envío indican que el conjunto de propiedades del conjunto se promociona en el documento saliente.  
  
## <a name="inspecting-correlation-sets"></a>Inspeccionar conjuntos de correlaciones  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]proporciona la capacidad de inspeccionar conjuntos de correlaciones. Puede inspeccionar un conjunto de correlaciones en una forma Expresión mediante código parecido al siguiente:  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 El ejemplo anterior se supone que ha creado una variable denominada **MsgLen** de tipo **System.Int16** y que la orquestación contiene una correlación de conjunto con nombre **Correlation_1**. La capacidad de inspeccionar conjuntos de correlaciones puede resultar útil si necesita inspeccionar el valor de una correlación que una orquestación ha pasado a otra.  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a>Pasar conjuntos de correlaciones a orquestaciones como parámetros  
 Puede pasar correlaciones como *en* parámetros a otras orquestaciones.