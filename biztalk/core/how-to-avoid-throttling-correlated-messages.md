---
title: Cómo evitar la limitación de mensajes correlacionados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfe47747-01e7-4e2f-bbd5-d5055cea001a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 755622a55f7b0216399cfe33842994ff0f70a259
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994437"
---
# <a name="how-to-avoid-throttling-correlated-messages"></a>Cómo evitar la limitación de mensajes correlacionados
Los mensajes que están en cola en BizTalk Server, por ejemplo, a través de una ubicación de recepción o mediante orquestaciones, se pueden procesar en uno de los siguientes modos:  
  
- Pueden activar instancias nuevas de suscriptores (es decir, orquestaciones o puertos de envío)  
  
- Se pueden enrutar a una instancia de suscriptor existente a través de la correlación. Para obtener más información sobre la correlación, vea [utilizando las correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).  
  
  Numerosos programadores piensan en las ubicaciones de recepción para integrar una solución cuando se reciben mensajes de activación y correlacionados para obtener la solución a través del mismo puerto. Esto es natural, puesto que minimiza el número de direcciones a las que los remitentes del mensaje deben realizar el seguimiento. Sin embargo, con la limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], pueden haber ventajas al pensar sobre la secuencia de mensajes de activación y la secuencia de mensajes correlacionados por separado en cuanto se refiere a la limitación.  
  
  Cuando los mensajes de correlación y de activación llegan a través de la misma ubicación de recepción, están sujetos al mismo estado de limitación debido a que la limitación se aplica en el nivel de host. Por tanto, todos los mensajes que llegan a las ubicaciones de recepción del host se limitarán como unidad. Esto no supone un problema para muchos escenarios, aunque hay casos en los que la limitación de correlaciones con activaciones puede dar lugar a un tipo de interbloqueo del sistema.  
  
## <a name="example"></a>Ejemplo  
 Por ejemplo, supongamos que tiene un escenario con una orquestación que recibe una activación, se usa para inicializar un conjunto de correlaciones y, a continuación, recibe un convoy de 10 mensajes más que siguen el conjunto de correlaciones. Además, se supone que, en cuanto a la carga, se acumula un registro en la cola de impresión cuando llega la combinación de mensajes de correlación y de activación, lo que da lugar a una limitación de la cantidad de mensajes que se pueden recibir. Desafortunadamente, los mensajes de correlación se limitan junto con las activaciones, lo que ralentiza la finalización de las orquestaciones y da a lugar a un registro posterior y a una limitación adicional. En el caso de que puedan continuar, esto daría lugar a una limitación del sistema a un rendimiento cercano a cero.  
  
 Al dividir la única ubicación de recepción en dos – una para las activaciones y otra para las correlaciones – y configurar las ubicaciones en hosts individuales, el umbral de limitación del tamaño de base de datos para las activaciones se puede mantener más bajo que el de las correlaciones, que resultará en un rendimiento general de registro reducido y mantendrá el flujo de mensajes.  
  
 Por lo tanto, puede que se pregunte: "¿por qué no puedo aumentar el umbral de tamaño de base de datos para mi única ubicación de recepción para solucionar el problema?" La respuesta es que puede, pero no siempre dará lugar al comportamiento deseado. La limitación se realiza principalmente para proteger al sistema de la sobrecarga. Si aumenta lo suficiente la altura de los umbrales o los desactiva completamente, eliminará esta protección.  
  
## <a name="recommendation"></a>Recomendación  
 La práctica recomendada para escenarios, como los que se describen anteriormente que son sensibles a la limitación de mensajes de correlación, es separar las ubicaciones de recepción en hosts individuales que se pueden limitar de forma independiente.  
  
 Cuando se configuran los hosts individuales para las ubicaciones de recepción, establezca el umbral de limitación del tamaño de base de datos para el host usado por las ubicaciones de recepción como un valor inferior al del umbral de limitación del tamaño de base de datos para el host usado por las orquestaciones o correlaciones.  
  
 Si sabe que la carga nunca será superior al del rendimiento sostenible máximo (MST) del sistema o que los rendimientos máximos se pueden recuperar entre los eventos de rendimiento, el aumento de los umbrales de limitación también funcionará, aunque puede que un rendimiento no se mantenga tan alto como cuando se usan hosts independientes para activaciones y correlaciones.