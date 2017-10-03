---
title: Escalar horizontalmente el nivel de servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, planning
- scaling, load balancing
- host instances, scaling
- scaling, examples
- fault tolerance
- scaling, scaling out
- scaling, fault tolerance
- NLB system, scaling
- scaling, host instances
ms.assetid: 01d1ab20-d7a9-4d0b-a61e-65e56fe5010e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35674e89d8f8104a35718531f2a87f95e8bc67e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-biztalk-server-tier"></a>Escalar horizontalmente el nivel de BizTalk Server
Para escalar horizontalmente el nivel de BizTalk, agregue más hardware a la topología existente. Se recomienda que agregue hardware en los siguientes escenarios:  
  
-   BizTalk Server se convierte en un cuello de botella. Alguno de los problemas siguientes puede causar el cuello de botella:  
  
-   CPU: si el escenario utiliza canalizaciones, asignaciones u orquestaciones que hacen un uso intensivo de CPU, los servidores BizTalk Server no tendrán ningún espacio en cabeza adicional de CPU.  
  
-   Memoria y E/S: si los equipos existentes han alcanzado su límite máximo de memoria y E/S, la única manera de agregar recursos consiste en Agregar otro equipo físico.  
  
-   El escalamiento vertical resulta demasiado caro. Por ejemplo, piense en una topología de servidor BizTalk Server, donde la CPU ha alcanzado su capacidad máxima. Si es más barato agregar equipos con procesadores dobles adicionales, en vez de actualizar el procesador doble a un procesador cuádruple, debería entonces hacer un escalamiento horizontal del sistema.  
  
-   El escalamiento vertical no corrige el cuello de botella. Puede que el escalamiento vertical no funcione en los siguientes escenarios:  
  
    -   E/S está en el nivel máximo para el equipo de BizTalk, de modo que necesita otro equipo para escalar el E/S.  
  
    -   La memoria está en el nivel máximo para su sistema operativo. En este escenario, la única forma de escalar su sistema es agregar un equipo adicional de BizTalk a la topología.  
  
 Es posible que en algunos escenarios desee servidores específicos para recibir, enviar mensajes y procesarlos. Cuando dispone de servidores específicos, es más fácil aislar problemas y realizar el mantenimiento en un equipo sin afectar a los otros. Puede agregar estos equipos escalando horizontalmente el nivel de BizTalk.  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a>Cuándo no es posible escalar horizontalmente el nivel de BizTalk  
  
-   En la base de datos de cuadro de mensaje se produce el cuello de botella.  
  
-   El cuello de botella se produce en un adaptador. Por ejemplo, si utiliza el adaptador de SQL, después de aumentar el número de receptores de BizTalk, la contención de bloqueo se incrementa en la base de datos SQL de la que extrae datos el adaptador de SQL de BizTalk. Esto limita su capacidad de escalar horizontalmente el adaptador de SQL.  
  
 La siguiente ilustración muestra un ejemplo de cómo puede escalar horizontalmente el nivel de BizTalk.  
  
 ![Escala de BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")  
  
 Esta figura muestra una topología de BizTalk escalada horizontalmente, que evoluciona de un servidor BizTalk Server a dos servidores BizTalk Server. En la primera topología de servidor BizTalk Server, tres instancias de host comparten los recursos del equipo de BizTalk. En la segunda topología de servidor BizTalk Server, el host de transmisión se separa en un servidor diferente, con lo que se consigue un mayor rendimiento.  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a>Consideraciones al escalar horizontalmente el nivel de BizTalk  
 Debe plantearse las siguientes preguntas antes de agregar otro equipo de servidor BizTalk Server:  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a>¿Cómo configuro el sistema para el equilibrio de carga y la tolerancia a errores al escalar horizontalmente el nivel de BizTalk?  
 La selección de la tecnología para el equilibrio de carga y la tolerancia a errores depende del adaptador que se utiliza en el escenario. Para adaptadores de SOAP y HTTP, la manera recomendada es usar NLB. Para obtener más detalles, consulte la documentación de NLB.  
  
#### <a name="how-do-i-refactor-the-host-instances"></a>¿Cómo volver a descomponer en factores las instancias de host?  
 No hay una regla única para determinar cómo debe volver a descomponer en factores las instancias de host al realizar un escalamiento horizontal del nivel de BizTalk. La factorización de las instancias de host depende de la complejidad del escenario. A continuación, se muestran algunos ejemplos sobre el modo de descomponer en factores las instancias de host.  
  
##### <a name="scenario-1"></a>Escenario 1  
 Una configuración de servidor BizTalk Server e instancias de host de recepción y transmisión se encuentran en el mismo equipo.  
  
 Suponga que hay un cuello de botella de CPU. Agrega otro equipo de BizTalk idéntico al grupo para realizar un escalamiento horizontal, lo que le proporciona dos formas de descomponer en factores las instancias de host.  
  
 A continuación se enumeran dos soluciones para este problema:  
  
-   **Solución 1**: la manera más fácil de factorizar en este escenario es clonar la factorización de instancia host desde el primer equipo al segundo equipo. Por lo tanto, en términos de funcionalidad, el segundo equipo es una copia exacta del primero; también puede tener tanto hosts de recepción como de envío. Suponiendo que no hay ningún otro cuello de botella, puede obtener un factor de escalamiento de 2 dado que se duplican los recursos de CPU.  
  
-   **Solución 2**: otra manera en factores las instancias de host es aislar la recepción y envío de funciones en equipos diferentes. Por lo tanto, uno de los servidores BizTalk Server es exclusivo para la recepción y otro para el envío.  
  
 **Comparar solución 1 y 2 de la solución**  
  
 En la solución 1, el número de instancias de host se duplica con respecto a una configuración BTS. Esto significa que aumentará la contención de bloqueo en el servidor SQL Server. El aumento en contención de bloqueo determinará el factor de escalamiento. Si la contención de bloqueo está dentro de límites que puedan convertirla en un cuello de botella, puede obtener un factor de escalamiento de 2.  
  
 La ventaja de la solución 2 es tener sólo dos instancias de host, por lo que la contención de bloqueo en el servidor SQL server debe ser menor comparada con la solución 1. Sin embargo, el factor de escalamiento depende por completo la complejidad de la recepción y envío instancias de host. Considere los casos siguientes en la solución 2:  
  
 Suponga que las instancias de host tanto de recepción como de transmisión son de la misma intensidad y cada una de ellas utiliza el 50 % de la CPU en la primera topología de servidor BizTalk Server. En la segunda topología de servidor BizTalk Server, se desplaza la instancia de host de transmisión a un equipo diferente y ahora tanto la recepción como la transmisión duplican los recursos. Esto debería proporcionar un factor de escalamiento de 2,  suponiendo que no hay ningún otro cuello de botella. Este caso resulta mejor que la Solución 1 porque hay solamente dos instancias de host y, por lo tanto, una menor contención de bloqueo.  
  
 Suponga que la transmisión es más intensa que la recepción y utiliza el 80 % de los recursos de la CPU en la primera topología de servidor BizTalk Server. Al mover la instancia de host de transmisión a otra máquina, obtendrá únicos de los recursos de CPU de más de 20% para que el factor de escalamiento máximo será de 1,2. Además, el equipo con la instancia de host de recepción usará sólo recursos de CPU de 20-30% para que la ventaja de escalamiento horizontal es mucho menor.  
  
 Observe la siguiente ilustración, que tiene cuatro servidores BizTalk Server. Todos los equipos son receptores y emisores, lo que ofrece un total de cuatro instancias de host de cada tipo (recepción y transmisión).  
  
 ![Re &#45; las instancias de host factorización](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")  
  
 Esta topología podría no ser la mejor posible. También debería probar otras permutaciones de factorización, en función de la complejidad del escenario. Por ejemplo:  
  
-   Dedique dos equipos a la recepción y otros dos a la transmisión. Esto le dará el mejor escalamiento posible cuando tanto la recepción como el envío son igualmente intensivos.  
  
-   Dedique tres equipos a la recepción y uno a la transmisión si la recepción es más intensiva que la transmisión.  
  
-   Dedique un equipo a la recepción y tres a la transmisión si la transmisión es más intensiva que la recepción.  
  
 En todos los escenarios, se recomienda que minimice el número de instancias de host de cada host para reducir la contención en la base de datos de cuadro de mensajes y para que, al mismo tiempo, la utilización de los recursos del equipo sea la máxima. La mejor permutación de factorización dependerá de la complejidad del escenario y del tipo de cuello de botella. Compruebe siempre la factorización antes de finalizar una permutación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md)   
 [Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md)   
 [Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md)   
 [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)   
 [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)   
 [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Bases de datos de escala horizontal](../core/scaled-out-databases.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)