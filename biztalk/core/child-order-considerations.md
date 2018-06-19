---
title: Consideraciones acerca del orden secundario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0909a8d69f5079e493fbc579d6ef4b0ca56f9c61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232740"
---
# <a name="child-order-considerations"></a>Consideraciones acerca del orden secundario

## <a name="requirements-for-header-in-a-flat-file"></a>Requisitos de encabezado en un archivo plano
Hay dos escenarios relacionados con archivos sin formato delimitados para el que se aplican consideraciones especiales al establecer el **orden secundario** propiedad. El primer escenario se refiere a situaciones en las que el documento de archivo sin formato tiene un encabezado, un cuerpo y, opcionalmente, un finalizador. En estos escenarios, debe atenerse a los siguientes requisitos:  
  
-   Debe establecer el **orden secundario** propiedad del registro raíz (delimitado) del encabezado que se **postfijo**.  
  
-   Si hay un finalizador, debe establecer el **orden secundario** propiedad del registro raíz (delimitado) del cuerpo en **postfijo**.  
  
-   Si un finalizador no está presente, puede establecer la **orden secundario** propiedad del registro raíz (delimitado) del cuerpo en **prefijo**, **infijo**, o **depostfijo**.  
  
-   Si hay un finalizador, puede establecer la **orden secundario** propiedad del registro raíz (delimitado) de ese finalizador en **prefijo**, **infijo**, o **depostfijo**.  
  
-   Puede establecer la **orden secundario** propiedad de los registros subordinados delimitados del encabezado, cuerpo y finalizador en **prefijo**, **infijo**, o **postfijo**.  
  
 El segundo escenario relacionado con delimitado por archivos sin formato y la **orden secundario** propiedad es que esta propiedad debe establecerse según lo que puede esperar los componentes en tiempo de ejecución de los nodos. La configuración correcta para el **orden secundario** propiedad no sea evidente para los nodos raíz y de grupo, como se muestra en los siguientes escenarios:  
  
-   **Nodo raíz.** piense en un archivo sin formato típico cuya estructura conste de registros seguidos de una combinación de retorno de carro y avance de línea. El delimitador separa los registros del archivo, y la secuencia es normalmente registro, delimitador, registro, delimitador, etc. En esta situación, el delimitador va siempre después los datos, que se corresponde con un **orden secundario** configuración de la propiedad de **postfijo**.  
  
-   **Nodos de grupo.** los nodos de grupo mostrados en BizTalk Server y en la representación XSD del esquema no están presentes de forma explícita en la representación de archivo sin formato del mensaje de instancia. Considere un pedido que contiene una colección de registros para cada elemento de línea, donde esos registros se repiten numerosas veces para representar los distintos elementos de línea del pedido. El esquema de dicho mensaje probablemente incluirá un nodo denominado LineItems que sirve como contenedor para el conjunto de repetición (a veces conceptual): en la representación de archivo sin formato del mensaje de instancia, el contenedor LineItems es de naturaleza conceptual y representado por la secuencia adecuada de los datos y delimitadores; en la representación XML del mensaje de instancia, el contenedor LineItems está presente de forma explícita en forma de un **LineItems** elemento en XML.  
  
 Considere un mensaje que contiene un nodo raíz y solo un nodo de grupo. Es sencillo ver si el último delimitador de la secuencia de entrada pertenece al nodo raíz. Por tanto, la secuencia de datos y delimitador en el bucle conceptual es meramente uno o más registros de elementos de línea. Solo en el caso de que haya más de un registro de elemento de línea, habrá un delimitador para separarlos. En este caso, el número de delimitadores es uno menos que los conjuntos de elementos que se están delimitando; además, los delimitadores se encuentran entre los elementos delimitados de una estructura conocida como Infijo.  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones de registro delimitadas](../core/delimited-record-considerations.md)   
-  **Orden secundario (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]