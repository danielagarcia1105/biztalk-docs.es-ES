---
title: Trabajar con escenarios de convoyes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1028ab37-7ead-41a6-a186-53e5344d1a28
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f1c9931fe91b284c53a05c7868554c622306fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-convoy-scenarios"></a>Trabajar con escenarios de convoyes
A *convoy* existe en cualquier momento que deben estar relacionado con varios mensajes individuales para lograr el resultado requerido. Hay dos tipos principales de convoyes: secuenciales y paralelos.  
  
 En algunas condiciones, una instancia de orquestación puede recibir un grupo de mensajes correlacionados al mismo tiempo. En esta situación, puede producirse una condición de anticipación, en la que uno de los mensajes del grupo debe inicializar un conjunto de correlaciones en la instancia de orquestación antes de que los demás mensajes puedan correlacionarse a esa misma instancia de orquestación.  
  
 Para asegurarse de que todos los mensajes correlacionados se reciban en la misma instancia de correlación, BizTalk Server detecta el potencial de esta condición de anticipación y trata todos estos mensajes como un convoy. Al darlos de alta, el motor de tiempo de ejecución crea una suscripción general y la identifica como parte de un convoy. Una vez rellenada la suscripción, el motor de mensajería crea una suscripción temporal basada en los valores de las propiedades de correlación predefinidas. Esta suscripción temporal se denomina un *conjunto de convoy*. Un conjunto de convoy es un grupo de conjuntos de correlaciones que se usan en un convoy. Todos los mensajes subsiguientes que coincidan con la suscripción general se evaluarán con respecto al conjunto de convoy, y los que coincidan se enrutarán a un puerto existente.  
  
## <a name="using-convoys-with-business-processes"></a>Utilizar convoyes con los procesos empresariales  
 Tenga en cuenta lo siguiente al utilizar el procesamiento de convoyes con un proceso empresarial:  
  
-   A *conjunto de correlaciones* es una lista de propiedades con valores específicos que usan para enrutar mensajes a un proceso empresarial específico. El conjunto de correlaciones usado en un **recepción** forma no puede contener más de tres propiedades que se usan para la correlación. Esto se debe a que estos valores se identifican y almacenan en la base de datos, que admite un máximo de tres parámetros.  
  
-   Los convoyes paralelos y secuenciales pueden coexistir en el mismo proceso empresarial, pero no pueden compartir entre sí ningún conjunto de correlaciones. El motivo es que cada conjunto de correlaciones únicamente puede pertenecer a un convoy.  
  
-   BizTalk Server no admite el procesamiento de convoyes cuando se usa el **Iniciar orquestación** forma para pasar una correlación ya inicializada establecida a una nueva orquestación. Esto se debe a que los conjuntos de convoyes se controlan en la base de datos, de manera independiente con respecto a las instancias de orquestación que ya estén ejecutándose.  
  
-   No se puede usar un solo **recepción** forma que se va a inicializar dos o más conjuntos de correlaciones que se utilizarán en convoyes separados. Por ejemplo, supongamos que la recepción r1 inicializa los conjuntos de correlaciones c1 y c2 del primer convoy, la recepción r2 sigue c1 para el segundo convoy, y la recepción r3 sigue c2 para el tercer convoy. Los conjuntos de convoyes correspondientes al segundo convoy son c1, r2 y los conjuntos de convoyes correspondientes al tercer convoy son c2, r3, todos ellos inicializados por r1. En este caso, el motor de orquestaciones no los tratará como convoyes. El ejemplo constituye un escenario de convoyes válido si tanto r2 como r3 siguen c1 y c2 (c1, r2, r3 y c2, r2, r3), si ambas siguen sólo c1 (c1, r2, r3), o si ambas siguen sólo c2 (c2, r2, r3).  
  
## <a name="zombies"></a>Zombies  
 El uso de convoyes puede dar lugar a mensajes perdidos denominados zombies. Cuando una suscripción de recepción sin activación de una orquestación en ejecución coincide con un mensaje de la base de datos de cuadro de mensajes, el cuadro de mensajes entrega el mensaje a la orquestación. Debido a que el cuadro de mensajes no conoce la lógica empresarial contenida en la orquestación, se limita a entregar a la orquestación todos los mensajes que coinciden con la suscripción. Si cualquiera de estos mensajes se entrega cuando el flujo de ejecución de la orquestación ha pasado las suscripciones de recepción que pueden consumir los mensajes, estos mensajes se convierten en zombies.  
  
 Un ejemplo de esta situación que crea zombies es una recepción dentro de un bucle que se repite 17 veces, pero se entregan al bucle 18 mensajes que coinciden con la suscripción de recepción. (El cuadro de mensajes no conoce que la lógica de la orquestación sólo admite 17 mensajes.) La orquestación no consume el mensaje número 18, porque el flujo de ejecución ya ha salido del bucle. La orquestación se completa, pero con mensajes descartados (zombies) que no se pueden reanudar porque la instancia de la orquestación ya se ha completado.  
  
 Puede administrar los zombies mediante una secuencia de comandos de Instrumental de administración de Windows (WMI) para consultar las instancias cuyo estado es "Suspendido (No reanudable)". Además, el motor de mensajería escribe el mensaje de error "Completado con mensajes descartados" en el registro de eventos.  
  
 Por añadidura, si tiene un convoy secuencial con un ámbito transaccional de larga ejecución y el ámbito tiene una configuración de tiempo de espera, es posible que algunas instancias de orquestación terminen en el estado "Suspendido (No reanudable)". Es probable que observe también que el número de mensajes de salida sumado al número de instancias con el estado "Suspendido (No reanudable)" es inferior al número de mensajes de entrada. Este comportamiento es así por diseño. Cuando se produce una excepción de tiempo de espera, el código entra en el controlador de excepciones. BizTalk Server llama al controlador de excepciones para que controle la excepción, lo que incluye los zombies. Puede utilizar un puerto de envío en el controlador de excepciones para enviar zombies a un destino para su revisión y procesamiento ulteriores.  
  
 Hay otros escenarios que pueden generar zombies además de los convoyes. Por ejemplo, supongamos que una instancia de orquestación espera un mensaje de respuesta de un proceso empresarial y que, por algún motivo, recibe dos mensajes de respuesta que coinciden con la suscripción. En este caso, el segundo mensaje se convierte en zombie. Otro ejemplo es cuando se tiene un **escuchar** forma con un **recepción** forma en una rama y un **retraso** forma en la otra rama. Si llega un mensaje al mismo tiempo en que se agota el tiempo de espera, el mensaje se convierte en zombie.  
  
 Para obtener más información sobre cómo administrar zombies, vea **quitar instancias de servicio suspendidas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
 [Convoyes secuenciales](../core/sequential-convoys.md)  
  
 [Convoyes paralelos](../core/parallel-convoys.md)  
  
## <a name="see-also"></a>Vea también  
 [Usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md)