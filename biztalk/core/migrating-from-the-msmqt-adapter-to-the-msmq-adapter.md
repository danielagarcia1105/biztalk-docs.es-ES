---
title: Migrar desde el adaptador de MSMQT al adaptador MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 12/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97126f70-0be5-4a2f-bcba-173fd932b6de
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0184254236cd898683956f7bdc4c81b91a599b94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974077"
---
# <a name="migrate-from-the-msmqt-adapter-to-the-msmq-adapter"></a>Migrar desde el adaptador de MSMQT al adaptador de MSMQ
Este tema comenta los aspectos que se deben considerar respecto a la entrega ordenada de un extremo a otro, la coherencia transaccional, una alta disponibilidad y escalabilidad antes de migrar soluciones del adaptador de BizTalk para Message Queue (MSMQT) al adaptador de Message Queue Server (MSMQ). En este tema, los conceptos de entrega ordenada, coherencia transaccional, alta disponibilidad y escalabilidad son los siguientes:  
  
-   **Entrega ordenada.** Garantizar que los mensajes se envían desde BizTalk Server en el mismo orden en el que se recibieron.  
  
-   **Coherencia transaccional.** Garantizar que no se pierden ni se duplican los mensajes que se procesan debido a errores de hardware, de software o de red.  
  
-   **Alta disponibilidad.** Garantizar que los servicios usados para procesar mensajes están siempre disponibles para el procesamiento.  
  
-   **Escalabilidad.** Capacidad de aumentar el volumen de procesamiento de mensajes existente.  
  
## <a name="end-to-end-ordered-delivery"></a>Entrega ordenada de extremo a otro  
 El adaptador de MSMQT garantiza la entrega ordenada de los mensajes de un extremo a otro. Esto significa que si una aplicación MSMQ envía los mensajes 1, 2 y 3 a una ubicación de recepción enlazada al adaptador de MSMQT, estos mensajes se entregan a una orquestación o un puerto de envío de BizTalk Server en el mismo orden: 1, 2, 3. Un uso de esta funcionalidad serían las operaciones de bolsa que se deben enviar y ejecutar en el mismo orden en el que se reciben.  
  
 La entrega ordenada de un extremo a otro con MSMQT requiere el trabajo conjunto de muchos componentes. La siguiente secuencia de sucesos muestra cómo se lleva esto a cabo con el adaptador de MSMQT:  
  
1. La API MSMQ de un equipo remoto recibe los mensajes 1, 2 y 3 en orden y los envía a una cola transaccional local en el mismo orden: 1, 2, 3.  
  
2. Un cliente MSMQ del equipo remoto toma los mensajes de la cola y los envía a la cola MSMQT en este orden: 1, 2, 3.  
  
3. El adaptador de MSMQT recibe los mensajes en el orden 1, 2, 3 y los entrega al componente Agente de mensajes de BizTalk en el mismo orden: 1, 2, 3.  
  
4. El componente Agente de mensajes de BizTalk garantiza que los mensajes se envíen al cuadro de mensaje en este orden: 1, 2, 3.  
  
5. El cuadro de mensaje enruta los mensajes y garantiza que, si se enrutan a la misma instancia de una orquestación o un puerto de envío, se entreguen a esta instancia en el mismo orden: 1, 2, 3.  
  
   En BizTalk Server 2004, MSMQT era el único adaptador capaz de garantizar end-to-end entrega ordenada. Todos los demás adaptadores integrados de BizTalk pueden cambiar el orden de los mensajes en los pasos 3 a 5 anteriores. La mayoría de los demás adaptadores integrados completan el paso 3 usando un componente conocido como Gestor extremo, que es intrínsecamente multiproceso y, por tanto, no mantiene el orden. El adaptador de MSMQ de BizTalk Server 2004 utiliza una característica de "Procesamiento en serie" que se conserva el orden en el paso 3, pero luego no piden el agente de mensajes para conservar el orden en el futuro, por lo que los mensajes se pueden enrutar a una orquestación o puerto de envío fuera de servicio.  
  
   **Entrega ordenada con el adaptador de MSMQ de extremo a otro**  
  
   Para lograr una entrega ordenada con el adaptador de MSMQ de extremo a otro, siga estos pasos:  
  
6. Habilitar la **entrega ordenada** de puerto para la orquestación de suscripción de propiedad en la recepción o puerto de envío. En BizTalk Server, los puertos en orquestaciones de recepción y puertos de envío una **entrega ordenada** opción de configuración. Si está habilitada esta opción, el puerto de recepción de la orquestación o el puerto de envío pide al cuadro de mensajes que le entregue los mensajes en el mismo orden en el que se enviaron al cuadro de mensajes.  
  
7. Establecer el **procesamiento ordenado** propiedad para la ubicación de recepción que está enlazada al adaptador de MSMQ a `True`. En BizTalk Server, que use el transporte de MSMQ puede configurarse para utilizar procesamiento ordenado que, si está habilitada, se asegura de que los mensajes se envían en el cuadro de mensajes en el mismo orden que se reciben de las ubicaciones de recepción.  
  
8. Establecer el **transaccional** propiedad para la ubicación de recepción que está enlazada al adaptador de MSMQ a `True`.  
  
9. Asegúrese de que las colas MSMQ que están supervisando las ubicaciones de recepción de MSMQ están marcadas como "Transaccional". Esta propiedad debe estar establecida en las colas para garantizar la entrega ordenada de los mensajes.  
  
> [!NOTE]
>  La entrega ordenada de los mensajes está garantizada únicamente si solo un equipo sirve a las colas MSMQ que están supervisando las ubicaciones de recepción de BizTalk. Esto puede suponer problemas de escalabilidad, como se explica a continuación.  
  
## <a name="transaction-usage-when-processing-messages-with-the-msmqt-adapter-vs-the-msmq-adapter"></a>Uso de transacciones cuando se procesan mensajes con el adaptador de MSMQT frente al adaptador de MSMQ  
 Con respecto al uso de transacciones, hay una diferencia clave en el modo en que procesan los mensajes los adaptadores de MSMQT y MSMQ.  
  
 Cuando se usa el adaptador de MSMQT, el proceso de recibir un mensaje de la red y procesarlo con BizTalk Server se realiza en una sola transacción. Cuando se usa el adaptador de MSMQT, los mensajes de confirmación generados para el remitente indican que el mensaje se ha recibido y procesado correctamente en BizTalk Server.  
  
 Cuando se usa el adaptador de MSMQ, los procesos de recibir un mensaje de la red y procesarlo con BizTalk Server se realizan en dos transacciones diferentes, una para recibir el mensaje de la red y otra para procesarlo con BizTalk Server. Cuando se usa el adaptador de MSMQ, los mensajes de confirmación generados para el remitente solo indican que el mensaje se ha recibido correctamente de la red, no que se haya procesado correctamente en BizTalk Server. El remitente recibe un mensaje de confirmación de Microsoft Message Queue Server cuando se recibe el mensaje de la red en el servidor y se guarda en la cola de MSMQ independientemente de que BizTalk Server esté instalado o no. Una vez guardado el mensaje en la cola de MSMQ, el adaptador de MSMQ de BizTalk lo recoge, lo procesa y lo publica en el cuadro de mensajes. Si este proceso no se realiza correctamente, se envía el mensaje a la cola de suspensión de BizTalk o se deja en la cola de MSMQ local (cuando se usa procesamiento transaccional), y el remitente no tiene ninguna indicación de que no se procesó el mensaje en BizTalk Server.  
  
 Si su arquitectura requiere la recepción de mensajes de confirmación cuando BizTalk Server procesa correctamente los mensajes, debe agregar mensajes de confirmación de nivel de aplicación si migra del adaptador de MSMQT al adaptador de MSMQ. Deberá actualizar la aplicación de orquestación y envío para implementar los mensajes de confirmación de nivel de aplicación.  
  
## <a name="high-availability-transactional-in-order"></a>Alta disponibilidad (transaccional, en orden)  
 Para proporcionar alta disponibilidad para el adaptador de MSMQT puede agregar varios equipos al host de recepción y configurar Equilibrio de carga de red (NLB) para tolerancia a errores, o puede agrupar el Host de BizTalk predeterminado. Si ejecuta el adaptador de MSMQT junto con NLB, si un servidor deja de funcionar, los demás servidores controlan la carga. Si ejecuta los controladores del adaptador de MSMQT en un host agrupado y un nodo de host deja de funcionar, el software del clúster conmuta al otro nodo. Cuando se usa el adaptador de MSMQ, NLB no funciona si es necesario procesamiento transaccional sin pérdida de datos, porque el adaptador de MSMQ usa colas de MSMQ locales para almacenamiento intermedio. En este escenario, si se ha entregado un mensaje a la cola de MSMQ local pero no lo ha consumido el adaptador de MSMQ, el mensaje se pierde si el equipo deja de funcionar.  
  
 Para proporcionar alta disponibilidad y coherencia transaccional con el adaptador de MSMQ, debe hacer lo siguiente:  
  
1. Configure Microsoft Message Queuing (MSMQ) como un recurso agrupado en un grupo de clúster de Windows Server en los servidores BizTalk.  
  
2. Configure el controlador de recepción del adaptador de MSMQ en una instancia de host de BizTalk que se haya configurado como un recurso de clúster en el mismo grupo de clúster que el recurso de MSMQ agrupado.  
  
3. Configure el recurso de clúster para la instancia de host de BizTalk con el fin de que mantenga una dependencia del recurso de MSMQ agrupado.  
  
   Para implementar la entrega ordenada con esta arquitectura, siga los pasos que se explican en la sección "End-to-end entrega ordenada con el adaptador de MSMQ."  
  
## <a name="high-availability-nontransactional-not-in-order"></a>Alta disponibilidad (no transaccional, sin orden)  
 Si necesita alta disponibilidad pero no necesita procesamiento transaccional, puede lograrlo con el adaptador de MSMQ, mediante la implementación de NLB y la ejecución de instancias de un host configurado con los controladores de envío y recepción de MSMQ en varios servidores BizTalk detrás de NLB. Al implementar NLB con MSMQ debe seguir los procedimientos recomendados, tal como se describe en el artículo de Microsoft Knowledge Base [899611: cómo Message Queue Server puede funcionar sobre el equilibrio de carga en la red (NLB)](https://support.microsoft.com/help/899611/how-message-queuing-can-function-over-network-load-balancing-nlb). En este escenario, si uno de los servidores BizTalk deja de funcionar, los mensajes que se están ejecutando en la instancia de host de ese servidor BizTalk no estarán disponibles hasta que se recupere el servidor BizTalk. Esta configuración proporciona alta disponibilidad porque, si uno de los servidores de BizTalk no está disponible, NLB enruta las solicitudes al otro servidor BizTalk.  
  
## <a name="scalability-nontransactional-not-in-order"></a>Escalabilidad (no transaccional, sin orden)  
 Para obtener escalabilidad, siga las instrucciones para lograr alta disponibilidad (no transaccional) y agregue instancias de host adicionales. Esta arquitectura proporciona entrega rápida y escalabilidad, pero no proporciona entrega ordenada.  
  
## <a name="scalability-transactional-not-in-order"></a>Escalabilidad (transaccional, sin orden)  
 Para la entrega transaccional de los mensajes sin orden, puede combinar el uso de NLB con clústeres de MSMQ y Windows. Esta arquitectura requiere que configure al menos dos grupos de clúster en dos entornos de Windows Cluster con los pasos que se explican en la sección "Alta disponibilidad (transaccional, en orden)" para cada clúster de Windows. A continuación, implemente NLB para distribuir la carga entre los grupos de clúster. Puesto que no se admite Windows NLB en un clúster de Windows, este escenario requiere una solución de NLB en hardware. El diagrama siguiente muestra esta arquitectura.  
  
 ![Equilibrio de carga entre grupos de clúster](../core/media/scaleclusteredmsmqwithnlb.gif "ScaleClusteredMSMQwithNLB")  
  
> [!NOTE]
>  Esta arquitectura no proporciona entrega ordenada.  
  
## <a name="scalability-transactional-in-order"></a>Escalabilidad (transaccional, en orden)  
 Escalar de forma horizontal una arquitectura que proporcione alta disponibilidad, coherencia transaccional y entrega ordenada es problemático al usar MSMQ 3.0 o anterior, puesto que no se admiten lecturas transaccionales remotas a menos que tanto el equipo con BizTalk Server como el servidor MSMQ remoto ejecuten MSMQ 4.0. Si se usa MSMQ 3.0 o anterior, debe conseguirse la escala horizontal mediante varias colas locales de MSMQ. Además, en este escenario, si se interrumpe la conexión TCP/IP a NLB para la sesión de MSMQ, se puede restaurar después con NLB a otro equipo, lo que puede producir una entrega no ordenada.  
  
 Una posible solución a esta limitación es equilibrar manualmente la carga de entrega de mensajes asignando colas de destino a diferentes equipos. Para ello, vincule instancias de host de BizTalk específicas con colas de MSMQ específicas. Así, por ejemplo, si recibe un gran número de documentos de un socio comercial concreto, cree un host y una cola de recepción aparte en un servidor BizTalk concreto solo para ese asociado.  
  
 Si es posible, ejecute MSMQ 4.0 en equipos remotos cuando se requieran tanto lecturas transaccionales remotas como balance de cargas.  
  
## <a name="summary"></a>Resumen  
 En la tabla siguiente, se resumen las arquitecturas que puede implementar para alojar funcionalidad específica.  
  
|**Funcionalidad**|**Ni NLB ni clúster**|**NLB**|**Cluster**|**NLB y clúster**|  
|-----------------------|---------------------------------|-------------|-----------------|-------------------------|  
|Entrega ordenada de un extremo a otro|Sí|no|Sí|Posible con configuración manual|  
|Coherencia transaccional|No (los mensajes se pueden perder o duplicar si se producen errores en el servicio)|no|Sí|Sí|  
|Alta disponibilidad|no|Sí|Sí|Sí|  
|Escalable|no|Sí|no|Sí|  
  
## <a name="see-also"></a>Vea también  
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)